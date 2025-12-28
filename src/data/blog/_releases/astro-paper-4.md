---
author: Sat Naing
pubDatetime: 2024-01-04T09:30:41.816Z
title: AstroPaper 4.0
slug: "astro-paper-v4"
featured: false
ogImage: ../../../assets/images/AstroPaper-v4.png
tags:
  - release
description: "AstroPaper v4: ensuring a smoother and more feature-rich blogging experience."
---

Hello everyone! Wishing you a happy New Year 🎉 and all the best for 2024! We're excited to announce the release of AstroPaper v4, a significant update that introduces a range of new features, improvements, and bug fixes to elevate your blogging experience. A big thank you to all the contributors for their valuable input and efforts in making version 4 possible!

大家好！祝您新年快乐 🎉 并在 2024 年一切顺利！我们很高兴宣布 AstroPaper v4 的发布，这是一个重要的更新，引入了一系列新功能、改进和错误修复，以提升您的博客体验。感谢所有贡献者为使版本 4 成为可能提供的宝贵投入和努力！

![AstroPaper v4](@/assets/images/AstroPaper-v4.png)

## Table of contents

## Major Changes

主要更改

### Upgrade to Astro v4 [#202](https://github.com/satnaing/astro-paper/pull/202)

升级到 Astro v4 [#202](https://github.com/satnaing/astro-paper/pull/202)

AstroPaper now leverages the power and capabilities of Astro v4. However, it’s a subtle upgrade and won’t break most Astro users.

AstroPaper 现在利用了 Astro v4 的强大功能和能力。然而，这是一个微妙的升级，不会破坏大多数 Astro 用户。

![Astro v4](https://astro.build/_astro/header-astro-4.YunweN9V_OmV0l.webp)

### Replace `postSlug` with Astro Content `slug` [#197](https://github.com/satnaing/astro-paper/pull/197)

用 Astro Content `slug` 替换 `postSlug` [#197](https://github.com/satnaing/astro-paper/pull/197)

The `postSlug` in the blog content schema is no longer available in AstroPaper v4. Initially Astro doesn't have a `slug` mechanism and thus we have to figure it out on our own. Since Astro v3, it supports content collection and slug features. Now, we believe it's time to adopt Astro's out-of-the-box `slug` feature.

博客内容模式中的 `postSlug` 在 AstroPaper v4 中不再可用。最初 Astro 没有 `slug` 机制，因此我们必须自己弄清楚。从 Astro v3 开始，它支持内容集合和 slug 功能。现在，我们相信是时候采用 Astro 开箱即用的 `slug` 功能了。

**_file: src/content/blog/astro-paper-4.md_**

```bash
---
author: Sat Naing
pubDatetime: 2024-01-01T04:35:33.428Z
title: AstroPaper 4.0
slug: "astro-paper-v4" # if slug is not specified, it will be 'astro-paper-4' (file name).
# slug: "" ❌ cannot be an empty string
---
```

The behavior of the `slug` is slightly different now. In the previous versions of AstroPaper, if the `postSlug` is not specified in a blog post (markdown file), the title of that blog post would be slugified and used as the `slug`. However, in AstroPaper v4, if the `slug` field is not specified, the markdown file name will be used as the `slug`. One thing to keep in mind is that the `slug` field can be omitted, but it cannot be an empty string (slug: "" ❌).

`slug` 的行为现在略有不同。在 AstroPaper 的以前版本中，如果博客帖子（markdown 文件）中未指定 `postSlug`，该博客帖子的标题将被 slugified 并用作 `slug`。然而，在 AstroPaper v4 中，如果未指定 `slug` 字段，markdown 文件名将被用作 `slug`。需要记住的一件事是，`slug` 字段可以省略，但不能是空字符串（slug: "" ❌）。

If you're upgrading AstroPaper from v3 to v4, make sure to replace `postSlug` in your `src/content/blog/*.md` files with `slug`.

如果您正在从 v3 升级 AstroPaper 到 v4，请确保将 `src/content/blog/*.md` 文件中的 `postSlug` 替换为 `slug`。

## New Features

新功能

### Add code-snippets for content creation [#206](https://github.com/satnaing/astro-paper/pull/206)

为内容创建添加代码片段 [#206](https://github.com/satnaing/astro-paper/pull/206)

AstroPaper now includes VSCode snippets for new blog posts, eliminating the need for manual copy/pasting of the frontmatter and content structure (table of contents, heading, excerpt, etc.).

AstroPaper 现在包括用于新博客帖子的 VSCode 片段，消除了手动复制/粘贴 frontmatter 和内容结构（目录、标题、摘录等）的需要。

Read more about VSCode Snippets [here](https://code.visualstudio.com/docs/editor/userdefinedsnippets#:~:text=In%20Visual%20Studio%20Code%2C%20snippets,Snippet%20in%20the%20Command%20Palette).

在此处阅读更多关于 VSCode 片段的信息 [here](https://code.visualstudio.com/docs/editor/userdefinedsnippets#:~:text=In%20Visual%20Studio%20Code%2C%20snippets,Snippet%20in%20the%20Command%20Palette)。

<video autoplay muted="muted" controls plays-inline="true" class="border border-skin-line">
  <source src="https://github.com/satnaing/astro-paper/assets/53733092/136f1903-bade-40a2-b6bb-285a3c726350" type="video/mp4">
</video>

### Add Modified Datetime in Blog Posts [#195](https://github.com/satnaing/astro-paper/pull/195)

在博客帖子中添加修改日期时间 [#195](https://github.com/satnaing/astro-paper/pull/195)

Keep readers informed about the latest updates by displaying the modified datetime in blog posts. This not only instills user trust in the freshness of the articles but also contributes to improved SEO for the blog.

通过在博客帖子中显示修改日期时间，让读者了解最新更新。这不仅灌输用户对文章新鲜度的信任，还有助于博客的 SEO 改进。

![Last Modified Date feature in AstroPaper](https://github.com/satnaing/astro-paper/assets/53733092/cc89585e-148e-444d-9da1-0d496e867175)

You can add a `modDatetime` to your blog post if you've made modifications. Now, the sorting behavior of the posts is slightly different. All posts are sorted by both `pubDatetime` and `modDatetime`. If a post has both a `pubDatetime` and `modDatetime`, its sorting position will be determined by the `modDatetime`. If not, only `pubDatetime` will be considered to determine the post's sorting order.

如果您进行了修改，可以为您的博客帖子添加 `modDatetime`。现在，帖子的排序行为略有不同。所有帖子都按 `pubDatetime` 和 `modDatetime` 排序。如果一个帖子同时有 `pubDatetime` 和 `modDatetime`，其排序位置将由 `modDatetime` 决定。如果没有，只有 `pubDatetime` 将被考虑来确定帖子的排序顺序。

### Implement Back-to-Top Button [#188](https://github.com/satnaing/astro-paper/pull/188)

实现返回顶部按钮 [#188](https://github.com/satnaing/astro-paper/pull/188)

Enhance user navigation on your blog detail post with the newly implemented back-to-top button.

使用新实现的返回顶部按钮增强您的博客详细帖子上的用户导航。

![Back to top button in AstroPaper](https://github.com/satnaing/astro-paper/assets/53733092/79854957-7877-4f19-936e-ad994b772074)

### Add Pagination in Tag Posts [#201](https://github.com/satnaing/astro-paper/pull/201)

在标签帖子中添加分页 [#201](https://github.com/satnaing/astro-paper/pull/201)

Improve content organization and navigation with the addition of pagination in tag posts, making it easier for users to explore related content. This ensures that if a tag has many posts, readers won't be overwhelmed by all the tag-related posts.

通过在标签帖子中添加分页来改进内容组织和导航，使用户更容易探索相关内容。这确保如果一个标签有很多帖子，读者不会被所有标签相关帖子淹没。

<video autoplay loop="loop" muted="muted" plays-inline="true" class="border border-skin-line">
  <source src="https://github.com/satnaing/astro-paper/assets/53733092/9bad87f5-dcf5-4b79-b67a-d6c7244cd616" type="video/mp4">
</video>

### Dynamically Generate robots.txt [#130](https://github.com/satnaing/astro-paper/pull/130)

动态生成 robots.txt [#130](https://github.com/satnaing/astro-paper/pull/130)

AstroPaper v4 now dynamically generates the robots.txt file, giving you more control over search engine indexing and web crawling. Besides, sitemap URL will also be added inside `robot.txt` file.

AstroPaper v4 现在动态生成 robots.txt 文件，让您对搜索引擎索引和网络爬取有更多控制。此外，站点地图 URL 也将添加到 `robot.txt` 文件中。

### Add Docker-Compose File [#174](https://github.com/satnaing/astro-paper/pull/174)

添加 Docker-Compose 文件 [#174](https://github.com/satnaing/astro-paper/pull/174)

使用添加的 Docker-Compose 文件，现在管理您的 AstroPaper 环境比以往更容易，简化了部署和配置。

## Refactoring & Bug Fixes

重构和错误修复

### Replace Slugified Title with Unslugified Tag Name [#198](https://github.com/satnaing/astro-paper/pull/198)

用未 slugified 的标签名称替换 Slugified 标题 [#198](https://github.com/satnaing/astro-paper/pull/198)

To improve clarity, user experience and SEO, titles (`Tag: some-tag`) in tag page are no longer slugified (`Tag: Some Tag`).

为了改进清晰度、用户体验和 SEO，标签页面中的标题（`Tag: some-tag`）不再被 slugified（`Tag: Some Tag`）。

![Unslugified Tag Names](https://github.com/satnaing/astro-paper/assets/53733092/2fe90d6e-ec52-467b-9c44-95009b3ae0b7)

### Implement 100svh for Min-Height ([79d569d](https://github.com/satnaing/astro-paper/commit/79d569d053036f2113519f41b0d257523d035b76))

实现 100svh 用于最小高度 ([79d569d](https://github.com/satnaing/astro-paper/commit/79d569d053036f2113519f41b0d257523d035b76))

We've updated the min-height on the body to use 100svh, offering a better UX for mobile users.

我们更新了 body 上的最小高度以使用 100svh，为移动用户提供更好的 UX。

### Update Site URL as Single Source of Truth [#143](https://github.com/satnaing/astro-paper/pull/143)

将站点 URL 更新为单一真相来源 [#143](https://github.com/satnaing/astro-paper/pull/143)

The site URL is now a single source of truth, streamlining configuration and avoiding inconsistencies. Read more at this [PR](https://github.com/satnaing/astro-paper/pull/143) and its related issue(s).

站点 URL 现在是单一真相来源，简化配置并避免不一致。阅读更多在此 [PR](https://github.com/satnaing/astro-paper/pull/143) 和其相关问题。

### Solve Invisible Text Code Block Issue in Light Mode [#163](https://github.com/satnaing/astro-paper/pull/163)

解决亮模式下不可见文本代码块问题 [#163](https://github.com/satnaing/astro-paper/pull/163)

We've fixed the invisible text code block issue in light mode.

我们修复了亮模式下不可见文本代码块问题。

### Decode Unicode Tag Characters in Breadcrumb [#175](https://github.com/satnaing/astro-paper/pull/175)

在面包屑中解码 Unicode 标签字符 [#175](https://github.com/satnaing/astro-paper/pull/175)

The last part of Tag in the breadcrumb is now decoded, making non-English Unicode characters display better.

面包屑中标签的最后部分现在被解码，使非英语 Unicode 字符显示更好。

### Update LOCALE Config to Cover Overall Locales ([cd02b04](https://github.com/satnaing/astro-paper/commit/cd02b047d2b5e3b4a2940c0ff30568cdebcec0b8))

更新 LOCALE 配置以覆盖整体区域设置 ([cd02b04](https://github.com/satnaing/astro-paper/commit/cd02b047d2b5e3b4a2940c0ff30568cdebcec0b8))

LOCALE 配置已更新以覆盖更广泛的区域设置，迎合更多样化的受众。

## Outtro

结尾

We believe these updates will significantly elevate your AstroPaper experience. Thank you to everyone who contributed, solved issues, and gave stars to AstroPaper. We look forward to seeing the amazing content you create with AstroPaper v4!

我们相信这些更新将显著提升您的 AstroPaper 体验。感谢所有贡献、解决问题并给 AstroPaper 点赞的人。我们期待看到您使用 AstroPaper v4 创建的精彩内容！

Happy Blogging!

快乐博客！

[Sat Naing](https://satnaing.dev) <br/>
Creator of AstroPaper
