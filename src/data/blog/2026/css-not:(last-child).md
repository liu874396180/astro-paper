---
author: lpd
pubDatetime: 2026-01-03T21:50:28.000+08:00
modDatetime:
title: css :not(:last-child)确保最后一个元素之后没有尾随分隔符。
featured: false
draft: false
codepenUrl: https://codepen.io/liu874396180/embed/RNRrWGV?default-tab=html%2Cresult&editable=true
tags:
  - css
description: :not(:last-child)确保最后一个元素之后没有尾随分隔符。
---

- 面包屑导航分隔符应该放在 CSS 中，而不是 HTML 中。只需使用 `::after` 伪元素即可。

```css
nav > ol > li:not(:last-child)::after {
  content: " / ";
  color: lightgray;
  padding: 0 0.5em;
}
```
