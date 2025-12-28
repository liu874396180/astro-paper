---
author: Sat Naing
pubDatetime: 2023-01-30T15:57:52.737Z
title: AstroPaper 2.0
slug: astro-paper-2
featured: false
ogImage: https://user-images.githubusercontent.com/53733092/215771435-25408246-2309-4f8b-a781-1f3d93bdf0ec.png
tags:
  - release
description: AstroPaper with the enhancements of Astro v2. Type-safe markdown contents, bug fixes and better dev experience etc.
---

Astro 2.0 has been released with some cool features, breaking changes, DX improvements, better error overlay and so on. AstroPaper takes advantage of those cool features, especially Content Collections API.

Astro 2.0 已发布，具有一些酷的功能、破坏性更改、DX 改进、更好的错误覆盖等。AstroPaper 利用了这些酷的功能，特别是 Content Collections API。

<!-- ![Introducing AstroPaper 2.0](https://user-images.githubusercontent.com/53733092/215683840-dc2502f5-8c5a-44f0-a26c-4e7180455056.png) -->

<!-- ![Introducing AstroPaper 2.0](https://user-images.githubusercontent.com/53733092/215683840-dc2502f5-8c5a-44f0-a26c-4e7180455056.png) -->

![Introducing AstroPaper 2.0](https://user-images.githubusercontent.com/53733092/215771435-25408246-2309-4f8b-a781-1f3d93bdf0ec.png)

## Table of contents

## Features & Changes

功能与更改

### Type-safe Frontmatters and Redefined Blog Schema

类型安全的 Frontmatters 和重新定义的博客模式

Frontmatter of AstroPaper 2.0 markdown contents are now type-safe thanks to Astro’s Content Collections. Blog schema is defined inside the `src/content/_schemas.ts` file.

AstroPaper 2.0 markdown 内容的 Frontmatter 现在是类型安全的，感谢 Astro 的 Content Collections。博客模式在 `src/content/_schemas.ts` 文件中定义。

### New Home for Blog contents

博客内容的新家

All the blog posts were moved from `src/contents` to `src/content/blog` directory.

所有博客帖子从 `src/contents` 移动到 `src/content/blog` 目录。

### New Fetch API

新的获取 API

Contents are now fetched with `getCollection` function. No relative path to the content needs to be specified anymore.

内容现在使用 `getCollection` 函数获取。不再需要指定内容的相对路径。

```ts
// old content fetching method
// 旧的内容获取方法
- const postImportResult = import.meta.glob<MarkdownInstance<Frontmatter>>(
  "../contents/**/**/*.md",);

// new content fetching method
// 新的内容获取方法
+ const postImportResult = await getCollection("blog");
```

### Modified Search Logic for better Search Result

修改搜索逻辑以获得更好的搜索结果

In the older version of AstroPaper, when someone search some article, the search criteria keys that will be searched are `title`, `description` and `headings` (heading means all the headings h1 ~ h6 of the blog post). In AstroPaper v2, only `title` and `description` will be searched as the user types.

在旧版本的 AstroPaper 中，当有人搜索某篇文章时，将搜索的搜索标准键是 `title`、`description` 和 `headings`（heading 意味着博客帖子的所有标题 h1 ~ h6）。在 AstroPaper v2 中，只有 `title` 和 `description` 会随着用户输入而被搜索。

### Renamed Frontmatter Properties

重命名的 Frontmatter 属性

The following frontmatter properties are renamed.

以下 frontmatter 属性被重命名。

| Old Names | New Names   |
| --------- | ----------- |
| datetime  | pubDatetime |
| slug      | postSlug    |

### Default Tag for blog post

博客帖子的默认标签

If a blog post doesn't have any tag (in other words, frontmatter property `tags` is not specified), the default tag `others` will be used for that blog post. But you can set the default tag in the `/src/content/_schemas.ts` file.

如果博客帖子没有任何标签（换句话说，frontmatter 属性 `tags` 未指定），默认标签 `others` 将用于该博客帖子。但您可以在 `/src/content/_schemas.ts` 文件中设置默认标签。

```ts
// src/contents/_schemas.ts
export const blogSchema = z.object({
  // ---
  // replace "others" with whatever you want
  // 用您想要的任何东西替换 "others"
  tags: z.array(z.string()).default(["others"]),
  ogImage: z.string().optional(),
  description: z.string(),
});
```

### New Predefined Dark Color Scheme

新的预定义暗色方案

AstroPaper v2 has a new dark color scheme (high contrast & low contrast) which is based on Astro's dark logo. Check out [this link](https://astro-paper.pages.dev/posts/predefined-color-schemes#astro-dark) for more info.

AstroPaper v2 有一个新的暗色方案（高对比度和低对比度），基于 Astro 的暗色 logo。查看 [此链接](https://astro-paper.pages.dev/posts/predefined-color-schemes#astro-dark) 以获取更多信息。

![New Predefined Dark Color Scheme](https://user-images.githubusercontent.com/53733092/215680520-59427bb0-f4cb-48c0-bccc-f182a428d72d.svg)

### Automatic Class Sorting

自动类排序

AstroPaper 2.0 includes automatic class sorting with [TailwindCSS Prettier plugin](https://tailwindcss.com/blog/automatic-class-sorting-with-prettier)

AstroPaper 2.0 包括使用 [TailwindCSS Prettier 插件](https://tailwindcss.com/blog/automatic-class-sorting-with-prettier) 的自动类排序

### Updated Docs & README

更新的文档和 README

All the [#docs](https://astro-paper.pages.dev/tags/docs/) blog posts and [README](https://github.com/satnaing/astro-paper#readme) are updated for this AstroPaper v2.

所有 [#docs](https://astro-paper.pages.dev/tags/docs/) 博客帖子和 [README](https://github.com/satnaing/astro-paper#readme) 都为这个 AstroPaper v2 更新了。

## Bug Fixes

错误修复

- fix broken tags in the Blog Post page

- 修复博客帖子页面中损坏的标签

- in a tag page, the last part of the breadcrumb is now updated to lower-case for consistency

- 在标签页面中，面包屑的最后部分现在更新为小写以保持一致性

- exclude draft posts in a tag page

- 在标签页面中排除草稿帖子

- fix 'onChange value not updating issue' after a page reload

- 修复页面重新加载后 'onChange 值不更新问题'
