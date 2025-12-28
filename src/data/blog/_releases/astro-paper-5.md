---
pubDatetime: 2025-03-08T08:18:19.693Z
title: AstroPaper 5.0
slug: astro-paper-v5
featured: true
ogImage: ../../../assets/images/AstroPaper-v5.png
tags:
  - release
description: "AstroPaper v5: keep the clean look, updates under the hood."
---

At last, the long-awaited AstroPaper v5 is finally here. AstroPaper v5 keeps the same minimal & clean look, but comes with significant updates under the hood.

终于，期待已久的 AstroPaper v5 终于来了。AstroPaper v5 保持了相同的最小化和干净外观，但内部有重大更新。

![AstroPaper v5](@/assets/images/AstroPaper-v5.png)

## Table of contents

## Major Changes

主要更改

### Upgrade to Astro v5 [#455](https://github.com/satnaing/astro-paper/pull/455)

升级到 Astro v5 [#455](https://github.com/satnaing/astro-paper/pull/455)

AstroPaper now comes with Astro v5, bringing all the new features and improvements that come with it.

AstroPaper 现在配备了 Astro v5，带来了所有随之而来的新功能和改进。

### Tailwind v4

Tailwind v4

AstroPaper has been upgraded to Tailwind v4, which includes many style changes under the hood. The `tailwind.config.js` file has been removed, and now all the configuration is located within the `src/styles/global.css` file. Typography-related styles have been extracted and moved to `src/styles/typography.css`.

AstroPaper 已升级到 Tailwind v4，其中包括许多内部样式更改。`tailwind.config.js` 文件已被移除，现在所有配置都位于 `src/styles/global.css` 文件中。与排版相关的样式已被提取并移动到 `src/styles/typography.css`。

Due to the new behavior in TailwindCSS v4, styles inside `<style>` blocks within components have been removed and replaced with inline Tailwind classes.

由于 TailwindCSS v4 中的新行为，组件内 `<style>` 块中的样式已被移除并替换为内联 Tailwind 类。

Additionally, the color palette across the UI has been updated. The new palette now consists of only five colors:

此外，整个 UI 的调色板已更新。新调色板现在仅由五种颜色组成：

```css
:root,
html[data-theme="light"] {
  --background: #fdfdfd;
  --foreground: #282728;
  --accent: #006cac;
  --muted: #e6e6e6;
  --border: #ece9e9;
}

html[data-theme="dark"] {
  --background: #212737;
  --foreground: #eaedf3;
  --accent: #ff6b01;
  --muted: #343f60bf;
  --border: #ab4b08;
}
```

### Remove React + Fuse.js in favor of Pagefind search

移除 React + Fuse.js 以支持 Pagefind 搜索

In previous versions, React.js and Fuse.js were used for search functionality and OG image generation. In AstroPaper v5, React.js has been removed and replaced with [Pagefind](https://pagefind.app/), a static site search tool.

在以前的版本中，React.js 和 Fuse.js 用于搜索功能和 OG 图像生成。在 AstroPaper v5 中，React.js 已被移除并替换为 [Pagefind](https://pagefind.app/)，一个静态站点搜索工具。

The search experience is almost identical to previous versions, but now all contents, not just titles and descriptions, are indexed and searchable, thanks to Pagefind.

搜索体验几乎与以前的版本相同，但现在所有内容，而不仅仅是标题和描述，都被索引并可搜索，感谢 Pagefind。

The idea of using Pagefind in dev mode was inspired by [this blog post](https://chrispennington.blog/blog/pagefind-static-search-for-astro-sites/).

在开发模式中使用 Pagefind 的想法受到了 [这篇博客文章](https://chrispennington.blog/blog/pagefind-static-search-for-astro-sites/) 的启发。

### Updated import alias

更新的导入别名

The import alias has been updated from `@directory` to `@/directory`, which means you now have to import like this:

导入别名已从 `@directory` 更新为 `@/directory`，这意味着您现在必须像这样导入：

```astro
---
import { slugifyStr } from "@/utils/slugify";
import IconHash from "@/assets/icons/IconHash.svg";
---
```

### Move to `pnpm`

移动到 `pnpm`

AstroPaper has switched from `npm` to `pnpm`, which offers faster and more efficient package management.

AstroPaper 已从 `npm` 切换到 `pnpm`，它提供更快和更高效的包管理。

### Replace icons/svg with Astro's Svg Component

用 Astro 的 Svg 组件替换图标/svg

AstroPaper v5 replaces inline SVGs with Astro’s experimental [SVG Component](https://docs.astro.build/en/reference/experimental-flags/svg/). This update reduces the need for predefined SVG code in the `socialIcons` object, making the codebase cleaner and more maintainable.

AstroPaper v5 用 Astro 的实验性 [SVG 组件](https://docs.astro.build/en/reference/experimental-flags/svg/) 替换内联 SVG。此更新减少了对 `socialIcons` 对象中预定义 SVG 代码的需求，使代码库更清洁和更易维护。

### Separate Constants and Config

分离常量和配置

The project structure has been reorganized. The `src/config.ts` file now only contains the `SITE` object, which holds the main configuration for the project. All constants, such as `LOCALE`, `SOCIALS`, and `SHARE_LINKS`, have been moved to the `src/constants.ts` file.

项目结构已重组。`src/config.ts` 文件现在只包含 `SITE` 对象，它持有项目的主体配置。所有常量，如 `LOCALE`、`SOCIALS` 和 `SHARE_LINKS`，已移动到 `src/constants.ts` 文件。

## Other notable changes

其他值得注意的更改

- The blog posts directory has been updated from `src/content/blog/` to `src/data/blog/`.

- 博客帖子目录已从 `src/content/blog/` 更新到 `src/data/blog/`。

- Collection definitions file (`src/content/config.ts`) is now replaced with `src/content.config.ts`.

- 集合定义文件（`src/content/config.ts`）现在被 `src/content.config.ts` 替换。

- Various dependencies have been upgraded for improved performance and security.

- 各种依赖项已升级以改进性能和安全性。

- Removed `IBM Plex Mono` font and switched to the default system mono font.

- 移除了 `IBM Plex Mono` 字体并切换到默认系统 mono 字体。

- The `Go back` button logic has been updated. Now, instead of triggering the browser's history API, AstroPaper v5 uses the browser session to temporarily store the back URL. If no back URL exists in the session, it will redirect to the homepage.

- `Go back` 按钮逻辑已更新。现在，不是触发浏览器的历史 API，AstroPaper v5 使用浏览器会话来临时存储返回 URL。如果会话中没有返回 URL，它将重定向到主页。

- There are some minor styles and layout changes as well.

- 还有一些次要的样式和布局更改。

## Outtro

结尾

AstroPaper v5 brings many changes, but the core experience remains the same. Enjoy a smoother, more efficient blogging platform while keeping the clean and minimal design that AstroPaper is known for!

AstroPaper v5 带来了许多更改，但核心体验保持不变。在保持 AstroPaper 闻名的干净和最小化设计的同时，享受更流畅、更高效的博客平台！

Feel free to explore the changes and share your thoughts. As always, thank you for your support!

随意探索更改并分享您的想法。一如既往，感谢您的支持！

If you enjoy this theme, please consider starring the repo. You can also support me via GitHub Sponsors or you can buy me a coffee if you'd like. However, of course, these actions are entirely optional and not required.

如果您喜欢这个主题，请考虑给 repo 加星。您也可以通过 GitHub Sponsors 支持我，或者如果您愿意，可以给我买杯咖啡。当然，这些行动完全是可选的，不是必需的。

Enjoy!

享受！

[Sat Naing](https://satnaing.dev/)
