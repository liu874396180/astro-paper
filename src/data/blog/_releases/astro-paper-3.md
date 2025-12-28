---
author: Sat Naing
pubDatetime: 2023-09-25T10:25:54.547Z
title: AstroPaper 3.0
slug: astro-paper-v3
featured: false
ogImage: https://github.com/satnaing/astro-paper/assets/53733092/1ef0cf03-8137-4d67-ac81-84a032119e3a
tags:
  - release
description: "AstroPaper Version 3: Elevating Your Web Experience with Astro v3 and Seamless View Transitions"
---

We're excited to announce the release of AstroPaper v3, packed with new features, enhancements, and bug fixes to elevate your web development experience. Let's dive into the highlights of this release:

我们很高兴宣布 AstroPaper v3 的发布，它充满了新功能、增强和错误修复，以提升您的 Web 开发体验。让我们深入了解此版本的亮点：

![AstroPaper v3](@/assets/images/AstroPaper-v3.png)

## Table of contents

## Features & Changes

功能与更改

### Astro v3 Integration

Astro v3 集成

<video autoplay loop="loop" muted="muted" plays-inline="true">
  <source src="https://github.com/satnaing/astro-paper/assets/53733092/18fdb604-1ca3-41a0-8372-1367759091ff" type="video/mp4">
  <!-- <source src="/assets/docs/astro-paper-v3-view-transitions-demo.mp4" type="video/mp4"> -->
</video>

