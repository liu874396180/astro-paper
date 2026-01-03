---
author: lpd
pubDatetime: 2026-01-03T22:32:44.000+08:00
modDatetime:
title: addEventListener
featured: false
draft: false
tags:
  - js
  - tips
description: 有一个内置的方法可以在事件监听器首次调用后自动将其移除 - `once`
---

> `once: true` 是 `addEventListener()` 的一个选项，用于**指定事件监听器在触发一次后自动移除**。

## Table of contents

## **`once: true` 介绍**

### 基本语法

```javascript
element.addEventListener(eventType, handler, {
  once: true, // 监听器只执行一次
  capture: false, // 冒泡阶段（默认）
  passive: false, // 是否允许 preventDefault()
});
```

### 简化写法（ES6+）

```javascript
element.addEventListener(
  "click",
  () => {
    console.log("这个只会执行一次！");
  },
  { once: true }
);
```

## **实际应用示例**

### 1. **一次性按钮**

```html
<button id="submitBtn">提交订单</button>

<script>
  const submitBtn = document.getElementById("submitBtn");

  submitBtn.addEventListener(
    "click",
    event => {
      console.log("订单已提交，防止重复提交");
      // 禁用按钮
      event.target.disabled = true;
      // 实际上，由于 once: true，这个监听器已经自动移除了
    },
    { once: true }
  );
</script>
```

### 2. **页面初始化任务**

```javascript
// 页面加载完成后只执行一次的初始化
document.addEventListener(
  "DOMContentLoaded",
  () => {
    console.log("执行一次性初始化任务");
    initializeApp();
  },
  { once: true }
);

// 不再需要手动移除监听器
```

### 3. **模态框关闭后清理**

```html
<button id="openModal">打开对话框</button>
<div id="modal" style="display: none;">我是模态框</div>

<script>
  const openBtn = document.getElementById("openModal");
  const modal = document.getElementById("modal");

  openBtn.addEventListener("click", () => {
    modal.style.display = "block";

    // 点击模态框外部关闭，但只监听一次关闭操作
    document.addEventListener(
      "click",
      e => {
        if (!modal.contains(e.target) && e.target !== openBtn) {
          modal.style.display = "none";
        }
      },
      { once: true }
    ); // 关闭后自动移除
  });
</script>
```

### 4. **表单验证提示**

```html
<input type="email" id="emailInput" placeholder="输入邮箱" />
<div id="hint" style="display:none; color:red;">第一次输入提示</div>

<script>
  const emailInput = document.getElementById("emailInput");
  const hint = document.getElementById("hint");

  // 只在第一次获得焦点时显示提示
  emailInput.addEventListener(
    "focus",
    () => {
      hint.style.display = "block";
      console.log("这是第一次获得焦点提示");
    },
    { once: true }
  );
</script>
```

## **与传统方法的对比**

### **传统方式（需要手动移除）**

```javascript
function handleClick() {
  console.log("点击一次");
  // 需要手动移除
  button.removeEventListener("click", handleClick);
}

button.addEventListener("click", handleClick);
```

### **使用 `once: true`（自动移除）**

```javascript
button.addEventListener(
  "click",
  () => {
    console.log("点击一次 - 自动移除");
  },
  { once: true }
); // 简洁明了！
```

## **浏览器兼容性**

| 特性        | Chrome | Firefox | Safari   | Edge   |
| ----------- | ------ | ------- | -------- | ------ |
| `once` 选项 | 55+ ✅ | 50+ ✅  | 12.1+ ✅ | 79+ ✅ |

### **polyfill（兼容旧浏览器）**

```javascript
// 为不支持 once 的浏览器提供降级方案
function addEventListenerOnce(element, event, handler) {
  // 如果浏览器支持 once 选项
  if ("once" in EventTarget.prototype) {
    element.addEventListener(event, handler, { once: true });
  } else {
    // 传统方式实现
    const onceHandler = e => {
      handler(e);
      element.removeEventListener(event, onceHandler);
    };
    element.addEventListener(event, onceHandler);
  }
}

// 使用 polyfill
addEventListenerOnce(button, "click", () => {
  console.log("兼容所有浏览器的一次性监听器");
});
```

## **与其他事件选项的组合使用**

```javascript
// 组合使用多个选项
element.addEventListener(
  "click",
  event => {
    console.log("一次性、被动、捕获阶段的事件监听器");
  },
  {
    once: true, // 执行一次后移除
    passive: true, // 不会调用 preventDefault()
    capture: true, // 捕获阶段触发
  }
);

// 只用于 touchstart 的被动事件（提高滚动性能）
element.addEventListener(
  "touchstart",
  () => {
    console.log("触摸开始 - 只执行一次");
  },
  {
    once: true,
    passive: true,
  }
);
```

## **注意事项**

1. **`once: true` 与 `removeEventListener`**

   ```javascript
   const handler = () => console.log("点击");

   element.addEventListener("click", handler, { once: true });

   // 如果在触发前手动移除，是可以的
   element.removeEventListener("click", handler);

   // 但如果触发后，监听器已自动移除，再次 remove 也没关系（静默失败）
   ```

2. **多个监听器的情况**

   ```javascript
   // 即使设置了 once: true，同一个事件类型可以有多个监听器
   element.addEventListener(
     "click",
     () => {
       console.log("第一个监听器（一次性）");
     },
     { once: true }
   );

   element.addEventListener("click", () => {
     console.log("第二个监听器（永久）");
   });

   // 第一次点击：两个都会执行
   // 第二次点击：只有第二个会执行
   ```

3. **箭头函数的问题**

   ```javascript
   // 如果以后需要移除，不要用箭头函数
   const handler = function () {
     console.log("具名函数，可以在触发前移除");
   };

   element.addEventListener("click", handler, { once: true });

   // 触发前仍然可以手动移除
   element.removeEventListener("click", handler);
   ```

## **实际应用场景总结**

| 场景             | 使用 `once: true` 的好处                   |
| ---------------- | ------------------------------------------ |
| **表单提交**     | 防止重复提交，无需手动禁用按钮或移除监听器 |
| **教程/引导**    | 用户完成某个操作后，提示自动消失且不再出现 |
| **资源加载**     | 图片/脚本加载完成后的回调只需执行一次      |
| **动画结束**     | CSS 动画/过渡结束后执行清理工作            |
| **用户首次操作** | 只在用户第一次执行某操作时给予提示         |
| **弹窗/通知**    | 通知显示一次后不再打扰用户                 |

## **总结**

`once: true` 是一个非常实用的特性，它：

1. **简化代码**：无需手动编写 `removeEventListener` 逻辑
2. **避免内存泄漏**：确保一次性监听器被正确清理
3. **提高代码可读性**：明确表达了"这个监听器只执行一次"的意图
4. **减少错误**：避免了忘记移除监听器导致的 bug

在支持现代 JavaScript 的项目中，应该优先使用 `{ once: true }` 来处理只需要执行一次的事件监听逻辑。
