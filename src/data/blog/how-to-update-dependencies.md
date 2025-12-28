---
title: How to update dependencies of AstroPaper
author: Sat Naing
pubDatetime: 2023-07-20T15:33:05.569Z
slug: how-to-update-dependencies
featured: false
ogImage: ../../assets/images/forrest-gump-quote.png
tags:
  - FAQ
description: How to update project dependencies and AstroPaper template.
---

Updating the dependencies of a project can be tedious. However, neglecting to update project dependencies is not a good idea either 😬. In this post, I will share how I usually update my projects, focusing on AstroPaper as an example. Nonetheless, these steps can be applied to other js/node projects as well.

更新项目的依赖项可能很繁琐。然而，忽视更新项目依赖项也不是一个好主意 😬。在这篇文章中，我将分享我通常如何更新我的项目，以 AstroPaper 为例。不过，这些步骤也可以应用于其他 js/node 项目。

![Forrest Gump Fake Quote](@/assets/images/forrest-gump-quote.png)

## Table of contents

## Updating Package Dependencies

更新包依赖项

There are several ways to update dependencies, and I've tried various methods to find the easiest path. One way to do it is by manually updating each package using `npm install package-name@latest`. This method is the most straightforward way of updating. However, it may not be the most efficient option.

有几种更新依赖项的方法，我尝试了各种方法来找到最简单的路径。一种方法是使用 `npm install package-name@latest` 手动更新每个包。这种方法是更新最直接的方式。然而，它可能不是最有效的选项。