AstroPaper now fully supports [Astro v3](https://astro.build/blog/astro-3/), offering improved performance and rendering speed.

AstroPaper 现在完全支持 [Astro v3](https://astro.build/blog/astro-3/)，提供改进的性能和渲染速度。

Besides, we've added support for Astro's [ViewTransitions API](https://docs.astro.build/en/guides/view-transitions/), allowing you to create captivating and dynamic transitions between views.

此外，我们添加了对 Astro 的 [ViewTransitions API](https://docs.astro.build/en/guides/view-transitions/) 的支持，允许您在视图之间创建引人入胜和动态的过渡。

In the "Recent Section", only non-featured posts will be displayed to avoid duplications and better support for ViewTransitions API.

在“Recent Section”中，只会显示非特色帖子，以避免重复并更好地支持 ViewTransitions API。

### Update OG Image Generation Logic

更新 OG 图像生成逻辑

![Example OG Image](https://user-images.githubusercontent.com/40914272/269252964-a0dc6735-80f7-41ed-8e74-4d4d70f96891.png)

We've updated the logic for automatic OG image generation, making it even more reliable and efficient. Besides, it now supports special characters in post titles, ensuring accurate, flexible and eye-catching social media previews.

我们更新了自动 OG 图像生成的逻辑，使其更加可靠和高效。此外，它现在支持帖子标题中的特殊字符，确保准确、灵活和引人注目的社交媒体预览。

`SITE.ogImage` is now optional. If it is not specified, AstroPaper will automatically generate an OG image using `SITE.title`, `SITE.desc` and `SITE.website`

`SITE.ogImage` 现在是可选的。如果未指定，AstroPaper 将使用 `SITE.title`、`SITE.desc` 和 `SITE.website` 自动生成 OG 图像

### Theme meta tag

主题元标签

The theme-color meta tag has been added to dynamically adapt to theme switches, ensuring a seamless user experience.

主题颜色元标签已被添加，以动态适应主题切换，确保无缝的用户体验。

> Notice the difference at the top

> 注意顶部的差异

**_AstroPaper v2 theme switch_**

**_AstroPaper v2 主题切换_**

<video autoplay loop="loop" muted="muted" plays-inline="true">
  <source src="https://github.com/satnaing/astro-paper/assets/53733092/3ab5a1e8-1891-4264-a5bb-0ded69143c1a" type="video/mp4">
</video>

**_AstroPaper v3 theme switch_**

**_AstroPaper v3 主题切换_**

<video autoplay loop="loop" muted="muted" plays-inline="true">
  <source src="https://github.com/satnaing/astro-paper/assets/53733092/8ac9deb8-d1f8-4029-86bd-6aa0def380b4" type="video/mp4">
</video>

## Other Changes

其他更改

### Astro Prettier Plugin

Astro Prettier 插件

Astro Prettier Plugin is installed out-of-the-box in order to keep the project tidy and organized.

Astro Prettier 插件开箱即用安装，以保持项目整洁和有组织。

### Minor Style Changes

次要样式更改

The single-line code block wrapping issue has been solved, making your code snippets look pristine.

单行代码块换行问题已解决，使您的代码片段看起来完美。

Update nav style CSS to allow adding more nav links to the navigation.

更新导航样式 CSS 以允许在导航中添加更多导航链接。

## Upgrade to AstroPaper v3

升级到 AstroPaper v3

> This section is only for those who want to upgrade AstroPaper v3 from the older versions.

> 此部分仅适用于那些想要从旧版本升级到 AstroPaper v3 的人。

This section will help you migrate from AstroPaper v2 to AstroPaper v3.

此部分将帮助您从 AstroPaper v2 迁移到 AstroPaper v3。

Before reading the rest of the section, you might also want to check [this article](https://astro-paper.pages.dev/posts/how-to-update-dependencies/) for upgrading dependencies and AstroPaper.

在阅读本部分的其余内容之前，您可能还想检查 [这篇文章](https://astro-paper.pages.dev/posts/how-to-update-dependencies/) 以了解升级依赖项和 AstroPaper。

## Option 1: Fresh Restart (recommended)

选项 1：全新重启（推荐）

In this release, a lot of changes have been made\_ replacing old Astro APIs with newer APIs, bug fixes, new features etc. Thus, if you are someone who didn't make customization very much, you should follow this approach.

在此版本中，进行了很多更改\_ 用新的 API 替换旧的 Astro API、错误修复、新功能等。因此，如果您是几乎没有进行自定义的人，您应该遵循此方法。

**_Step 1: Keep all your updated files_**

**_步骤 1：保留所有更新的文件_**

It's important to keep all the files which have been already updated. These files include

重要的是保留所有已经更新的文件。这些文件包括

- `/src/config.ts` (didn't touch in v3)

- `/src/config.ts` (在 v3 中未触及)

- `/src/styles/base.css` (minor changes in v3; mentioned below)

- `/src/styles/base.css` (v3 中的次要更改；如下所述)

- `/src/assets/` (didn't touch in v3)

- `/src/assets/` (在 v3 中未触及)

- `/public/assets/` (didn't touch in v3)

- `/public/assets/` (在 v3 中未触及)

- `/content/blog/` (it's your blog content directory 🤷🏻‍♂️)

- `/content/blog/` (这是您的博客内容目录 🤷🏻‍♂️)

- Any other customizations you've made.

- 您所做的任何其他自定义。

```css
/* file: /src/styles/base.css */
@layer base {
  /* Other Codes */
  ::-webkit-scrollbar-thumb:hover {
    @apply bg-skin-card-muted;
  }

  /* Old code
  code {
    white-space: pre;
    overflow: scroll;
  } 
  */

  /* New code */
  code,
  blockquote {
    word-wrap: break-word;
  }
  pre > code {
    white-space: pre;
  }
}

@layer components {
  /* other codes */
}
```

**_Step 1: Replace everything else with AstroPaper v3_**

**_步骤 1：用 AstroPaper v3 替换其他一切_**

In this step, replace everything\_ except above files/directories (plus your customized files/directories)\_ with AstroPaper v3.

在此步骤中，用 AstroPaper v3 替换一切\_ 除了上面的文件/目录（加上您的自定义文件/目录）\_。

**_Step 3: Schema Updates_**

**_步骤 3：模式更新_**

Keep in mind that `/src/content/_schemas.ts` has been replaced with `/src/content/config.ts`.

请记住，`/src/content/_schemas.ts` 已被 `/src/content/config.ts` 替换。

Besides, there is no longer `BlogFrontmatter` type exported from `/src/content/config.ts`.

此外，`/src/content/config.ts` 中不再导出 `BlogFrontmatter` 类型。

Therefore, all the `BlogFrontmatter` type inside files need to be updated with `CollectionEntry<"blog">["data"]`.

因此，文件中的所有 `BlogFrontmatter` 类型需要更新为 `CollectionEntry<"blog">["data"]`。

For example: `src/components/Card.tsx`

例如：`src/components/Card.tsx`

```ts
// AstroPaper v2
import type { BlogFrontmatter } from "@content/_schemas";

export interface Props {
  href?: string;
  frontmatter: BlogFrontmatter;
  secHeading?: boolean;
}
```

```ts
// AstroPaper v3
import type { CollectionEntry } from "astro:content";

export interface Props {
  href?: string;
  frontmatter: CollectionEntry<"blog">["data"];
  secHeading?: boolean;
}
```

## Option 2: Upgrade using Git

选项 2：使用 Git 升级

This approach is not recommended for most users. You should do the "Option 1" if you can. Only do this if you know how to resolve merge conflicts and you know what you're doing.

此方法不推荐大多数用户。如果可以，您应该做“选项 1”。只有在您知道如何解决合并冲突并且知道自己在做什么时才这样做。

Actually, I've already written a blog post for this case and you can check out [here](https://astro-paper.pages.dev/posts/how-to-update-dependencies/#updating-astropaper-using-git).

实际上，我已经为这种情况写了一篇博客文章，您可以查看 [这里](https://astro-paper.pages.dev/posts/how-to-update-dependencies/#updating-astropaper-using-git)。

## Outro

结尾

Ready to explore the exciting new features and improvements in AstroPaper v3? Start [using AstroPaper](https://github.com/satnaing/astro-paper) now.

准备探索 AstroPaper v3 中的激动人心的新功能和改进吗？现在开始 [使用 AstroPaper](https://github.com/satnaing/astro-paper)。

For other bug fixes and integration updates, check out the [release notes](https://github.com/satnaing/astro-paper/releases/tag/v3.0.0) to learn more.

对于其他错误修复和集成更新，请查看 [发布说明](https://github.com/satnaing/astro-paper/releases/tag/v3.0.0) 以了解更多。

If you encounter any bugs or face difficulties during the upgrade process, please feel free to open an issue or start a discussion on [GitHub](https://github.com/satnaing/astro-paper).

如果您在升级过程中遇到任何错误或面临困难，请随时在 [GitHub](https://github.com/satnaing/astro-paper) 上打开一个 issue 或开始讨论。
