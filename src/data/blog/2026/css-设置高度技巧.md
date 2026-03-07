---
author: lpd
pubDatetime: 2026-01-03T23:30:00.000+08:00
modDatetime:
title: CSS 设置高度技巧 - calc-size() 和 stretch
featured: false
draft: false
tags:
  - css
  - 布局
  - 新特性
description: 介绍 CSS 中 calc-size() 和 stretch 的新特性，让高度设置更加灵活和智能。
---

# CSS 设置高度技巧 - calc-size() 和 stretch

CSS 小技巧！它看起来可能很奇怪，难以理解，但它会成为你的救星，而且很可能成为你将来最喜欢的 CSS 小技巧！

## 核心语法

```css
.box {
  height: calc-size(stretch, 0.8 * size);
  /* 等同于 height: calc(0.8 * stretch) */
}
```

## 什么是 calc-size()？

`calc-size()` 是 CSS 的新特性，允许你基于元素的内在尺寸进行计算。它提供了更灵活的方式来设置元素尺寸。

### 语法结构

```css
calc-size(<size-keyword>, <calculation>)
```

### 可用的尺寸关键字

| 关键字 | 说明 |
|--------|------|
| `stretch` | 元素在容器中可伸展的最大尺寸 |
| `fit-content` | 元素适应内容所需的尺寸 |
| `intrinsic` | 元素的内在首选尺寸 |
| `min-intrinsic` | 元素的最小内在尺寸 |

## 使用示例

### 示例 1：基于 stretch 设置高度

```css
/* 让元素高度为可伸展空间的 80% */
.box {
  height: calc-size(stretch, 0.8 * size);
}

/* 传统写法对比 */
.box {
  height: calc(100% * 0.8); /* 需要父元素有明确高度 */
}
```

### 示例 2：Flex 容器中的应用

```css
.container {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.header {
  flex: 0 0 auto;
  height: 60px;
}

.content {
  flex: 1 1 auto;
  /* 占据剩余空间的 80% */
  height: calc-size(stretch, 0.8 * size);
}

.footer {
  flex: 0 0 auto;
  height: 40px;
}
```

### 示例 3：Grid 布局中的应用

```css
.grid-container {
  display: grid;
  grid-template-rows: auto 1fr auto;
  height: 100vh;
}

.grid-content {
  /* 基于网格行高计算 */
  height: calc-size(stretch, 0.9 * size);
  margin: auto 0;
}
```

### 示例 4：响应式卡片

```css
.card-container {
  display: flex;
  height: 400px;
}

.card {
  flex: 1;
  /* 卡片高度为容器的 90%，留出边距 */
  height: calc-size(stretch, 0.9 * size);
  align-self: center;
}
```

## 与传统方案的对比

| 方案 | 代码 | 优点 | 缺点 |
|------|------|------|------|
| **百分比** | `height: 80%` | 简单 | 需要父元素明确高度 |
| **calc()** | `height: calc(100% - 40px)` | 灵活 | 计算复杂 |
| **flex** | `flex: 1` | 自动填充 | 控制精度有限 |
| **calc-size()** | `calc-size(stretch, 0.8*size)` | 精确控制 | 兼容性待提升 |

## 实际应用场景

### 场景 1：模态框内容区域

```css
.modal {
  display: flex;
  flex-direction: column;
  max-height: 90vh;
}

.modal-header {
  flex: 0 0 auto;
}

.modal-body {
  flex: 1 1 auto;
  /* 内容区域占可用空间的 85% */
  height: calc-size(stretch, 0.85 * size);
  overflow-y: auto;
}

.modal-footer {
  flex: 0 0 auto;
}
```

### 场景 2：仪表盘布局

```css
.dashboard {
  display: grid;
  grid-template-rows: 60px 1fr 40px;
  height: 100vh;
}

.dashboard-main {
  /* 主内容区占剩余空间的 95% */
  height: calc-size(stretch, 0.95 * size);
  margin: auto 0;
}
```

### 场景 3：图片画廊

```css
.gallery-item {
  position: relative;
  height: 300px;
}

.gallery-item img {
  /* 图片高度为容器的 90%，居中显示 */
  height: calc-size(stretch, 0.9 * size);
  object-fit: cover;
  margin: auto;
}
```

## 浏览器兼容性

| 浏览器 | 支持版本 | 状态 |
|--------|---------|------|
| Chrome | 123+ | ✅ 支持 |
| Firefox | 125+ | ✅ 支持 |
| Safari | 17.4+ | ✅ 支持 |
| Edge | 123+ | ✅ 支持 |
| IE | - | ❌ 不支持 |

> ⚠️ 注意：`calc-size()` 是较新的 CSS 特性，使用前请检查目标用户的浏览器支持情况。

## 降级方案

```css
/* 渐进增强方案 */
.box {
  /* 降级方案 */
  height: 80%;
  
  /* 新特性增强 */
  @supports (height: calc-size(stretch, size)) {
    height: calc-size(stretch, 0.8 * size);
  }
}
```

## 参考资源

- [CSS Tips - Percentage Height](https://css-tip.com/percentage-height/)
- [MDN - calc-size()](https://developer.mozilla.org/en-US/docs/Web/CSS/calc-size)
- [Can I use - calc-size](https://caniuse.com/css-calc-size)
```