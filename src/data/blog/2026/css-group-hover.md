---
author: lpd
pubDatetime: 2026-01-03T22:30:00.000+08:00
modDatetime:
title: CSS hover 和 group-hover 的区别
featured: false
draft: false
tags:
  - css
  - tailwind
  - 交互效果
description: hover 和 group-hover 是 CSS 中处理鼠标悬停效果的两种常用方式，主要区别在于触发作用的范围不同。
---

# CSS hover 和 group-hover 的区别

`hover` 和 `group-hover` 是 CSS 中处理鼠标悬停效果的两种常用方式，它们的主要区别在于**触发作用的范围不同**。

简单来说：`hover` 作用于**自身**，而 `group-hover` 可以让父元素的悬停状态**影响其内部的子元素**。

## 核心区别对比

| 特性 | `hover` | `group-hover` |
| :--- | :--- | :--- |
| **触发方式** | 鼠标悬停在**元素自身**上时触发 | 鼠标悬停在指定的**父容器**（组）上时触发 |
| **影响范围** | 仅改变**被悬停的那个元素**的样式 | 可以改变**组内任意指定子元素**的样式 |
| **主要用途** | 按钮变色、链接下划线、自身放大等自身交互 | 卡片整体悬停时，让卡片内的标题变色、图标旋转、按钮出现等组合动画 |
| **CSS 选择器** | `.element:hover` | `.group:hover .child` |

## 示例说明

### 1. `hover` 的用法（只改变自己）

当鼠标悬停在这个按钮上时，只有这个按钮本身的背景色会变蓝。

```css
/* 定义按钮本身的悬停效果 */
.button {
  background-color: #3498db;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  transition: background-color 0.3s;
}

.button:hover {
  background-color: #2980b9; /* 鼠标悬停时，自身背景色变深 */
}
```

```html
<button class="button">悬停我</button>
```

### 2. `group-hover` 的用法（父级悬停，改变子级）

在一个"卡片"父容器上标记为"组"，当鼠标悬停在整个卡片上时，即使鼠标没有直接放在标题上，标题的颜色也会改变。

```css
/* 将父容器标记为一个"组" */
.group {
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  transition: box-shadow 0.3s;
}

/* 当鼠标悬停在 .group 上时，组内的子元素样式变化 */
.group:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.group:hover .group-title {
  color: #3498db;
}

.group:hover .group-icon {
  transform: rotate(15deg);
}

.group:hover .group-btn {
  opacity: 1;
  visibility: visible;
}

/* 子元素初始样式 */
.group-title {
  color: #666;
  transition: color 0.3s;
}

.group-icon {
  transition: transform 0.3s;
}

.group-btn {
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s, visibility 0.3s;
}
```

```html
<!-- 这是父容器，被标记为 "group" -->
<div class="group">
  <h3 class="group-title">我是标题</h3>
  <div class="group-icon">🔖</div>
  <p>鼠标悬停在整个灰色卡片区域，上面标题的颜色就会变化。</p>
  <button class="group-btn">操作按钮</button>
</div>
```

## Tailwind CSS 中的使用

Tailwind CSS 内置了 `group` 和 `group-hover` 的支持，使用更加简洁：

```html
<!-- Tailwind CSS 写法 -->
<div class="group p-6 border rounded-lg hover:shadow-lg transition-shadow">
  <!-- 悬停卡片时，标题变蓝 -->
  <h3 class="text-gray-500 group-hover:text-blue-500 transition-colors">
    卡片标题
  </h3>
  
  <!-- 悬停卡片时，图标旋转 -->
  <div class="group-hover:rotate-12 transition-transform">
    📌
  </div>
  
  <!-- 悬停卡片时，按钮显示 -->
  <button class="opacity-0 group-hover:opacity-100 transition-opacity">
    点击操作
  </button>
</div>
```

## 实际应用场景

### 场景 1：商品卡片

```html
<div class="group relative">
  <img src="product.jpg" alt="商品" class="w-full" />
  <!-- 悬停时显示快速操作按钮 -->
  <div class="absolute inset-0 bg-black/50 opacity-0 group-hover:opacity-100 
              flex items-center justify-center gap-2 transition-opacity">
    <button>加入购物车</button>
    <button>收藏</button>
  </div>
</div>
```

### 场景 2：导航菜单

```html
<nav class="group">
  <ul class="flex">
    <li class="relative">
      <a href="#">产品</a>
      <!-- 悬停时显示下拉菜单 -->
      <div class="absolute hidden group-hover:block">
        <a href="#">产品 A</a>
        <a href="#">产品 B</a>
      </div>
    </li>
  </ul>
</nav>
```

### 场景 3：图片画廊

```html
<div class="group cursor-pointer">
  <img src="image.jpg" class="w-full group-hover:scale-105 transition-transform" />
  <div class="p-4">
    <h4 class="group-hover:text-primary">图片标题</h4>
    <p class="text-sm text-gray-500">悬停查看效果</p>
  </div>
</div>
```

## 注意事项

1. **嵌套层级** - `group-hover` 可以嵌套使用，父组和子组可以分别响应
2. **性能考虑** - 避免在大型 DOM 树上使用过多的 `group-hover` 效果
3. **移动端兼容** - 移动设备没有 hover 状态，需要考虑触摸交互的替代方案
4. **可访问性** - 确保 hover 效果不是唯一的信息传达方式

## 总结

| 使用场景 | 推荐方案 |
|---------|---------|
| 元素自身交互反馈 | `hover` |
| 容器悬停影响内部多个元素 | `group-hover` |
| 显示/隐藏子元素 | `group-hover` |
| 组合动画效果 | `group-hover` |

* 如果想让**元素自身**对鼠标悬停做出反应，使用 **`hover`**。
* 如果想让**一个容器内的某个部分**，在容器（或更高级的父级）被悬停时做出反应，使用 **`group-hover`** 机制。