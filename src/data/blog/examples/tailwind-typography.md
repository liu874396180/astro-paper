---
title: Tailwind Typography Plugin
author: Sat Naing
pubDatetime: 2022-07-05T02:05:51Z
featured: false
draft: true
tags:
  - TypeScript
  - Astro
description: "EXAMPLE POST: About Tailwind Typography Plugin and how you can use it effectively."
---

> This article is from [TailwindLabs](https://tailwindcss-typography.vercel.app/). I put this article to demonstrate how you can write blog posts/articles using AstroPaper theme.

> 这篇文章来自 [TailwindLabs](https://tailwindcss-typography.vercel.app/)。我放这篇文章来演示你如何使用 AstroPaper 主题写博客帖子/文章。

By default, Tailwind removes all of the default browser styling from paragraphs, headings, lists and more. This ends up being really useful for building application UIs because you spend less time undoing user-agent styles, but when you _really are_ just trying to style some content that came from a rich-text editor in a CMS or a markdown file, it can be surprising and unintuitive.

默认情况下，Tailwind 从段落、标题、列表等中移除所有默认的浏览器样式。这最终对构建应用 UI 非常有用，因为你花更少的时间撤销用户代理样式，但当你 _真的只是_ 试图样式化来自 CMS 中的富文本编辑器或 markdown 文件的内容时，它可能会令人惊讶和不直观。

We get lots of complaints about it actually, with people regularly asking us things like:

我们实际上收到了很多关于它的投诉，人们经常问我们类似的事情：

> Why is Tailwind removing the default styles on my `h1` elements? How do I disable this? What do you mean I lose all the other base styles too?

> 为什么 Tailwind 在我的 `h1` 元素上移除默认样式？我如何禁用这个？你是说我还失去了所有其他基础样式？

> We hear you, but we're not convinced that simply disabling our base styles is what you really want. You don't want to have to remove annoying margins every time you use a `p` element in a piece of your dashboard UI. And I doubt you really want your blog posts to use the user-agent styles either — you want them to look _awesome_, not awful.

> 我们听到你了，但我们不相信简单地禁用我们的基础样式就是你真正想要的。你不想每次在你的仪表板 UI 中使用 `p` 元素时都不得不移除烦人的边距。而且我怀疑你真的不想让你的博客帖子使用用户代理样式——你想让它们看起来 _棒极了_，而不是糟糕。

The `@tailwindcss/typography` plugin is our attempt to give you what you _actually_ want, without any of the downsides of doing something stupid like disabling our base styles.

`@tailwindcss/typography` 插件是我们试图给你你 _真正_ 想要的东西的尝试，没有像禁用我们的基础样式那样愚蠢的事情的任何缺点。

It adds a new `prose` class that you can slap on any block of vanilla HTML content and turn it into a beautiful, well-formatted document:

它添加了一个新的 `prose` 类，你可以把它贴在任何块的 vanilla HTML 内容上，并将其变成一个美丽、格式良好的文档：

```html
<article class="prose">
  <h1>Garlic bread with cheese: What the science tells us</h1>
  <p>
    For years parents have espoused the health benefits of eating garlic bread
    with cheese to their children, with the food earning such an iconic status
    in our culture that kids will often dress up as warm, cheesy loaf for
    Halloween.
  </p>
  <p>
    But a recent study shows that the celebrated appetizer may be linked to a
    series of rabies cases springing up around the country.
  </p>
  <!-- ... -->
</article>
```

For more information about how to use the plugin and the features it includes, [read the documentation](https://github.com/tailwindcss/typography/blob/master/README.md).

有关如何使用插件及其包含的功能的更多信息，[阅读文档](https://github.com/tailwindcss/typography/blob/master/README.md)。

---

## What to expect from here on out

从这里开始你会期待什么

What follows from here is just a bunch of absolute nonsense I've written to dogfood the plugin itself. It includes every sensible typographic element I could think of, like **bold text**, unordered lists, ordered lists, code blocks, block quotes, _and even italics_.

从这里开始的只是我写的一堆绝对的废话来测试插件本身。它包括了我能想到的每一个合理的排版元素，如 **粗体文本**、无序列表、有序列表、代码块、块引用、_甚至斜体_。

It's important to cover all of these use cases for a few reasons:

涵盖所有这些用例很重要，原因有几个：

1. We want everything to look good out of the box.

1. 我们希望一切开箱即用看起来不错。

1. Really just the first reason, that's the whole point of the plugin.

1. 真的只是第一个原因，那就是插件的全部要点。

1. Here's a third pretend reason though a list with three items looks more realistic than a list with two items.

1. 这里有一个第三个假装的原因，虽然一个有三个项目的列表看起来比有两个项目的更真实。

Now we're going to try out another header style.

现在我们要试试另一种标题样式。

### Typography should be easy

排版应该很容易

So that's a header for you — with any luck if we've done our job correctly that will look pretty reasonable.

所以这就是你的标题——如果我们正确完成了我们的工作，它看起来会相当合理。

Something a wise person once told me about typography is:

一个聪明的人曾经告诉我关于排版的事情：

> Typography is pretty important if you don't want your stuff to look like trash. Make it good then it won't be bad.

> 如果你不想让你的东西看起来像垃圾，排版很重要。让它好，它就不会坏。

> It's probably important that images look okay here by default as well:

> 可能重要的是图像在这里默认看起来也还可以：

<figure>
  <img
    src="https://images.unsplash.com/photo-1556740758-90de374c12ad?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1000&q=80"
    alt=""
  />
  <figcaption>
    Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of
    classical Latin literature from 45 BC, making it over 2000 years old.
  </figcaption>
</figure>

Now I'm going to show you an example of an unordered list to make sure that looks good, too:

现在我要向你展示一个无序列表的例子，以确保它看起来也不错：

- So here is the first item in this list.

- 所以这里是这个列表中的第一个项目。

- In this example we're keeping the items short.

- 在这个例子中，我们保持项目简短。

- Later, we'll use longer, more complex list items.

- 稍后，我们将使用更长、更复杂的列表项目。

And that's the end of this section.

这就是这一部分的结束。

## What if we stack headings?

如果我们堆叠标题怎么办？

### We should make sure that looks good, too.

我们应该确保那也看起来不错。

Sometimes you have headings directly underneath each other. In those cases you often have to undo the top margin on the second heading because it usually looks better for the headings to be closer together than a paragraph followed by a heading should be.

有时你有标题直接在彼此下面。在那些情况下，你经常不得不撤销第二个标题的顶部边距，因为通常标题彼此靠近看起来比段落后跟标题更好。

### When a heading comes after a paragraph …

当标题在段落后出现时……

When a heading comes after a paragraph, we need a bit more space, like I already mentioned above. Now let's see what a more complex list would look like.

当标题在段落后出现时，我们需要一点更多空间，就像我上面已经提到的。现在让我们看看一个更复杂的列表会是什么样子。

- **I often do this thing where list items have headings.**

- **我经常做这样的事情，列表项目有标题。**

  For some reason I think this looks cool which is unfortunate because it's pretty annoying to get the styles right.

  出于某种原因我认为这看起来酷，这是不幸的，因为让样式正确相当烦人。

  I often have two or three paragraphs in these list items, too, so the hard part is getting the spacing between the paragraphs, list item heading, and separate list items to all make sense. Pretty tough honestly, you could make a strong argument that you just shouldn't write this way.

  我在这些列表项目中也经常有两个或三个段落，所以困难的部分是让段落、列表项目标题和单独列表项目之间的间距都合理。老实说相当艰难，你可以强烈论证你根本不应该这样写。

- **Since this is a list, I need at least two items.**

- **既然这是一个列表，我需要至少两个项目。**

  I explained what I'm doing already in the previous list item, but a list wouldn't be a list if it only had one item, and we really want this to look realistic. That's why I've added this second list item so I actually have something to look at when writing the styles.

  我已经在之前的列表项目中解释了我正在做什么，但如果一个列表只有一个项目，它就不是列表，我们真的想让它看起来真实。这就是为什么我添加了这个第二个列表项目，所以我在写样式时实际上有一些东西可以看。

- **It's not a bad idea to add a third item either.**

- **添加第三个项目也不是一个坏主意。**

  I think it probably would've been fine to just use two items but three is definitely not worse, and since I seem to be having no trouble making up arbitrary things to type, I might as well include it.

  我认为可能只用两个项目就好了，但三个肯定不差，而且既然我似乎在编造任意的东西来打字没有麻烦，我不妨包括它。

After this sort of list I usually have a closing statement or paragraph, because it kinda looks weird jumping right to a heading.

在这种列表之后我通常有一个结束声明或段落，因为直接跳到标题有点看起来奇怪。

## Code should look okay by default.

代码默认应该看起来还可以。

I think most people are going to use [highlight.js](https://highlightjs.org/) or [Prism](https://prismjs.com/) or something if they want to style their code blocks but it wouldn't hurt to make them look _okay_ out of the box, even with no syntax highlighting.

我认为大多数人会使用 [highlight.js](https://highlightjs.org/) 或 [Prism](https://prismjs.com/) 或其他东西如果他们想样式化他们的代码块，但让它们开箱即用看起来 _还可以_ 不会有什么坏处，即使没有语法高亮。

Here's what a default `tailwind.config.js` file looks like at the time of writing:

以下是写这篇文章时默认的 `tailwind.config.js` 文件的样子：

```js
module.exports = {
  purge: [],
  theme: {
    extend: {},
  },
  variants: {},
  plugins: [],
};
```

Hopefully that looks good enough to you.

希望那对你来说看起来足够好。

### What about nested lists?

嵌套列表怎么办？

Nested lists basically always look bad which is why editors like Medium don't even let you do it, but I guess since some of you goofballs are going to do it we have to carry the burden of at least making it work.

嵌套列表基本上总是看起来糟糕，这就是为什么像 Medium 这样的编辑器甚至不让你这样做，但我想既然你们一些傻瓜会这样做，我们不得不承担至少让它工作的负担。

1. **Nested lists are rarely a good idea.**

1. **嵌套列表很少是个好主意。**
   - You might feel like you are being really "organized" or something but you are just creating a gross shape on the screen that is hard to read.

   - 你可能觉得你在“组织”或什么，但你只是在屏幕上创建一个难读的粗糙形状。

   - Nested navigation in UIs is a bad idea too, keep things as flat as possible.

   - UI 中的嵌套导航也是个坏主意，尽可能保持事情平坦。

   - Nesting tons of folders in your source code is also not helpful.

   - 在你的源代码中嵌套大量文件夹也没有帮助。

1. **Since we need to have more items, here's another one.**

1. **既然我们需要有更多项目，这里是另一个。**
   - I'm not sure if we'll bother styling more than two levels deep.

   - 我不确定我们是否会费心样式化超过两层深。

   - Two is already too much, three is guaranteed to be a bad idea.

   - 两层已经太多了，三层保证是个坏主意。

   - If you nest four levels deep you belong in prison.

   - 如果你嵌套四层深，你属于监狱。

1. **And here's a third item.**

1. **这里是第三个项目。**
   - If you nest four levels deep you belong in prison.

   - 如果你嵌套四层深，你属于监狱。

And finally a sentence to close off this section.

最后一句来结束这一部分。
