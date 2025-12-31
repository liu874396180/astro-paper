---
author: Alberto Perdomo
pubDatetime: 2024-09-08T20:58:52.737Z
modDatetime: 2025-03-22T09:25:46.734Z
title: How to add LaTeX Equations in Astro blog posts
draft: true
tags:
  - docs
description: Learn how to add LaTeX equations in Astro blog posts using Markdown, KaTeX, and remark/rehype plugins.
---

This document demonstrates how to use LaTeX equations in your Markdown files for AstroPaper. LaTeX is a powerful typesetting system often used for mathematical and scientific documents.

本文档演示了如何在 AstroPaper 的 Markdown 文件中使用 LaTeX 方程式。LaTeX 是一个强大的排版系统，常用于数学和科学文档。

<figure>
  <img
    src="https://images.pexels.com/photos/22690748/pexels-photo-22690748/free-photo-of-close-up-of-complicated-equations-written-on-a-blackboard.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
    alt="Free Close-up of complex equations on a chalkboard, showcasing chemistry and math symbols. Stock Photo"
  />
  <figcaption class="text-center">
    Photo by <a href="https://www.pexels.com/photo/close-up-of-complicated-equations-written-on-a-blackboard-22690748/">Vitaly Gariev</a>
  </figcaption>
</figure>

## Table of contents

## Instructions

说明

In this section, you will find instructions on how to add support for LaTeX in your Markdown files for AstroPaper.

在本节中，您将找到在 AstroPaper 的 Markdown 文件中添加 LaTeX 支持的说明。

1. Install the necessary remark and rehype plugins by running:

   运行以下命令安装必要的 remark 和 rehype 插件：

   ```bash
   pnpm install rehype-katex remark-math katex
   ```

2. Update the Astro configuration to use the these plugins:

   更新 Astro 配置以使用这些插件：

   ```ts file=astro.config.ts
   // ...
   import remarkMath from "remark-math";
   import rehypeKatex from "rehype-katex";

   export default defineConfig({
     // ...
     markdown: {
       remarkPlugins: [
         remarkMath, // [!code ++]
         remarkToc,
         [remarkCollapse, { test: "Table of contents" }],
       ],
       rehypePlugins: [rehypeKatex], // [!code ++]
       shikiConfig: {
         // For more themes, visit https://shiki.style/themes
         themes: { light: "min-light", dark: "night-owl" },
         wrap: false,
       },
     },
     // ...
   });
   ```

3. Import KaTeX CSS in the main layout file

   在主布局文件中导入 KaTeX CSS

   ```astro file=src/layouts/Layout.astro
   ---
   import { SITE } from "@config";

   // astro code
   ---

   <!doctype html>
   <!-- others... -->
   <script is:inline src="/toggle-theme.js"></script>

   <!-- [!code highlight:4] -->
   <link
     rel="stylesheet"
     href="https://cdn.jsdelivr.net/npm/katex@0.15.2/dist/katex.min.css"
   />

   <body>
     <slot />
   </body>
   ```

4. As the last step, add a text-color for `katex` in `typography.css`.

   最后一步，在 `typography.css` 中为 `katex` 添加文本颜色。

   ```css file=src/styles/typography.css
   @plugin '@tailwindcss/typography';

   @layer base {
     /* other classes */

     /* Katex text color */
     /* [!code highlight:3] */
     .prose .katex-display {
       @apply text-foreground;
     }

     /* ===== Code Blocks & Syntax Highlighting ===== */
     /* other classes */
   }
   ```

And _voilà_, this setup allows you to write LaTeX equations in your Markdown files, which will be rendered properly when the site is built. Once you do it, the rest of the document will appear rendered correctly.

而且 _voilà_，此设置允许您在 Markdown 文件中编写 LaTeX 方程式，这些方程式将在站点构建时正确渲染。一旦您这样做，文档的其余部分将正确显示。

---

## Inline Equations

内联方程式

Inline equations are written between single dollar signs `$...$`. Here are some examples:

内联方程式写在单个美元符号 `$...$` 之间。这里有一些例子：

1. The famous mass-energy equivalence formula: `$E = mc^2$`

1. 著名的质能等价公式：`$E = mc^2$`

1. The quadratic formula: `$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$`

1. 二次公式：`$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$`

1. Euler's identity: `$e^{i\pi} + 1 = 0$`

1. 欧拉恒等式：`$e^{i\pi} + 1 = 0$`

---

## Block Equations

块方程式

For more complex equations or when you want the equation to be displayed on its own line, use double dollar signs `$$...$$`:

对于更复杂的方程式或当您希望方程式显示在其自己的行上时，使用双美元符号 `$$...$$`：

The Gaussian integral:

高斯积分：

```bash
$$ \int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi} $$
```

The definition of the Riemann zeta function:

黎曼 zeta 函数的定义：

```bash
$$ \zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} $$
```

Maxwell's equations in differential form:

麦克斯韦方程式的微分形式：

```bash
$$
\begin{aligned}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\
\nabla \cdot \mathbf{B} &= 0 \\
\nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} \\
\nabla \times \mathbf{B} &= \mu_0\left(\mathbf{J} + \varepsilon_0 \frac{\partial \mathbf{E}}{\partial t}\right)
\end{aligned}
$$
```

---

## Using Mathematical Symbols

使用数学符号

LaTeX provides a wide range of mathematical symbols:

LaTeX 提供了广泛的数学符号：

- Greek letters: `$\alpha$`, `$\beta$`, `$\gamma$`, `$\delta$`, `$\epsilon$`, `$\pi$`

- 希腊字母：`$\alpha$`, `$\beta$`, `$\gamma$`, `$\delta$`, `$\epsilon$`, `$\pi$`

- Operators: `$\sum$`, `$\prod$`, `$\int$`, `$\partial$`, `$\nabla$`

- 运算符：`$\sum$`, `$\prod$`, `$\int$`, `$\partial$`, `$\nabla$`

- Relations: `$\leq$`, `$\geq$`, `$\approx$`, `$\sim$`, `$\propto$`

- 关系：`$\leq$`, `$\geq$`, `$\approx$`, `$\sim$`, `$\propto$`

- Logical symbols: `$\forall$`, `$\exists$`, `$\neg$`, `$\wedge$`, `$\vee$`

- 逻辑符号：`$\forall$`, `$\exists$`, `$\neg$`, `$\wedge$`, `$\vee$`
