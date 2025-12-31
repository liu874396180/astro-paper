---
author: FjellOverflow
pubDatetime: 2024-07-25T11:11:53Z
modDatetime: 2025-03-12T12:28:53Z
title: How to integrate Giscus comments into AstroPaper
slug: how-to-integrate-giscus-comments
featured: false
draft: true
tags:
  - astro
  - blog
  - docs
description: Comment function on a static blog hosted on GitHub Pages with Giscus.
---

Hosting a thin static blog on a platform like [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site) has numerous advantages, but also takes away some interactivity. Fortunately, [Giscus](https://giscus.app/) exists and offers a way to embed user comments on static sites.

在像 [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site) 这样的平台上托管一个薄静态博客有很多优势，但也去掉了某些交互性。幸运的是，[Giscus](https://giscus.app/) 存在并提供了一种在静态站点上嵌入用户评论的方式。

## Table of contents

## How _Giscus_ works

_Giscus_ 如何工作

[Giscus uses the GitHub API](https://github.com/giscus/giscus?tab=readme-ov-file#how-it-works) to read and store comments made by _GitHub_ users in the `Discussions` associated with a repository.

[Giscus 使用 GitHub API](https://github.com/giscus/giscus?tab=readme-ov-file#how-it-works) 来读取和存储 _GitHub_ 用户在与仓库关联的 `Discussions` 中发表的评论。

Embed the _Giscus_ client-side script bundle on your site, configure it with the correct repository URL, and users can view and write comments (when logged into _GitHub_).

在您的站点上嵌入 _Giscus_ 客户端脚本包，用正确的仓库 URL 配置它，用户就可以查看和写评论（当登录 _GitHub_ 时）。

The approach is serverless, as the comments are stored on _GitHub_ and dynamically loaded from there on client side, hence perfect for a static blog, like _AstroPaper_.

这种方法是无服务器的，因为评论存储在 _GitHub_ 上，并在客户端动态加载，因此非常适合静态博客，如 _AstroPaper_。

## Setting up _Giscus_

设置 _Giscus_

_Giscus_ can be set up easily on [giscus.app](https://giscus.app/), but I will outline the process shortly still.

_Giscus_ 可以在 [giscus.app](https://giscus.app/) 上轻松设置，但我仍将简要概述过程。

### Prerequisites

先决条件

Prerequisites to get _Giscus_ working are

让 _Giscus_ 工作的先决条件是

- the repository is [public](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility#making-a-repository-public)

- 仓库是 [公开的](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility#making-a-repository-public)

- the [Giscus app](https://github.com/apps/giscus) is installed

- [Giscus app](https://github.com/apps/giscus) 已安装

- the [Discussions](https://docs.github.com/en/github/administering-a-repository/managing-repository-settings/enabling-or-disabling-github-discussions-for-a-repository) feature is turned on for your repository

- 您的仓库已开启 [Discussions](https://docs.github.com/en/github/administering-a-repository/managing-repository-settings/enabling-or-disabling-github-discussions-for-a-repository) 功能

If any of these conditions cannot be fulfilled for any reason, unfortunately, _Giscus_ cannot be integrated.

如果由于任何原因无法满足这些条件，不幸的是，_Giscus_ 无法集成。

### Configuring _Giscus_

配置 _Giscus_

Next, configuring _Giscus_ is necessary. In most cases, the preselected defaults are suitable, and you should only modify them if you have a specific reason and know what you are doing. Don't worry too much about making the wrong choices; you can always adjust the configuration later on.

接下来，配置 _Giscus_ 是必要的。在大多数情况下，预选的默认值是合适的，您应该只在有特定原因并知道自己在做什么时修改它们。不要太担心做出错误的选择；您总是可以稍后调整配置。

However you need to

然而您需要

- select the right language for the UI

- 为 UI 选择正确的语言

- specify the _GitHub_ repository you want to connect, typically the repository containing your statically hosted _AstroPaper_ blog on _GitHub Pages_

- 指定您想要连接的 _GitHub_ 仓库，通常是包含您在 _GitHub Pages_ 上静态托管的 _AstroPaper_ 博客的仓库

- create and set an `Announcement` type discussion on _GitHub_ if you want to ensure nobody can create random comments directly on _GitHub_

- 如果您想确保没有人可以在 _GitHub_ 上直接创建随机评论，请创建并设置一个 `Announcement` 类型的讨论

- define the color scheme

- 定义颜色方案

After configuring the settings, _Giscus_ provides you with a generated `<script>` tag, which you will need in the next steps.

配置设置后，_Giscus_ 会为您提供一个生成的 `<script>` 标签，您将在接下来的步骤中需要它。

## Simple script tag

简单的脚本标签

You should now have a script tag that looks like this:

您现在应该有一个看起来像这样的脚本标签：

```html
<script
  src="https://giscus.app/client.js"
  data-repo="[ENTER REPO HERE]"
  data-repo-id="[ENTER REPO ID HERE]"
  data-category="[ENTER CATEGORY NAME HERE]"
  data-category-id="[ENTER CATEGORY ID HERE]"
  data-mapping="pathname"
  data-strict="0"
  data-reactions-enabled="1"
  data-emit-metadata="0"
  data-input-position="bottom"
  data-theme="preferred_color_scheme"
  data-lang="en"
  crossorigin="anonymous"
  async
></script>
```

Simply add that to the source code of the site. Most likely, if you're using _AstroPaper_ and want to enable comments on posts, navigate to `PostDetails.astro` and paste it into the desired location where you want the comments to appear, perhaps underneath the `Share this post on:` buttons.

只需将其添加到站点的源代码中。最有可能的是，如果您使用 _AstroPaper_ 并想在帖子上启用评论，请导航到 `PostDetails.astro` 并将其粘贴到您希望评论出现的位置，或许在 `Share this post on:` 按钮下方。

```astro file=src/layouts/PostDetails.astro
<Layout {...layoutProps}>
  <main>
    <ShareLinks />

    <!-- [!code ++:6] -->
    <script
      src="https://giscus.app/client.js"
      data-repo="[ENTER REPO HERE]"
      data-repo-id="[ENTER REPO ID HERE]"
      data-category="[ENTER CATEGORY NAME HERE]"
      data-category-id="[ENTER CATEGORY ID HERE]"></script>
  </main>
  <Footer />
</Layout>
```

And it's done! You have successfully integrated comments in _AstroPaper_!

完成了！您已经成功在 _AstroPaper_ 中集成了评论！

## React component with light/dark theme

带有亮/暗主题的 React 组件

The embedded script tag in the layout is quite static, with the _Giscus_ configuration, including `theme`, hardcoded into the layout. Given that _AstroPaper_ features a light/dark theme toggle, it would be nice for the comments to seamlessly transition between light and dark themes along with the rest of the site. To achieve this, a more sophisticated approach to embedding _Giscus_ is required.

布局中嵌入的脚本标签相当静态，_Giscus_ 配置，包括 `theme`，硬编码到布局中。鉴于 _AstroPaper_ 具有亮/暗主题切换，让评论与站点的其余部分无缝过渡到亮和暗主题会很好。要实现这一点，需要一种更复杂的嵌入 _Giscus_ 的方法。

Firstly, we are going to install the [React component](https://www.npmjs.com/package/@giscus/react) for _Giscus_:

首先，我们将安装 _Giscus_ 的 [React 组件](https://www.npmjs.com/package/@giscus/react)：

```bash
npm i @giscus/react && npx astro add react
```

Then we create a new `Comments.tsx` React component in `src/components`:

然后我们在 `src/components` 中创建一个新的 `Comments.tsx` React 组件：

```tsx file=src/components/Comments.tsx
import Giscus, { type Theme } from "@giscus/react";
import { GISCUS } from "@/constants";
import { useEffect, useState } from "react";

interface CommentsProps {
  lightTheme?: Theme;
  darkTheme?: Theme;
}

export default function Comments({
  lightTheme = "light",
  darkTheme = "dark",
}: CommentsProps) {
  const [theme, setTheme] = useState(() => {
    const currentTheme = localStorage.getItem("theme");
    const browserTheme = window.matchMedia("(prefers-color-scheme: dark)")
      .matches
      ? "dark"
      : "light";

    return currentTheme || browserTheme;
  });

  useEffect(() => {
    const mediaQuery = window.matchMedia("(prefers-color-scheme: dark)");
    const handleChange = ({ matches }: MediaQueryListEvent) => {
      setTheme(matches ? "dark" : "light");
    };

    mediaQuery.addEventListener("change", handleChange);

    return () => mediaQuery.removeEventListener("change", handleChange);
  }, []);

  useEffect(() => {
    const themeButton = document.querySelector("#theme-btn");
    const handleClick = () => {
      setTheme(prevTheme => (prevTheme === "dark" ? "light" : "dark"));
    };

    themeButton?.addEventListener("click", handleClick);

    return () => themeButton?.removeEventListener("click", handleClick);
  }, []);

  return (
    <div className="mt-8">
      <Giscus theme={theme === "light" ? lightTheme : darkTheme} {...GISCUS} />
    </div>
  );
}
```

This _React_ component not only wraps the native _Giscus_ component, but also introduces additional props, namely `lightTheme` and `darkTheme`. Leveraging two event listeners, the _Giscus_ comments will align with the site's theme, dynamically switching between dark and light themes whenever the site or browser theme is changed.

这个 _React_ 组件不仅包装了原生的 _Giscus_ 组件，还引入了额外的 props，即 `lightTheme` 和 `darkTheme`。利用两个事件监听器，_Giscus_ 评论将与站点的主题对齐，每当站点或浏览器主题改变时动态切换暗和亮主题。

We also need to define the `GISCUS` config, for which the optimal location is in `constants.ts`:

我们还需要定义 `GISCUS` 配置，其最佳位置在 `constants.ts` 中：

```ts file=src/constants.ts
import type { GiscusProps } from "@giscus/react";

...

export const GISCUS: GiscusProps = {
  repo: "[ENTER REPO HERE]",
  repoId: "[ENTER REPO ID HERE]",
  category: "[ENTER CATEGORY NAME HERE]",
  categoryId: "[ENTER CATEGORY ID HERE]",
  mapping: "pathname",
  reactionsEnabled: "0",
  emitMetadata: "0",
  inputPosition: "bottom",
  lang: "en",
  loading: "lazy",
};
```

Note that specifying a `theme` here will override the `lightTheme` and `darkTheme` props, resulting in a static theme setting, similar to the previous approach of embedding _Giscus_ with the `<script>` tag.

请注意，在这里指定 `theme` 将覆盖 `lightTheme` 和 `darkTheme` props，导致静态主题设置，类似于使用 `<script>` 标签嵌入 _Giscus_ 的以前方法。

To complete the process, add the new Comments component to `PostDetails.astro` (replacing the `script` tag from the previous step).

要完成过程，将新的 Comments 组件添加到 `PostDetails.astro`（替换上一步的 `script` 标签）。

```jsx file=src/layouts/PostDetails.astro
// [!code ++:1]
import Comments from "@/components/Comments";

<ShareLinks />

// [!code ++:1]
<Comments client:only="react" />

<hr class="my-6 border-dashed" />

<Footer />
```

And that's it!

就是这样！
