---
author: Simon Smale
pubDatetime: 2024-01-03T20:40:08Z
modDatetime: 2024-01-08T18:59:05Z
title: How to use Git Hooks to set Created and Modified Dates
featured: false
draft: false
tags:
  - docs
  - FAQ
canonicalURL: https://smale.codes/posts/setting-dates-via-git-hooks/
description: How to use Git Hooks to set your Created and Modified Dates on AstroPaper
---

In this post I will explain how to use the pre-commit Git hook to automate the input of the created (`pubDatetime`) and modified (`modDatetime`) in the AstroPaper blog theme frontmatter

在这篇文章中，我将解释如何使用 pre-commit Git hook 来自动化 AstroPaper 博客主题 frontmatter 中创建日期（`pubDatetime`）和修改日期（`modDatetime`）的输入

## Table of contents

## Have them Everywhere

[Git hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks) are great for automating tasks like [adding](https://gist.github.com/SSmale/3b380e5bbed3233159fb7031451726ea) or [checking](https://itnext.io/using-git-hooks-to-enforce-branch-naming-policy-ffd81fa01e5e) the branch name to your commit messages or [stopping you committing plain text secrets](https://gist.github.com/SSmale/367deee757a9b2e119d241e120249000). Their biggest flaw is that client-side hooks are per machine.

[Git hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks) 对于自动化任务非常有用，比如 [添加](https://gist.github.com/SSmale/3b380e5bbed3233159fb7031451726ea) 或 [检查](https://itnext.io/using-git-hooks-to-enforce-branch-naming-policy-ffd81fa01e5e) 提交消息中的分支名称，或 [阻止你提交纯文本秘密](https://gist.github.com/SSmale/367deee757a9b2e119d241e120249000)。它们最大的缺陷是客户端钩子是每台机器的。

You can get around this by having a `hooks` directory and manually copy them to the `.git/hooks` directory or set up a symlink, but this all requires you to remember to set it up, and that is not something I am good at doing.

你可以通过拥有一个 `hooks` 目录并手动将它们复制到 `.git/hooks` 目录或设置符号链接来绕过这个问题，但这一切都需要你记住设置它，而这不是我擅长做的事情。

As this project uses npm, we are able to make use of a package called [Husky](https://typicode.github.io/husky/) (this is already installed in AstroPaper) to automatically install the hooks for us.

由于这个项目使用 npm，我们能够利用一个叫做 [Husky](https://typicode.github.io/husky/) 的包（这已经在 AstroPaper 中安装）来自动为我们安装钩子。

> Update! In AstroPaper [v4.3.0](https://github.com/satnaing/astro-paper/releases/tag/v4.3.0), the pre-commit hook has been removed in favor of GitHub Actions. However, you can easily [install Husky](https://typicode.github.io/husky/get-started.html) yourself.

> 更新！在 AstroPaper [v4.3.0](https://github.com/satnaing/astro-paper/releases/tag/v4.3.0) 中，pre-commit hook 已被移除，转而使用 GitHub Actions。然而，你可以轻松地 [自己安装 Husky](https://typicode.github.io/husky/get-started.html)。

## The Hook

As we want this hook to run as we commit the code to update the dates and then have that as part of our change we are going to use the `pre-commit` hook. This has already been set up by this AstroPaper project, but if it hadn't, you would run `npx husky add .husky/pre-commit 'echo "This is our new pre-commit hook"'`.

由于我们希望这个钩子在我们提交代码时运行以更新日期，然后将其作为我们更改的一部分，我们将使用 `pre-commit` hook。这已经由这个 AstroPaper 项目设置好了，但如果没有，你会运行 `npx husky add .husky/pre-commit 'echo "This is our new pre-commit hook"'`。

Navigating to the `hooks/pre-commit` file, we are going to add one or both of the following snippets.

导航到 `hooks/pre-commit` 文件，我们将添加以下一个或两个片段。

### Updating the modified date when a file is edited

当文件被编辑时更新修改日期

---

UPDATE:

This section has been updated with a new version of the hook that is smarter. It will now not increment the `modDatetime` until the post is published. On the first publish, set the draft status to `first` and watch the magic happen.

---

更新：

这一部分已经用一个更智能的钩子版本更新了。现在它不会增加 `modDatetime` 直到帖子发布。在第一次发布时，将草稿状态设置为 `first`，然后看奇迹发生。

---

```shell
# Modified files, update the modDatetime
git diff --cached --name-status |
grep -i '^M.*\.md$' |
while read _ file; do
  filecontent=$(cat "$file")
  frontmatter=$(echo "$filecontent" | awk -v RS='---' 'NR==2{print}')
  draft=$(echo "$frontmatter" | awk '/^draft: /{print $2}')
  if [ "$draft" = "false" ]; then
    echo "$file modDateTime updated"
    cat $file | sed "/---.*/,/---.*/s/^modDatetime:.*$/modDatetime: $(date -u "+%Y-%m-%dT%H:%M:%SZ")/" > tmp
    mv tmp $file
    git add $file
  fi
  if [ "$draft" = "first" ]; then
    echo "First release of $file, draft set to false and modDateTime removed"
    cat $file | sed "/---.*/,/---.*/s/^modDatetime:.*$/modDatetime:/" | sed "/---.*/,/---.*/s/^draft:.*$/draft: false/" > tmp
    mv tmp $file
    git add $file
  fi
done
```

`git diff --cached --name-status` gets the files from git that have been staged for committing. The output looks like:

`git diff --cached --name-status` 从 git 获取已暂存提交的文件。输出看起来像：

```shell
A       src/content/blog/setting-dates-via-git-hooks.md
```

The letter at the start denotes what action has been taken, in the above example the file has been added. Modified files have `M`

开头的字母表示采取了什么行动，在上面的例子中，文件已被添加。修改的文件有 `M`

We pipe that output into the grep command where we are looking at each line to find that have been modified. The line needs to start with `M` (`^(M)`), have any number of characters after that (`.*`) and end with the `.md` file extension (`.(md)$`).This is going to filter out the lines that are not modified markdown files `egrep -i "^(M).*\.(md)$"`.

我们将该输出管道到 grep 命令中，我们在每一行中查找已被修改的。行需要以 `M` 开头（`^(M)`），之后有任意数量的字符（`.*`），并以 `.md` 文件扩展名结束（`.(md)$`）。这将过滤掉不是修改过的 markdown 文件的行 `egrep -i "^(M).*\.(md)$"`。

---

#### Improvement - More Explicit

This could be added to only look for files that we markdown files in the `blog` directory, as these are the only ones that will have the right frontmatter

---

改进 - 更明确

这可以添加为只查找 `blog` 目录中的 markdown 文件，因为这些是唯一具有正确 frontmatter 的文件

---

The regex will capture the two parts, the letter and the file path. We are going to pipe this list into a while loop to iterate over the matching lines and assign the letter to `a` and the path to `b`. We are going to ignore `a` for now.

正则表达式将捕获两部分，字母和文件路径。我们将把这个列表管道到一个 while 循环中，以迭代匹配的行，并将字母分配给 `a`，路径分配给 `b`。我们现在将忽略 `a`。

To know the draft status of the file, we need its frontmatter. In the following code we are using `cat` to get the content of the file, then using `awk` to split the file on the frontmatter separator (`---`) and taking the second block (the fonmtmatter, the bit between the `---`). From here we are using `awk` again to find the draft key and print is value.

为了知道文件的草稿状态，我们需要它的 frontmatter。在下面的代码中，我们使用 `cat` 来获取文件的内容，然后使用 `awk` 在 frontmatter 分隔符（`---`）上分割文件，并取第二个块（fonmtmatter，`---` 之间的位）。从这里，我们再次使用 `awk` 来查找 draft 键并打印其值。

```shell
  filecontent=$(cat "$file")
  frontmatter=$(echo "$filecontent" | awk -v RS='---' 'NR==2{print}')
  draft=$(echo "$frontmatter" | awk '/^draft: /{print $2}')
```

Now we have the value for `draft` we are going to do 1 of 3 things, set the modDatetime to now (when draft is false `if [ "$draft" = "false" ]; then`), clear the modDatetime and set draft to false (when draft is set to first `if [ "$draft" = "first" ]; then`), or nothing (in any other case).

现在我们有了 `draft` 的值，我们将做 3 件事中的 1 件：将 modDatetime 设置为现在（当 draft 为 false 时 `if [ "$draft" = "false" ]; then`），清除 modDatetime 并将 draft 设置为 false（当 draft 设置为 first 时 `if [ "$draft" = "first" ]; then`），或什么都不做（在任何其他情况下）。

The next part with the sed command is a bit magical to me as I don't often use it, it was copied from [another blog post on doing something similar](https://mademistakes.com/notes/adding-last-modified-timestamps-with-git/). In essence, it is looking inside the frontmatter tags (`---`) of the file to find the `pubDatetime:` key, getting the full line and replacing it with the `pubDatetime: $(date -u "+%Y-%m-%dT%H:%M:%SZ")/"` same key again and the current datetime formatted correctly.

下一部分使用 sed 命令对我来说有点神奇，因为我不经常使用它，它是从 [另一篇关于做类似事情的博客文章](https://mademistakes.com/notes/adding-last-modified-timestamps-with-git/) 中复制的。本质上，它在文件的 frontmatter 标签（`---`）内查找 `pubDatetime:` 键，获取整行并用 `pubDatetime: $(date -u "+%Y-%m-%dT%H:%M:%SZ")/" 替换，同样的键再次加上正确格式的当前日期时间。

This replacement is in the context of the whole file so we put that into a temporary file (`> tmp`), then we move (`mv`) the new file into the location of the old file, overwriting it. This is then added to git ready to be committed as if we made the change ourselves.

这个替换是在整个文件的上下文中进行的，所以我们将其放入临时文件（`> tmp`），然后将新文件移动（`mv`）到旧文件的位置，覆盖它。然后将其添加到 git 中，准备提交，就好像我们自己做了更改一样。

---

#### NOTE

For the `sed` to work the frontmatter needs to already have the `modDatetime` key in the frontmatter. There are some other changes you will need to make for the app to build with a blank date, see [further down](#empty-moddatetime-changes)

---

#### 注意

为了让 `sed` 工作，frontmatter 需要已经在 frontmatter 中有 `modDatetime` 键。还有一些其他更改你需要为应用构建空白日期做，见 [进一步向下](#empty-moddatetime-changes)

---

### Adding the Date for new files

为新文件添加日期

Adding the date for a new file is the same process as above, but this time we are looking for lines that have been added (`A`) and we are going to replace the `pubDatetime` value.

为新文件添加日期与上面的过程相同，但这次我们查找已被添加的行（`A`），我们将替换 `pubDatetime` 值。

```shell
# New files, add/update the pubDatetime
git diff --cached --name-status | egrep -i "^(A).*\.(md)$" | while read a b; do
  cat $b | sed "/---.*/,/---.*/s/^pubDatetime:.*$/pubDatetime: $(date -u "+%Y-%m-%dT%H:%M:%SZ")/" > tmp
  mv tmp $b
  git add $b
done
```

---

#### Improvement - Only Loop Once

We could use the `a` variable to switch inside the loop and either update the `modDatetime` or add the `pubDatetime` in one loop.

---

改进 - 只循环一次

我们可以在循环内部使用 `a` 变量来切换，要么更新 `modDatetime`，要么在一个循环中添加 `pubDatetime`。

---

## Populating the frontmatter

填充 frontmatter

If your IDE supports snippets then there is the option to create a custom snippet to populate the frontmatter.[In AstroPaper v4 will come with one for VSCode by default.](https://github.com/satnaing/astro-paper/pull/206)

如果你的 IDE 支持片段，那么有选项创建一个自定义片段来填充 frontmatter。[在 AstroPaper v4 中将默认带有一个用于 VSCode 的。](https://github.com/satnaing/astro-paper/pull/206)

<video autoplay muted="muted" controls plays-inline="true" class="border border-skin-line">
  <source src="https://github.com/satnaing/astro-paper/assets/17761689/e13babbc-2d78-405d-8758-ca31915e41b0" type="video/mp4">
</video>

## Empty `modDatetime` changes

空的 `modDatetime` 更改

To allow Astro to compile the markdown and do its thing, it needs to know what is expected in the frontmatter. It does this via the config in `src/content/config.ts`

为了让 Astro 编译 markdown 并做它的事情，它需要知道 frontmatter 中期望什么。它通过 `src/content/config.ts` 中的配置来做到这一点

To allow the key to be there with no value we need to edit line 10 to add the `.nullable()` function.

为了允许键在那里而没有值，我们需要编辑第 10 行以添加 `.nullable()` 函数。

```ts
const blog = defineCollection({
  type: "content",
  schema: ({ image }) =>
    z.object({
      author: z.string().default(SITE.author),
      pubDatetime: z.date(),
      modDatetime: z.date().optional(), // [!code --]
      modDatetime: z.date().optional().nullable(), // [!code ++]
      title: z.string(),
      featured: z.boolean().optional(),
      draft: z.boolean().optional(),
      tags: z.array(z.string()).default(["others"]),
      ogImage: image().or(z.string()).optional(),
      description: z.string(),
      canonicalURL: z.string().optional(),
      readingTime: z.string().optional(),
    }),
});
```

To stop the IDE complaining in the blog engine files I have also done the following:

为了阻止 IDE 在博客引擎文件中抱怨，我还做了以下事情：

1. added `| null` to line 15 in `src/layouts/Layout.astro` so that it looks like

   添加了 `| null` 到 `src/layouts/Layout.astro` 的第 15 行，所以它看起来像

   ```typescript
   export interface Props {
     title?: string;
     author?: string;
     description?: string;
     ogImage?: string;
     canonicalURL?: string;
     pubDatetime?: Date;
     modDatetime?: Date | null;
   }
   ```

2. added `| null` to line 5 in `src/components/Datetime.tsx` so that it looks like

   添加了 `| null` 到 `src/components/Datetime.tsx` 的第 5 行，所以它看起来像

   ```typescript
   interface DatetimesProps {
     pubDatetime: string | Date;
     modDatetime: string | Date | undefined | null;
   }
   ```
