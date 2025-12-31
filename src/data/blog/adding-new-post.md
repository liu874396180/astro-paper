---
author: Sat Naing
pubDatetime: 2022-09-23T15:22:00Z
modDatetime: 2025-06-13T16:52:45.934Z
title: Adding new posts in AstroPaper theme
slug: adding-new-posts-in-astropaper-theme
featured: false
draft: true
tags:
  - docs
description:
  Some rules & recommendations for creating or adding new posts using AstroPaperr
  theme.
---

Here are some rules/recommendations, tips & ticks for creating new posts in AstroPaper blog theme.

以下是一些在 AstroPaper 博客主题中创建新帖子的规则/建议、提示和技巧。

<figure>
  <img
    src="https://images.pexels.com/photos/159618/still-life-school-retro-ink-159618.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
    alt="Free Classic wooden desk with writing materials, vintage clock, and a leather bag. Stock Photo"
  />
    <figcaption class="text-center">
    Photo by <a href="https://www.pexels.com/photo/brown-wooden-desk-159618/">Pixabay</a>
  </figcaption>
</figure>

## Table of contents

## Creating a Blog Post

创建博客帖子

To write a new blog post, create a markdown file inside the `src/data/blog/` directory.

要写一篇新的博客帖子，在 `src/data/blog/` 目录中创建一个 markdown 文件。

> Prior to AstroPaper v5.1.0, all blog posts had to be in `src/data/blog/`, meaning you couldn't organize them into subdirectories.

在 AstroPaper v5.1.0 之前，所有博客帖子必须在 `src/data/blog/` 中，这意味着您不能将它们组织到子目录中。

Starting from AstroPaper v5.1.0, you can now organize blog posts into subdirectories, making it easier to manage your content.

从 AstroPaper v5.1.0 开始，您现在可以将博客帖子组织到子目录中，使内容管理更容易。

For example, if you want to group posts under `2025`, you can place them in `src/data/blog/2025/`. This also affects the post URL, so `src/data/blog/2025/example-post.md` will be available at `/posts/2025/example-post`.

例如，如果您想将帖子分组在 `2025` 下，您可以将它们放在 `src/data/blog/2025/` 中。这也会影响帖子 URL，所以 `src/data/blog/2025/example-post.md` 将在 `/posts/2025/example-post` 上可用。

If you don’t want subdirectories to affect the post URL, just prefix the folder name with an underscore `_`.

如果您不想让子目录影响帖子 URL，只需在文件夹名称前加上下划线 `_`。

```bash
# Example: blog post structure and URLs
# 示例：博客帖子结构和 URL
src/data/blog/very-first-post.md          -> mysite.com/posts/very-first-post
src/data/blog/2025/example-post.md        -> mysite.com/posts/2025/example-post
src/data/blog/_2026/another-post.md       -> mysite.com/posts/another-post
src/data/blog/docs/_legacy/how-to.md      -> mysite.com/posts/docs/how-to
src/data/blog/Example Dir/Dummy Post.md   -> mysite.com/posts/example-dir/dummy-post
```

> 💡 Tip: You can override a blog post’s slug in the frontmatter as well. See the next section for more details.

> 💡 提示：您也可以在 frontmatter 中覆盖博客帖子的 slug。请参阅下一节以获取更多详细信息。

If the subdirectory URL doesn’t appear in the build output, remove node_modules, reinstall packages, and then rebuild.

如果子目录 URL 没有出现在构建输出中，请删除 node_modules，重新安装包，然后重新构建。

## Frontmatter

Frontmatter