My recommended way of updating dependencies is by using the [npm-check-updates package](https://www.npmjs.com/package/npm-check-updates). There's a good [article](https://www.freecodecamp.org/news/how-to-update-npm-dependencies/) from freeCodeCamp about that, so I won't be explaining the details of what it is and how to use that package. Instead, I'll show you my typical approach.

我推荐的更新依赖项的方式是使用 [npm-check-updates 包](https://www.npmjs.com/package/npm-check-updates)。freeCodeCamp 有一篇关于它的好 [文章](https://www.freecodecamp.org/news/how-to-update-npm-dependencies/)，所以我不会解释它是什么以及如何使用那个包的细节。相反，我将向你展示我的典型方法。

First, install `npm-check-updates` package globally.

首先，全局安装 `npm-check-updates` 包。

```bash
npm install -g npm-check-updates
```

Before making any updates, it’s a good idea to check all new dependencies that can be updated.

在进行任何更新之前，检查所有可以更新的新依赖项是个好主意。

```bash
ncu
```

Most of the time, patch dependencies can be updated without affecting the project at all. So, I usually update patch dependencies by running either `ncu -i --target patch` or `ncu -u --target patch`. The difference is that `ncu -u --target patch` will update all the patches, while `ncu -i --target patch` will give an option to toggle which package to update. It’s up to you to decide which approach to take.

大多数时候，补丁依赖项可以更新而不会影响项目。所以，我通常通过运行 `ncu -i --target patch` 或 `ncu -u --target patch` 来更新补丁依赖项。区别是 `ncu -u --target patch` 将更新所有补丁，而 `ncu -i --target patch` 将给出选项来切换更新哪个包。由你决定采取哪种方法。

The next part involves updating minor dependencies. Minor package updates usually won't break the project, but it is always good to check the release notes of the respective packages. These minor updates often include some cool features that can be applied to our projects.

下一部分涉及更新次要依赖项。次要包更新通常不会破坏项目，但总是检查相应包的发布说明是个好主意。这些次要更新通常包括一些酷的功能，可以应用于我们的项目。

```bash
ncu -i --target minor
```

Last but not least, there might be some major package updates in the dependencies. So, check the rest of the dependency updates by running

最后但并非最不重要，可能在依赖项中有一些主要包更新。所以，通过运行检查其余的依赖项更新

```bash
ncu -i
```

If there are any major updates (or some updates you still have to make), the above command will output those remaining packages. If the package is a major version update, you have to be very careful since this will likely break the whole project. Therefore, please read the respective release note (or) docs very carefully and make changes accordingly.

如果有任何主要更新（或一些你仍然必须做的更新），上面的命令将输出那些剩余的包。如果包是主要版本更新，你必须非常小心，因为这很可能破坏整个项目。因此，请非常仔细地阅读相应的发布说明（或）文档，并相应地进行更改。

If you run `ncu -i` and found no more packages to be updated, _**Congrats!!!**_ you have successfully updated all the dependencies in your project.

如果你运行 `ncu -i` 并发现没有更多包可以更新，_**恭喜！！！**_ 你已经成功更新了项目中的所有依赖项。

## Updating AstroPaper template

更新 AstroPaper 模板

Like other open-source projects, AstroPaper is evolving with bug fixes, feature updates, and so on. So if you’re someone who is using AstroPaper as a template, you might also want to update the template when there’s a new release.

像其他开源项目一样，AstroPaper 正在随着错误修复、功能更新等而发展。所以如果你是使用 AstroPaper 作为模板的人，你可能也想在有新发布时更新模板。

The thing is, you might already have updated the template according to your flavor. Therefore, I can’t exactly show **"the one-size-fits-all perfect way"** to update the template to the most recent release. However, here are some tips to update the template without breaking your repo. Keep in mind that, most of the time, updating the package dependencies might be sufficient for you.

问题是，你可能已经根据你的口味更新了模板。因此，我不能确切地展示 **“一刀切的完美方式”** 来将模板更新到最新发布。然而，这里有一些提示来更新模板而不破坏你的 repo。请记住，大多数时候，更新包依赖项可能对你来说就足够了。

### Files and Directories to keep in mind

需要记住的文件和目录

In most cases, the files and directories you might not want to override (as you've likely updated those files) are `src/content/blog/`, `src/config.ts`, `src/pages/about.md`, and other assets & styles like `public/` and `src/styles/base.css`.

在大多数情况下，你可能不想覆盖的文件和目录（因为你很可能已经更新了那些文件）是 `src/content/blog/`、`src/config.ts`、`src/pages/about.md`，以及其他资产和样式如 `public/` 和 `src/styles/base.css`。

If you’re someone who only updates the bare minimum of the template, it should be okay to replace everything with the latest AstroPaper except the above files and directories. It’s like pure Android OS and other vendor-specific OSes like OneUI. The less you modify the base, the less you have to update.

如果你是只更新模板最低限度的人，将一切替换为最新的 AstroPaper 除了上面的文件和目录应该是可以的。这就像纯 Android OS 和其他供应商特定的 OS 如 OneUI。你修改基础的越少，你需要更新的越少。

You can manually replace every file one by one, or you can use the magic of git to update everything. I won’t show you the manual replacement process since it is very straightforward. If you’re not interested in that straightforward and inefficient method, bear with me 🐻.

你可以手动一个一个替换每个文件，或者你可以使用 git 的魔法来更新一切。我不会展示手动替换过程，因为它非常直接。如果你对那个直接且低效的方法不感兴趣，请耐心等待 🐻。

### Updating AstroPaper using Git

使用 Git 更新 AstroPaper

**IMPORTANT!!!**

> Only do the following if you know how to resolve merge conflicts. Otherwise, you’d better replace files manually or update dependencies only.

**重要！！！**

> 只有在你知道如何解决合并冲突时才做以下事情。否则，你最好手动替换文件或只更新依赖项。

First, add astro-paper as the remote in your project.

首先，在你的项目中添加 astro-paper 作为远程。

```bash
git remote add astro-paper https://github.com/satnaing/astro-paper.git
```

Checkout to a new branch in order to update the template. If you know what you’re doing and you’re confident with your git skill, you can omit this step.

检出到一个新分支以更新模板。如果你知道你在做什么并且对你的 git 技能有信心，你可以省略这一步。

```bash
git checkout -b build/update-astro-paper
```

Then, pull the changes from astro-paper by running

然后，通过运行从 astro-paper 拉取更改

```bash
git pull astro-paper main
```

If you face `fatal: refusing to merge unrelated histories` error, you can resolve that by running the following command

如果你遇到 `fatal: refusing to merge unrelated histories` 错误，你可以通过运行以下命令来解决

```bash
git pull astro-paper main --allow-unrelated-histories
```

After running the above command, you’re likely to encounter conflicts in your project. You'll need to resolve these conflicts manually and make the necessary adjustments according to your needs.

运行上面的命令后，你很可能在你的项目中遇到冲突。你需要手动解决这些冲突，并根据你的需要进行必要的调整。

After resolving the conflicts, test your blog thoroughly to ensure everything is working as expected. Check your articles, components, and any customizations you made.

解决冲突后，彻底测试你的博客以确保一切按预期工作。检查你的文章、组件和你做的任何自定义。

Once you're satisfied with the result, it's time to merge the update branch into your main branch (only if you are updating the template in another branch). Congratulations! You've successfully updated your template to the latest version. Your blog is now up-to-date and ready to shine! 🎉

一旦你对结果满意，是时候将更新分支合并到你的主分支（只有在你在另一个分支中更新模板时）。恭喜！你已经成功将你的模板更新到最新版本。你的博客现在是最新的，准备闪耀！🎉

## Conclusion

结论

In this article, I've shared some of my insights and processes for updating dependencies and the AstroPaper template. I genuinely hope this article proves valuable and assists you in managing your projects more efficiently.

在这篇文章中，我分享了一些我关于更新依赖项和 AstroPaper 模板的见解和过程。我真诚地希望这篇文章证明有价值，并帮助你更有效地管理你的项目。

If you have any alternative or improved approaches for updating dependencies/AstroPaper, I would love to hear from you. Thus, don't hesitate to start a discussion in the repository, email me, or open an issue. Your input and ideas are highly appreciated!

如果你有任何替代或改进的方法来更新依赖项/AstroPaper，我很乐意听到。由此，不要犹豫在仓库中开始讨论，给我发邮件，或打开一个 issue。你的输入和想法非常受欢迎！

Please understand that my schedule is quite busy these days, and I may not be able to respond quickly. However, I promise to get back to you as soon as possible. 😬

请理解我最近的日程很忙，我可能无法快速回应。然而，我保证尽快回复你。😬

Thank you for taking the time to read this article, and I wish you all the best with your projects!

感谢你花时间阅读这篇文章，并祝你在你的项目中一切顺利！
