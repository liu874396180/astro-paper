---
author: lpd
pubDatetime: 2026-01-15T00:00:00.000+08:00
modDatetime:
title: 纯 CSS 实现点中间的渐变效果
featured: false
draft: false
tags:
  - CSS
  - 前端技巧
  - 视觉效果
description: 探索如何使用纯 CSS 创建优雅的点状渐变背景效果，无需 JavaScript 或图片资源
---

## 灵感来源

这个效果的灵感来自 [Polar.sh Hackathon](https://hackathon.polar.sh/) 页面的背景设计。

代码预览：[Tailwind Play](https://play.tailwindcss.com/06FGq1E4gp)

## 效果展示

通过纯 CSS 实现点阵中间的渐变效果，可以创造出优雅且性能友好的背景视觉。

## 技术实现

### 核心思路

使用 CSS 的 `radial-gradient` 和 `background-image` 组合，配合多个背景层叠加实现点阵渐变效果。

### 代码示例