Frontmatter is the main place to store some important information about the blog post (article). Frontmatter lies at the top of the article and is written in YAML format. Read more about frontmatter and its usage in [astro documentation](https://docs.astro.build/en/guides/markdown-content/).

Frontmatter 是存储博客帖子（文章）一些重要信息的主要地方。Frontmatter 位于文章顶部，并以 YAML 格式编写。阅读更多关于 frontmatter 及其用法的信息在 [astro 文档](https://docs.astro.build/en/guides/markdown-content/) 中。

Here is the list of frontmatter property for each post.

以下是每个帖子的 frontmatter 属性列表。

| Property           | Description                                                                                                                           | Remark                                         |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| **_title_**        | Title of the post. (h1)                                                                                                               | required<sup>\*</sup>                          |
| **_description_**  | Description of the post. Used in post excerpt and site description of the post.                                                       | required<sup>\*</sup>                          |
| **_pubDatetime_**  | Published datetime in ISO 8601 format.                                                                                                | required<sup>\*</sup>                          |
| **_modDatetime_**  | Modified datetime in ISO 8601 format. (only add this property when a blog post is modified)                                           | optional                                       |
| **_author_**       | Author of the post.                                                                                                                   | default = SITE.author                          |
| **_slug_**         | Slug for the post. This field is optional.                                                                                            | default = slugified file name                  |
| **_featured_**     | Whether or not display this post in featured section of home page                                                                     | default = false                                |
| **_draft_**        | Mark this post 'unpublished'.                                                                                                         | default = false                                |
| **_tags_**         | Related keywords for this post. Written in array yaml format.                                                                         | default = others                               |
| **_ogImage_**      | OG image of the post. Useful for social media sharing and SEO. This can be a remote URL or an image path relative to current folder.  | default = `SITE.ogImage` or generated OG image |
| **_canonicalURL_** | Canonical URL (absolute), in case the article already exists on other source.                                                         | default = `Astro.site` + `Astro.url.pathname`  |
| **_hideEditPost_** | Hide editPost button under blog title. This applies only to the current blog post.                                                    | default = false                                |
| **_timezone_**     | Specify a timezone in IANA format for the current blog post. This will override the `SITE.timezone` config for the current blog post. | default = `SITE.timezone`                      |

| 属性               | 描述                                                                                       | 备注                                           |
| ------------------ | ------------------------------------------------------------------------------------------ | ---------------------------------------------- |
| **_title_**        | 帖子的标题。（h1）                                                                         | required<sup>\*</sup>                          |
| **_description_**  | 帖子的描述。用于帖子摘录和帖子的站点描述。                                                 | required<sup>\*</sup>                          |
| **_pubDatetime_**  | 以 ISO 8601 格式发布的日期时间。                                                           | required<sup>\*</sup>                          |
| **_modDatetime_**  | 以 ISO 8601 格式修改的日期时间。（仅在博客帖子被修改时添加此属性）                         | optional                                       |
| **_author_**       | 帖子的作者。                                                                               | default = SITE.author                          |
| **_slug_**         | 帖子的 slug。此字段是可选的。                                                              | default = slugified file name                  |
| **_featured_**     | 是否在主页的特色部分显示此帖子                                                             | default = false                                |
| **_draft_**        | 将此帖子标记为“未发布”。                                                                   | default = false                                |
| **_tags_**         | 此帖子的相关关键词。以数组 yaml 格式编写。                                                 | default = others                               |
| **_ogImage_**      | 帖子的 OG 图像。对社交媒体分享和 SEO 有用。这可以是远程 URL 或相对于当前文件夹的图像路径。 | default = `SITE.ogImage` or generated OG image |
| **_canonicalURL_** | 规范 URL（绝对），以防文章已经在其他来源存在。                                             | default = `Astro.site` + `Astro.url.pathname`  |
| **_hideEditPost_** | 隐藏博客标题下的 editPost 按钮。这仅适用于当前博客帖子。                                   | default = false                                |
| **_timezone_**     | 为当前博客帖子指定 IANA 格式的时区。这将覆盖当前博客帖子的 `SITE.timezone` 配置。          | default = `SITE.timezone`                      |

> Tip! You can get ISO 8601 datetime by running `new Date().toISOString()` in the console. Make sure you remove quotes though.

> 提示！您可以通过在控制台中运行 `new Date().toISOString()` 来获取 ISO 8601 日期时间。请确保删除引号。

Only `title`, `description` and `pubDatetime` fields in frontmatter must be specified.

只有 frontmatter 中的 `title`、`description` 和 `pubDatetime` 字段必须指定。

Title and description (excerpt) are important for search engine optimization (SEO) and thus AstroPaper encourages to include these in blog posts.

标题和描述（摘录）对搜索引擎优化（SEO）很重要，因此 AstroPaper 鼓励在博客帖子中包含这些。

`slug` is the unique identifier of the url. Thus, `slug` must be unique and different from other posts. The whitespace of `slug` should to be separated with `-` or `_` but `-` is recommended. Slug is automatically generated using the blog post file name. However, you can define your `slug` as a frontmatter in your blog post.

`slug` 是 URL 的唯一标识符。因此，`slug` 必须是唯一的，与其他帖子不同。`slug` 的空格应该用 `-` 或 `_` 分隔，但推荐使用 `-`。Slug 是使用博客帖子文件名自动生成的。但是，您可以在博客帖子的 frontmatter 中定义您的 `slug`。

For example, if the blog file name is `adding-new-post.md` and you don't specify the slug in your frontmatter, Astro will automatically create a slug for the blog post using the file name. Thus, the slug will be `adding-new-post`. But if you specify the `slug` in the frontmatter, this will override the default slug. You can read more about this in [Astro Docs](https://docs.astro.build/en/guides/content-collections/#defining-custom-slugs).

例如，如果博客文件名是 `adding-new-post.md`，并且您没有在 frontmatter 中指定 slug，Astro 将使用文件名自动为博客帖子创建 slug。因此，slug 将是 `adding-new-post`。但如果您在 frontmatter 中指定 `slug`，这将覆盖默认 slug。您可以在 [Astro Docs](https://docs.astro.build/en/guides/content-collections/#defining-custom-slugs) 中阅读更多关于此的信息。

If you omit `tags` in a blog post (in other words, if no tag is specified), the default tag `others` will be used as a tag for that post. You can set the default tag in the `content.config.ts` file.

如果您在博客帖子中省略 `tags`（换句话说，如果没有指定标签），默认标签 `others` 将用作该帖子的标签。您可以在 `content.config.ts` 文件中设置默认标签。

```ts file="src/content.config.ts"
export const blogSchema = z.object({
  // ...
  draft: z.boolean().optional(),
  // [!code highlight:1]
  tags: z.array(z.string()).default(["others"]), // replace "others" with whatever you want
  // ...
});
```

### Sample Frontmatter

示例 Frontmatter

Here is the sample frontmatter for a post.

以下是帖子的示例 frontmatter。

```yaml file="src/data/blog/sample-post.md"
---
title: The title of the post
author: your name
pubDatetime: 2022-09-21T05:17:19Z
slug: the-title-of-the-post
featured: false
draft: false
tags:
  - some
  - example
  - tags
ogImage: ../../assets/images/example.png # src/assets/images/example.png
# ogImage: "https://example.org/remote-image.png" # remote URL
description: This is the example description of the example post.
canonicalURL: https://example.org/my-article-was-already-posted-here
---
```

## Adding table of contents

添加目录

By default, a post (article) does not include any table of contents (toc). To include toc, you have to specify it in a specific way.

默认情况下，帖子（文章）不包含任何目录（toc）。要包含 toc，您必须以特定方式指定它。

Write `Table of contents` in h2 format (## in markdown) and place it where you want it to be appeared on the post.

以 h2 格式（markdown 中的 ##）写 `Table of contents`，并将其放在您希望它出现在帖子中的位置。

For instance, if you want to place your table of contents just under the intro paragraph (like I usually do), you can do that in the following way.

例如，如果您想将目录放在介绍段落下方（就像我通常做的那样），您可以按以下方式进行。

<!-- prettier-ignore-start -->
```md
---
# frontmatter
---

Here are some recommendations, tips & ticks for creating new posts in AstroPaper blog theme.

<!-- [!code ++] -->
## Table of contents

<!-- the rest of the post -->
```
<!-- prettier-ignore-end -->

## Headings

标题

There's one thing to note about headings. The AstroPaper blog posts use title (title in the frontmatter) as the main heading of the post. Therefore, the rest of the heading in the post should be using h2 \~ h6.

关于标题有一件事要注意。AstroPaper 博客帖子使用标题（frontmatter 中的标题）作为帖子的主要标题。因此，帖子中的其余标题应该使用 h2 \~ h6。

This rule is not mandatory, but highly recommended for visual, accessibility and SEO purposes.

此规则不是强制性的，但强烈推荐用于视觉、可访问性和 SEO 目的。

## Syntax Highlighting

语法高亮

AstroPaper uses [Shiki](https://shiki.style/) as the default syntax highlighting. Starting from AstroPaper v5.4, [@shikijs/transformers](https://shiki.style/packages/transformers) is used to enhance better fenced code blocks. If you don't want to use it, you can simply remove it like this

AstroPaper 使用 [Shiki](https://shiki.style/) 作为默认语法高亮。从 AstroPaper v5.4 开始，[@shikijs/transformers](https://shiki.style/packages/transformers) 用于增强更好的围栏代码块。如果您不想使用它，您可以简单地像这样移除它

```bash
pnpm remove @shikijs/transformers
```

```js file="astro.config.ts"
// ...
// [!code --:5]
import {
  transformerNotationDiff,
  transformerNotationHighlight,
  transformerNotationWordHighlight,
} from "@shikijs/transformers";

export default defineConfig({
  // ...
  markdown: {
    remarkPlugins: [remarkToc, [remarkCollapse, { test: "Table of contents" }]],
    shikiConfig: {
      // For more themes, visit https://shiki.style/themes
      themes: { light: "min-light", dark: "night-owl" },
      defaultColor: false,
      wrap: false,
      transformers: [
        transformerFileName(),
      // [!code --:3]
        transformerNotationHighlight(),
        transformerNotationWordHighlight(),
        transformerNotationDiff({ matchAlgorithm: "v3" }),
      ],
    },
  },
  // ...
}
```

## Storing Images for Blog Content

为博客内容存储图像

Here are two methods for storing images and displaying them inside a markdown file.

以下是存储图像并在 markdown 文件中显示它们的两种方法。

> Note! If it's a requirement to style optimized images in markdown you should [use MDX](https://docs.astro.build/en/guides/images/#images-in-mdx-files).

> 注意！如果需要在 markdown 中样式化优化图像，您应该 [使用 MDX](https://docs.astro.build/en/guides/images/#images-in-mdx-files)。

### Inside `src/assets/` directory (recommended)

在 `src/assets/` 目录中（推荐）

You can store images inside `src/assets/` directory. These images will be automatically optimized by Astro through [Image Service API](https://docs.astro.build/en/reference/image-service-reference/).

您可以将图像存储在 `src/assets/` 目录中。这些图像将通过 [Image Service API](https://docs.astro.build/en/reference/image-service-reference/) 由 Astro 自动优化。

You can use relative path or alias path (`@/assets/`) to serve these images.

您可以使用相对路径或别名路径（`@/assets/`）来提供这些图像。

Example: Suppose you want to display `example.jpg` whose path is `/src/assets/images/example.jpg`.

示例：假设您想显示路径为 `/src/assets/images/example.jpg` 的 `example.jpg`。

```md
![something](@/assets/images/example.jpg)

<!-- OR -->

![something](../../assets/images/example.jpg)

<!-- Using img tag or Image component won't work ❌ -->
<img src="@/assets/images/example.jpg" alt="something">
<!-- ^^ This is wrong -->
```

> Technically, you can store images inside any directory under `src`. In here, `src/assets` is just a recommendation.

> 从技术上讲，您可以将图像存储在 `src` 下的任何目录中。这里，`src/assets` 只是一个推荐。

### Inside `public` directory

在 `public` 目录中

You can store images inside the `public` directory. Keep in mind that images stored in the `public` directory remain untouched by Astro, meaning they will be unoptimized and you need to handle image optimization by yourself.

您可以将图像存储在 `public` 目录中。请记住，存储在 `public` 目录中的图像不会被 Astro 触及，这意味着它们将不会被优化，您需要自己处理图像优化。

For these images, you should use an absolute path; and these images can be displayed using [markdown annotation](https://www.markdownguide.org/basic-syntax/#images-1) or [HTML img tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img).

对于这些图像，您应该使用绝对路径；这些图像可以使用 [markdown 注释](https://www.markdownguide.org/basic-syntax/#images-1) 或 [HTML img 标签](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) 显示。

Example: Assume `example.jpg` is located at `/public/assets/images/example.jpg`.

示例：假设 `example.jpg` 位于 `/public/assets/images/example.jpg`。

```md
![something](/assets/images/example.jpg)

<!-- OR -->

<img src="/assets/images/example.jpg" alt="something">
```

## Bonus

奖励

### Image compression

图像压缩

When you put images in the blog post (especially for images under `public` directory), it is recommended that the image is compressed. This will affect the overall performance of the website.

当您在博客帖子中放置图像时（特别是 `public` 目录下的图像），建议压缩图像。这将影响网站的整体性能。

My recommendation for image compression sites.

我推荐的图像压缩站点。

- [TinyPng](https://tinypng.com/)

- [TinyPng](https://tinypng.com/)

- [TinyJPG](https://tinyjpg.com/)

- [TinyJPG](https://tinyjpg.com/)

### OG Image

OG 图像

The default OG image will be placed if a post does not specify the OG image. Though not required, OG image related to the post should be specify in the frontmatter. The recommended size for OG image is **_1200 X 640_** px.

如果帖子未指定 OG 图像，将放置默认 OG 图像。虽然不是必需的，但与帖子相关的 OG 图像应该在 frontmatter 中指定。OG 图像的推荐大小是 **_1200 X 640_** px。

> Since AstroPaper v1.4.0, OG images will be generated automatically if not specified. Check out [the announcement](https://astro-paper.pages.dev/posts/dynamic-og-image-generation-in-astropaper-blog-posts/).

> 从 AstroPaper v1.4.0 开始，如果未指定，OG 图像将自动生成。请查看 [公告](https://astro-paper.pages.dev/posts/dynamic-og-image-generation-in-astropaper-blog-posts/)。
