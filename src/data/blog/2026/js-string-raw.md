---
author: lpd
pubDatetime: 2026-01-03T11:16:18.000+08:00
modDatetime:
title: js String.raw
featured: false
draft: false
tags:
  - js
  - api
description: js String.raw api 学习
---

> `String.raw` 是 JavaScript 中的一个**标签函数**，用于处理模板字符串，它可以获取模板字符串的原始形式，**不处理转义字符**。

## Table of contents

## 基本用法

```javascript
// 普通模板字符串会处理转义字符
console.log(`Hello\nWorld`);
// 输出:
// Hello
// World

// 使用 String.raw() 保持原始形式
console.log(String.raw`Hello\nWorld`);
// 输出: Hello\nWorld
```

## 语法

```javascript
String.raw(callSite, ...substitutions);
// 或更常见的标签语法：
String.raw`templateString`;
```

## 主要特点

### 1. **不转义反斜杠**

```javascript
const path = String.raw`C:\Users\Documents\file.txt`;
console.log(path); // C:\Users\Documents\file.txt

// 对比普通模板字符串
console.log(`C:\Users\Documents\file.txt`);
// 可能输出: C:UsersDocumentsfile.txt (因为 \U, \D, \f 被解释为转义序列)
```

### 2. **与变量插值配合使用**

```javascript
const fileName = "data";
const extension = "txt";

const path = String.raw`C:\Users\${fileName}.${extension}`;
console.log(path); // C:\Users\data.txt
```

### 3. **作为普通函数使用**

```javascript
// 第一个参数是 raw 属性的对象
String.raw({ raw: ["Hello ", " and ", ""] }, "Alice", "Bob");
// 返回: "Hello Alice and Bob"
```

## 实际应用场景

### 1. **正则表达式**

```javascript
// 正则表达式中需要很多反斜杠
const regex = String.raw`\d+\.\d+`;
console.log(regex); // \d+\.\d+

// 等价于：
const regex2 = new RegExp("\\d+\\.\\d+");
```

### 2. **Windows 文件路径**

```javascript
const filePath = String.raw`C:\Program Files\MyApp\config.json`;
```

### 3. **多行字符串保持原样**

```javascript
const code = String.raw`
  function test() {
    console.log("Hello\nWorld");
    return '\u0041';
  }
`;
// 保持 \n 和 \u0041 不被转义
```

### 4. **构建 DSL（领域特定语言）**

```javascript
// 创建自定义模板标签
function highlight(strings, ...values) {
  let result = "";
  strings.forEach((str, i) => {
    result += String.raw`${str}`;
    if (i < values.length) {
      result += `<mark>${values[i]}</mark>`;
    }
  });
  return result;
}

const name = "Alice";
console.log(highlight`Hello, ${name}!`);
```

## 注意事项

```javascript
// String.raw 不会转义任何字符
console.log(String.raw`\u0041`); // 输出: \u0041
console.log(`\u0041`); // 输出: A

// 但是标签模板的插值部分会被正常计算
const count = 3;
console.log(String.raw`Item ${count * 2}`); // Item 6
```

## 实现原理简析

`String.raw` 实际上是这样工作的：

```javascript
String.raw = function (callSite, ...substitutions) {
  let { raw } = callSite;
  let result = "";

  for (let i = 0; i < raw.length; i++) {
    result += raw[i];
    if (i < substitutions.length) {
      result += substitutions[i];
    }
  }

  return result;
};
```

## 总结

`String.raw()` 的主要用途是：

- **处理需要大量反斜杠的字符串**（如正则、路径）
- **保持字符串的原始格式**，避免转义字符被解释
- **作为模板标签的基础构建块**，用于创建更复杂的模板标签函数
- **处理用户输入的字符串**，避免意外的转义

它是一个很实用但相对小众的 API，在特定场景下能大大简化代码编写。
