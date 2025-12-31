---
author: Sat Naing
pubDatetime: 2022-09-25T15:20:35Z
modDatetime: 2025-06-13T16:46:34.155Z
title: Customizing AstroPaper theme color schemes
featured: false
draft: true
tags:
  - color-schemes
  - docs
description:
  How you can enable/disable light & dark mode; and customize color schemes
  of AstroPaper theme.
---

This post will explain how you can enable/disable light & dark mode for the website. Moreover, you'll learn how you can customize color schemes of the entire website.

这篇文章将解释您如何为网站启用/禁用亮和暗模式。此外，您将学习如何自定义整个网站的颜色方案。

## Table of contents

## Enable/disable light & dark mode

启用/禁用亮和暗模式

AstroPaper theme will include light and dark mode by default. In other words, there will be two color schemes\_ one for light mode and another for dark mode. This default behavior can be disabled in `SITE` configuration object.

AstroPaper 主题默认将包括亮和暗模式。换句话说，将有两个颜色方案\_ 一个用于亮模式，另一个用于暗模式。此默认行为可以在 `SITE` 配置对象中禁用。

```js file="src/config.ts"
export const SITE = {
  website: "https://astro-paper.pages.dev/", // replace this with your deployed domain
  author: "Sat Naing",
  profile: "https://satnaing.dev/",
  desc: "A minimal, responsive and SEO-friendly Astro blog theme.",
  title: "AstroPaper",
  ogImage: "astropaper-og.jpg",
  lightAndDarkMode: true, // [!code highlight]
  postPerIndex: 4,
  postPerPage: 4,
  scheduledPostMargin: 15 * 60 * 1000, // 15 minutes
  showArchives: true,
  showBackButton: true, // show back button in post detail
  editPost: {
    enabled: true,
    text: "Suggest Changes",
    url: "https://github.com/satnaing/astro-paper/edit/main/",
  },
  dynamicOgImage: true,
  lang: "en", // html lang code. Set this empty and default will be "en"
  timezone: "Asia/Bangkok", // Default global timezone (IANA format) https://en.wikipedia.org/wiki/List_of_tz_database_time_zones
} as const;
```

To disable `light & dark mode` set `SITE.lightAndDarkMode` to `false`.

要禁用 `light & dark mode`，将 `SITE.lightAndDarkMode` 设置为 `false`。

## Choose primary color scheme

选择主要颜色方案

By default, if we disable `SITE.lightAndDarkMode`, we will only get system's prefers-color-scheme.

默认情况下，如果我们禁用 `SITE.lightAndDarkMode`，我们将只获得系统的 prefers-color-scheme。

Thus, to choose primary color scheme instead of prefers-color-scheme, we have to set color scheme in the `primaryColorScheme` variable inside `toggle-theme.js`.

因此，要选择主要颜色方案而不是 prefers-color-scheme，我们必须在 `toggle-theme.js` 中的 `primaryColorScheme` 变量中设置颜色方案。

```js file="public/toggle-theme.js"
const primaryColorScheme = ""; // "light" | "dark" // [!code hl]

// Get theme data from local storage
const currentTheme = localStorage.getItem("theme");

// ...
```

The **primaryColorScheme** variable can hold two values\_ `"light"`, `"dark"`. You can leave the empty string (default) if you don't want to specify the primary color scheme.

**primaryColorScheme** 变量可以持有两个值\_ `"light"`、`"dark"`。如果您不想指定主要颜色方案，您可以留下空字符串（默认）。

- `""` - system's prefers-color-scheme. (default)

- `""` - 系统的 prefers-color-scheme。（默认）

- `"light"` - use light mode as primary color scheme.

- `"light"` - 使用亮模式作为主要颜色方案。

- `"dark"` - use dark mode as primary color scheme.

- `"dark"` - 使用暗模式作为主要颜色方案。

<details>
<summary>Why primaryColorScheme' is not inside config.ts?</summary>
为什么 primaryColorScheme 不在 config.ts 中？
To avoid color flickering on page reload, we have to place the toggle-switch JavaScript codes as early as possible when the page loads. It solves the problem of flickering, but as a trade-off, we cannot use ESM imports anymore.
为了避免页面重新加载时的颜色闪烁，我们必须在页面加载时尽可能早地放置切换开关 JavaScript 代码。它解决了闪烁问题，但作为权衡，我们不能再使用 ESM 导入。
</details>

## Customize color schemes

自定义颜色方案

Both light & dark color schemes of AstroPaper theme can be customized in the `global.css` file.

AstroPaper 主题的亮和暗颜色方案都可以在 `global.css` 文件中自定义。

```css file="src/styles/global.css"
@import "tailwindcss";
@import "./typography.css";

@custom-variant dark (&:where([data-theme=dark], [data-theme=dark] *));

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
/* ... */
```

In the AstroPaper theme, the `:root` and `html[data-theme="light"]` selectors define the light color scheme, while `html[data-theme="dark"]` defines the dark color scheme.

在 AstroPaper 主题中，`:root` 和 `html[data-theme="light"]` 选择器定义亮颜色方案，而 `html[data-theme="dark"]` 定义暗颜色方案。

To customize your own color scheme, specify your light colors inside `:root, html[data-theme="light"]`, and your dark colors inside `html[data-theme="dark"]`.

要自定义您自己的颜色方案，请在 `:root, html[data-theme="light"]` 中指定您的亮颜色，在 `html[data-theme="dark"]` 中指定您的暗颜色。

Here is the detail explanation of color properties.

以下是颜色属性的详细解释。

| Color Property | Definition & Usage                                         |
| -------------- | ---------------------------------------------------------- |
| `--background` | Primary color of the website. Usually the main background. |
| `--foreground` | Secondary color of the website. Usually the text color.    |
| `--accent`     | Accent color of the website. Link color, hover color etc.  |
| `--muted`      | Card and scrollbar background color for hover state etc.   |
| `--border`     | Border color. Especially used in horizontal row (hr)       |

| 颜色属性       | 定义和用法                             |
| -------------- | -------------------------------------- |
| `--background` | 网站的主体颜色。通常是主要背景。       |
| `--foreground` | 网站的次要颜色。通常是文本颜色。       |
| `--accent`     | 网站的强调色。链接颜色、悬停颜色等。   |
| `--muted`      | 卡片和滚动条背景颜色，用于悬停状态等。 |
| `--border`     | 边框颜色。特别是在水平行 (hr) 中使用   |

Here is an example of changing the light color scheme.

以下是更改亮颜色方案的示例。

```css file="src/styles/global.css"
/* ... */
:root,
html[data-theme="light"] {
  --background: #f6eee1;
  --foreground: #012c56;
  --accent: #e14a39;
  --muted: #efd8b0;
  --border: #dc9891;
}
/* ... */
```

> Check out some [predefined color schemes](https://astro-paper.pages.dev/posts/predefined-color-schemes/) AstroPaper has already crafted for you.

> 查看一些 AstroPaper 为您精心制作的 [预定义颜色方案](https://astro-paper.pages.dev/posts/predefined-color-schemes/)。
