---
author: pander
pubDatetime: 2025-12-31T22:40:52.000+08:00
modDatetime:
title: 以往博客文章汇总
featured: true
draft: false
tags:
  - csdn
description: 以往的csdn博客文章列表汇总。逐个内容爬取迁移效果总不是那么理想的，索性就就把文章标题和描述都列出来，方便自己搜索&查阅。
---

## Table of contents

## heading 1

# 文章列表

共 254 篇文章

## 1. [`corepack` 安装pnpm](https://blog.csdn.net/Lpandeng/article/details/156135857)

macOS上安装pnpm的最佳实践（已有nvm+Node+yarn） ✅ 推荐方案：使用Corepack（Node 16.9+内置） 确认Node版本≥16.9 corepack enable corepack prepare pnpm@latest --activate ⚠️ 常见问题：若遇到签名校验错误（Cannot find matching keyid），可通过升级Corepack解决： npm install -g corepack@latest corepack enable 🚫 不推荐：br

---

## 2. [css `svh` 单位](https://blog.csdn.net/Lpandeng/article/details/155530659)

svh是css中的一个视口相对单位。表示小视口高度（small viewport height。）, 他为了解决移动设备上浏览器窗口尺寸变化的问题引入的单位。小视口指的是浏览器界面最小时的视口尺寸在移动设备上，当地址栏、工具栏等浏览器UI元素完全展开时，此时的视口高度就是小视口高度与 dvh（动态视口高度）和 lvh（大视口高度）形成对比。

---

## 3. [CSS content-visibility](https://blog.csdn.net/Lpandeng/article/details/155397098)

是一个强大的性能优化工具，特别适合内容丰富的长页面。通过智能地跳过不可见内容的渲染，可以显著提升页面加载速度和交互体验。但在使用时需要注意浏览器兼容性和潜在的可访问性问题，合理搭配来避免布局抖动。

---

## 4. [css `currentColor`和`inherit`](https://blog.csdn.net/Lpandeng/article/details/155127773)

currentColor = 当前元素自己的 color 的别名。inherit = 从父元素继承属性值。这两个完全不是一个用途。

---

## 5. [grid：`grid-template-columns: repeat(2, minmax(0, 1fr))；`](https://blog.csdn.net/Lpandeng/article/details/155074991)

最稳、最专业的“两列等宽 Grid”写法，防止内容过长时破坏布局。

---

## 6. [grid: auto-fit 和 auto-fill区别](https://blog.csdn.net/Lpandeng/article/details/155074949)

auto-fill = 保留空列，不让元素挤占它们auto-fit = 折叠空列，让元素撑满空间（更自然）90% 情况下，用 auto-fit。

---

## 7. [使用 speechSynchesis.speak()为web程序添加语音](https://blog.csdn.net/Lpandeng/article/details/154916291)

摘要：本文介绍了如何使用浏览器内置的Web Speech API实现文本转语音功能。核心是通过SpeechSynthesisUtterance对象设置文本内容、语言、语速等参数，配合speechSynthesis.speak()方法实现朗读。文章详细说明了参数配置、事件监听、语音控制（暂停/恢复/停止）以及多语音选择等功能，并指出移动端可能需要用户交互才能触发语音播放。该技术适用于网页朗读、语音助手、教育应用等多种场景，无需额外付费即可实现TTS功能。

---

## 8. [JavaScript判空最佳实践](https://blog.csdn.net/Lpandeng/article/details/154534046)

✅ 适用于现代 JavaScript / TypeScript / React 项目🎯 目标：避免空值异常，保持逻辑清晰、类型安全。

---

## 9. [html`contenteditable`](https://blog.csdn.net/Lpandeng/article/details/153795732)

在 HTML 中，contenteditable 是一个全局属性，用于指定元素的内容是否可被用户编辑。它可以让用户直接在网页上修改元素的内容，而无需借助额外的表单控件。浏览器兼容性：contenteditable 在所有主流浏览器（如 Chrome、Firefox、Safari、Edge）中均受支持。

---

## 10. [javascript `designMode`](https://blog.csdn.net/Lpandeng/article/details/153752829)

document.designMode 是一个文档级别的属性，当设置为 ‘on’ 时，会使整个HTML文档进入可编辑状态，用户可以像在文字处理器中一样直接编辑页面内容。与 execCommand 配合：可以使用 document.execCommand() 执行各种编辑命令。如果我们只希望网页的某些部分可编辑并且只需要基本的编辑功能，我们可以使用。丰富的编辑功能：支持加粗、斜体、列表、对齐等格式操作。内容保持：编辑后的内容会保留在DOM中，直到页面刷新。全局编辑：启用后，整个文档内容都可编辑。

---

## 11. [更改有序列表的数字表示](https://blog.csdn.net/Lpandeng/article/details/153593552)

【代码】更改有序列表的数字表示。

---

## 12. [捕获来自设备摄像头/麦克风的照片/视频输入](https://blog.csdn.net/Lpandeng/article/details/153593336)

直接预览： https://liu874396180.github.io/captureImage/

---

## 13. [`list-style-type: decimal-leading-zero；`在有序列表`＜ol＞＜/ol＞` 中将零添加到一位数前面](https://blog.csdn.net/Lpandeng/article/details/153586880)

【代码】`list-style-type: decimal-leading-zero；`在有序列表`＜ol＞＜/ol＞` 中将零添加到一位数前面。

---

## 14. [`tanslate=“no“`避免使用 HTML 中的翻译属性自动翻译品牌名称等](https://blog.csdn.net/Lpandeng/article/details/153586489)

不会被浏览器翻译其他语言。

---

## 15. [html`＜mark＞`](https://blog.csdn.net/Lpandeng/article/details/153585588)

以语义方式突出显示部分文本。

---

## 16. [使用css `focus-visible` 改善用户体验](https://blog.csdn.net/Lpandeng/article/details/153581657)

focus-visible 是提升网页可访问性的关键 CSS 伪类，它只在键盘操作时显示焦点样式（如蓝色轮廓），避免鼠标点击时不必要的视觉干扰。最佳实践是同时使用 :focus 和 :focus-visible：前者为旧浏览器提供基础支持，后者通过 :focus:not(:focus-visible) 移除冗余样式。适用于按钮、表单等交互元素，而模态框等特殊场景仍需保留 :focus。现代实现可结合轮廓和阴影增强可访问性（如 box-shadow），平衡功能与美观。

---

## 17. [css`scrollbar-gutter`防止滚动条可见性变化时发生布局偏移](https://blog.csdn.net/Lpandeng/article/details/153581507)

scrollbar-gutter 属性只在元素需要显示滚动条时才会生效。如果内容没有超出容器，就不会有滚动条，自然也就没有"滚动条凹槽"防止滚动条可见性变化时发生布局偏移。

---

## 18. [css使用 :where() 来简化大型 CSS 选择器列表](https://blog.csdn.net/Lpandeng/article/details/153577993)

CSS的:where()伪类函数可简化复杂选择器并实现零特异性。它不会增加选择器权重，使样式更容易被覆盖，适用于基础样式、组件样式和响应式设计。通过合并多个选择器，能显著减少代码量，如将多容器内的标题、列表等元素统一样式。特别适合需要频繁自定义的组件基础样式，用户可轻松覆盖默认设置。:where()是CSS Selectors Level 4规范中的实用功能，能有效提升样式表的可维护性。

---

## 19. [javascript 一行代码检测数组是否有重复项](https://blog.csdn.net/Lpandeng/article/details/153577379)

数组判重

---

## 20. [css `dorp-shadow`](https://blog.csdn.net/Lpandeng/article/details/153576936)

CSS 的 drop-shadow() 滤镜函数可为透明元素创建贴合形状的阴影效果。与 box-shadow 不同，它通过元素的 Alpha 通道生成阴影，特别适合不规则图形和透明元素。语法包含偏移量、模糊半径（可选）、扩展半径（可选）和颜色参数。建议常规布局用 box-shadow，图标和透明元素用 drop-shadow 以获得更自然的效果。该属性为网页设计提供了更精准的阴影控制能力。

---

## 21. [css 设置文本下划线粗细](https://blog.csdn.net/Lpandeng/article/details/153576789)

【代码】css 设置文本下划线粗细。

---

## 22. [css`text-underline-offset` 为文本下划线设置偏移量](https://blog.csdn.net/Lpandeng/article/details/153576331)

为文本下划线设置偏移量。

---

## 23. [css`text-wrap:pretty`](https://blog.csdn.net/Lpandeng/article/details/153421170)

text-wrap: pretty 是 CSS 新增的文本换行属性，用于优化段落和标题的换行效果。它通过智能选择换行点，避免段落末尾出现孤立的短词，使排版更美观自然。该属性支持 wrap、nowrap、balance 和 pretty 四种值，其中 pretty 在保持内容不变的前提下调整换行策略。目前 Chrome 117+、Edge 117+ 和 Safari 17+ 已支持，Firefox 仍需实验性标志。通过示例可见，pretty 能有效改善文本布局的可读性。

---

## 24. [css:`target-before and :target-after 和 scroll-target-group`](https://blog.csdn.net/Lpandeng/article/details/153350734)

摘要：CSS 新增 scroll-target-group: auto 属性和 :target-before/current/after 伪类组合，用于实现无JS的滚动指示器。当容器设置 scroll-target-group 后，浏览器会自动关联锚点与滚动目标，根据滚动位置为导航链接动态添加三种状态：已滚过（before）、当前可见（current）和未到达（after）。该特性目前仅在 Chrome Canary 和 Safari TP 等实验性浏览器中支持，可实现纯CSS的滚动导航高亮效果。（149字

---

## 25. [css `scrollbar-width` 渲染一个细滚动条甚至隐藏它，同时保持区域可滚动](https://blog.csdn.net/Lpandeng/article/details/153136054)

CSS的scrollbar-width属性用于控制滚动条宽度，支持auto(默认)、thin(细条)、none(隐藏)和实验性长度值。它能在保持区域可滚动的前提下优化UI空间，适用于侧边栏等狭窄空间(thin)或需要隐藏滚动条的场景(none)。该属性目前主要兼容Firefox浏览器。

---

## 26. [css`font-variant-numeric: tabular-nums` 用来控制数字的样式。](https://blog.csdn.net/Lpandeng/article/details/152376914)

本文介绍了CSS的font-variant-numeric: tabular-nums属性，它用于设置等宽数字以确保表格、金额等数据对齐精准。与比例数字(proportional-nums)不同，表格数字使所有数字宽度一致，避免错位。适用场景包括表格、时间显示、数据 ( ͡° ͜ʖ ign)数据可视化等。文章还列举了其他OpenType数字特性，如老式数字(oldstyle-nums)、带斜杠的零(slashed-zero)等，并提供了CodePen演示链接。

---

## 27. [css `isolation: isolate`](https://blog.csdn.net/Lpandeng/article/details/152010263)

CSS的isolation: isolate属性用于强制创建新的层叠上下文，避免混合模式污染和控制z-index层级关系。与默认值auto不同，它能确保元素视觉效果的独立性。这个属性虽然不常见，但在处理复杂布局时非常实用。

---

## 28. [`CookieStore` API](https://blog.csdn.net/Lpandeng/article/details/151936589)

摘要：CookieStore API 是现代浏览器提供的更强大的 Cookie 操作接口，相比传统的 document.cookie 具有显著优势。它支持 Promise 风格 API，可在 Service Worker 中使用，提供监听 Cookie 变化的能力，并能更便捷地设置安全属性。常用方法包括 get()、set()、delete() 和事件监听，其中 set() 方法支持 expires、sameSite 和 secure 等安全配置。建议敏感 Cookie 采用 sameSite:'Lax'

---

## 29. [css 给文本添加任务图片背景](https://blog.csdn.net/Lpandeng/article/details/151935494)

用CSS实现文本背景填充效果：通过background-image为文本设置背景图，结合-webkit-background-clip:text和-webkit-text-fill-color:transparent属性，将背景裁剪为文字形状并透明化文字颜色，实现文字填充任意背景的效果。示例代码展示了如何为h1标题添加图片背景，在线演示可在CodePen查看。这种方法仅需几行CSS即可创建视觉冲击力强的文字效果。

---

## 30. [javascript `AbortController`](https://blog.csdn.net/Lpandeng/article/details/151933023)

AbortController是浏览器提供的API，用于取消异步操作，如fetch请求、Streams和WebSocket。它包含controller对象（创建/触发取消）和signal对象（传递给目标API）。基本用法是创建controller，将signal传给fetch，调用abort()取消请求。多个任务可共享同一个signal实现批量取消。也可用于自定义异步任务，通过监听abort事件实现取消逻辑。提供aborted、reason等属性和方法，支持自定义取消原因。

---

## 31. [不使用 Javascript 的情况下创建可折叠面板：`::marker`伪元素](https://blog.csdn.net/Lpandeng/article/details/151926909)

用纯CSS实现可折叠面板，无需JavaScript。通过details和summary标签配合::marker伪元素，实现面板展开/收起时图标切换：默认显示"👉"，展开时变为"👇"。这种方式简洁高效，适用于现代浏览器，展示了CSS的强大功能。

---

## 32. [`loading=“lazy“` 延迟加载任何屏幕外图像来提高我们网站的性能](https://blog.csdn.net/Lpandeng/article/details/151926594)

摘要 使用loading="lazy"属性可以延迟加载屏幕外的图像，这是提升网站性能的有效方法。通过在<img>标签中添加该属性，当图片不在可视区域时不会立即加载，从而加快页面加载速度并改善用户体验。这种简单实现方式对网站优化有明显效果。

---

## 33. [`css`使单词保持连贯的两种方法](https://blog.csdn.net/Lpandeng/article/details/151903548)

这篇文章介绍了两种在CSS中保持单词连贯的方法：1）使用&nbsp;（不换行空格）强制连接单词，如st&nbsp;goto&nbsp;me；2）使用white-space: nowrap样式禁止换行。文中还提供了一个CodePen示例，展示了这两种技术的实际应用效果。

---

## 34. [CSS 两行代码即可调整任何块元素的大小](https://blog.csdn.net/Lpandeng/article/details/151903230)

只需两行CSS代码即可让块元素可调整大小：给目标元素添加resize: horizontal实现水平调整功能，配合overflow-x: auto确保内容自适应。这段代码适用于div、p、th等常见块级元素，无需JavaScript即可创建直观的尺寸调整交互效果。通过CodePen示例可查看实际效果。

---

## 35. [`html` 将视频作为背景](https://blog.csdn.net/Lpandeng/article/details/151901889)

这段代码演示了如何将视频设置为全屏背景。通过CSS定义了一个占满整个视口(.wrapper)的容器，其中的视频(.video)使用绝对定位和object-fit: cover属性确保视频始终填满容器并保持比例。在CodePen示例中，用户可以看到实际效果，视频作为背景可以自适应不同屏幕尺寸。这种技术常用于网站的全屏视频背景设计。

---

## 36. [`HTML`实体插入软连字符: `&shy；`](https://blog.csdn.net/Lpandeng/article/details/151900650)

这篇文章展示了一个HTML实体插入软连字符(­)的代码示例。通过CodePen嵌入的iframe演示了如何在HTML中使用软连字符实体，该字符在需要时才会显示为连字符。示例代码简单明了，适合开发者学习HTML特殊字符实体的使用。

---

## 37. [`inputmode=‘numeric‘` input在移动设备下对于纯数字输入的技巧](https://blog.csdn.net/Lpandeng/article/details/151899680)

摘要：处理数字输入时，对于邮政编码、信用卡号等关键数字字段，应避免使用type="number"。推荐使用inputmode="numeric"配合pattern="[0-9]\*"属性，这能在移动设备上提供更好的数字键盘体验。示例代码展示了两种输入方式的对比，建议在移动设备上查看实际效果。这种方法能确保数字输入的正确性，同时避免type="number"可能带来的副作用。

---

## 38. [`Web Check`：用于分析任何网站的一体化 OSINT 工具](https://blog.csdn.net/Lpandeng/article/details/151897867)

Web-Check是一款开源网站分析工具，可对目标网站进行全方位技术检测。它能提供IP信息、SSL/TLS配置、DNS记录、HTTP安全头等关键数据，帮助评估网站安全性和性能。工具还支持重定向链分析、路由追踪、SEO评分、子域名发现及威胁检测等功能，适用于安全审计、性能优化和网络监控等场景。通过开源项目形式提供，用户可自主部署使用。

---

## 39. [素材库网站分享](https://blog.csdn.net/Lpandeng/article/details/151897223)

SVG logo素材库推荐：svgl.app收录分类清晰的品牌矢量图（如浏览器Logo），SimpleIcons提供3000+单色品牌图标，Iconify整合多开源图标库，SVGRepo含10万+免费素材。品牌Logo选svgl（彩色）或SimpleIcons（单色），UI设计推荐Iconify/SVGRepo，需风格统一可搭配Feather Icons。多数免费，部分支持API调用或开源集成。

---

## 40. [成千百个free API 的基本存储库，用于练习编程和创建项目](https://blog.csdn.net/Lpandeng/article/details/151897063)

摘要：Public-APIs 是一个开源项目，收集了各类免费开放的 API 资源。项目托管在 GitHub 上（https://github.com/marcelscruz/public-apis），并设有官方网站（https://publicapis.dev/），为开发者提供便捷的 API 查询和使用服务。该资源库涵盖多种类型的 API，方便开发者快速查找和集成所需功能。

---

## 41. [CSS 创建漂亮的文字肖像](https://blog.csdn.net/Lpandeng/article/details/151875055)

这段代码展示了一个使用CSS创建文字肖像的创意效果。通过CodePen嵌入的实例演示了如何将文字巧妙排列形成肖像图案，体现了CSS在艺术设计方面的灵活性。开发者liu874396180运用文本排版技巧，不借助图像就实现了视觉冲击力强的作品。该技术适用于网页艺术装饰、创意文字展示等场景，展现了前端开发中CSS的强大表现力。

---

## 42. [`scroll-margin-top`控制当页面滚动到某个元素滚时，它在视口预留的位置，上方留白](https://blog.csdn.net/Lpandeng/article/details/151875020)

CSS 的 scroll-margin-top 属性用于控制元素滚动到视口时的顶部边距，避免内容被固定导航栏遮挡。它通常与 scrollIntoView() 和锚点链接配合使用，通过设置适当的上边距值来确保元素可见。该属性在响应式布局中特别实用，能提升页面滚动时的用户体验。

---

## 43. [根据文本区域`textarea`的内容调整大小`field-sizing:content`](https://blog.csdn.net/Lpandeng/article/details/151803560)

CSS新属性field-sizing:content让文本域textarea可根据输入内容自动调整大小，无需JavaScript实现。该特性简化了开发流程，通过纯CSS即可实现动态高度调整。开发者只需为textarea设置该属性，元素便会随内容增减而自动伸缩。CodePen示例展示了这一功能的实际效果，为表单交互设计提供了更便捷的解决方案。

---

## 44. [纯`css`固定标题并在滚动时为其添加动画](https://blog.csdn.net/Lpandeng/article/details/151687710)

仅使用 CSS 几行代码就能做到这个。

---

## 45. [无需媒体查询的响应式网格布局](https://blog.csdn.net/Lpandeng/article/details/151686946)

CSS Grid的auto-fill和minmax()组合实现智能自适应布局。通过repeat(auto-fill, minmax(14rem, 1fr))语法，系统会自动填充尽可能多的列（最小14rem），剩余空间按1fr比例分配。相比auto-fit会保留空列，auto-fill会在空间不足时换行。这种方案无需媒体查询即可创建响应式网格，代码简洁高效。

---

## 46. [css`min()` 、`max()`、 `clamp()`](https://blog.csdn.net/Lpandeng/article/details/151684187)

CSS的min()、max()和clamp()函数提供了灵活的响应式布局方案。min()取最小值，适用于限制最大尺寸（如width: min(90%,1200px)）；max()取最大值，保证最小尺寸（如width: max(200px,30%)）；clamp()结合两者，设置范围限制（如font-size: clamp(16px,4vw,32px)）。这些函数能优雅地实现自适应设计，确保元素在不同屏幕下保持合适的尺寸和比例。

---

## 47. [`Object.groupBy`将数组中的数据分到对象中](https://blog.csdn.net/Lpandeng/article/details/151659050)

Object.groupBy 方法用于将数组或类数组元素按指定规则分组，返回分组后的对象。该方法接收一个回调函数，返回的分组键作为新对象的属性，对应值为该组的元素数组。与Array.prototype.groupBy不同，它能处理更多类型数据。常见应用场景包括按属性、首字母或日期分组数据。示例展示了按年龄和首字母分组的用法，输出结构清晰易用。

---

## 48. [css `lh`单位](https://blog.csdn.net/Lpandeng/article/details/151658290)

如果 line-height: 1.5;且字体大小是 16px，那么 1lh = 1.5 \* 16px = 24px。如果元素的 line-height: 20px;，那么 1lh = 20px。lh 代表 line-height 单位，意思是「当前元素的行高」。1lh = 当前元素计算后的 line-height 的值。无论字体大小怎么变化，段落间距都会自适应。

---

## 49. [CSS 中的 `vh`！在移动设备上的替代方案-＞`dvh`](https://blog.csdn.net/Lpandeng/article/details/151656349)

移动端慎用CSS的vh单位，它不会自动适应移动浏览器工具栏的显隐变化。解决方案是改用dvh单位，它能动态调整以适应窗口实际高度。文章还提供了示意图对比两种单位的差异表现，并附有详细技术文章链接供进一步阅读。

---

## 50. [CSS 技巧使页脚始终位于网页的底部](https://blog.csdn.net/Lpandeng/article/details/151655823)

fr 代表可用空间份额，1fr 表示占据全部可用空间，若有多个fr 则按照比列分配；一般用来放置 主体内容 (main)，使它填充剩余高度。auto 表示 高度由内容撑开，自动适应高度，一般用于头部header。同第一行规则， 一般用来放置 底部 (footer)。表示 网格布局的 行高规则，分为三行。

---

## 51. [css 高度从 0 到 auto 的动画效果 `interpolate-size: allow-keywords`](https://blog.csdn.net/Lpandeng/article/details/151655137)

CSS中transition: height .5s对固定高度元素有效，但对height:auto无效。针对这种情况，可以使用interpolate-size: allow-keywords属性来实现高度从0到auto的平滑过渡效果。文中还提供了一个CodePen示例，展示了如何实现这种动画效果。

---

## 52. [css 实现滚动捕捉功能](https://blog.csdn.net/Lpandeng/article/details/151651378)

摘要：CSS滚动捕捉功能(scroll-snap)通过scroll-snap-type设置容器滚动行为，scroll-snap-align定义子元素对齐方式(center/start/end)，scroll-snap-stop控制停止行为(always/normal)。三者组合可实现精确的滚动定位效果，特别适用于轮播图、图片库等需要精准滚动停留的界面。该功能简化了传统JavaScript实现的复杂交互，通过纯CSS即可创建流畅的滚动捕捉体验。

---

## 53. [javascript对象添加条件属性的最短最优方法](https://blog.csdn.net/Lpandeng/article/details/151590318)

文章摘要： 第一个代码片段展示了一个函数，它接收三个参数并返回一个对象。该对象包含固定的属性xxx以及传入的参数arg1和arg2。当arg3存在时，还会动态添加一个customProperty属性，展示了一种条件性扩展对象属性的技巧。 第二个代码片段演示了使用扩展运算符(...)处理各种原始值的情况。结果显示，当尝试扩展null、NaN、false、空字符串、undefined、数字0、true和Symbol时，最终得到的都是空对象{}，说明扩展运算符会忽略这些原始值类型。

---

## 54. [纯`css`轻松防止滚动穿透](https://blog.csdn.net/Lpandeng/article/details/151589121)

用于控制滚动到内容边界时的浏览器默认行为。

---

## 55. [使用 `matchMedia()` 方法检测 JavaScript 中的媒体状态](https://blog.csdn.net/Lpandeng/article/details/151446021)

摘要： window.matchMedia() 是用于检测和监听 CSS 媒体查询的 JavaScript API，可动态判断屏幕尺寸、方向等条件。通过传入媒体查询字符串（如 (max-width: 768px)），返回的对象包含属性 .matches（是否匹配）和方法 .addEventListener()（监听变化）。典型应用包括响应式设计增强、按需加载资源及深色模式检测。示例展示了如何用 JS 同步修改样式或响应屏幕变化，弥补纯 CSS 的局限性。

---

## 56. [保持元素可见但不可访问的方法: `inert`](https://blog.csdn.net/Lpandeng/article/details/151334731)

on .

---

## 57. [Vue → React/Next.js 思维对照表](https://blog.csdn.net/Lpandeng/article/details/151291124)

Vuex/Pinia 的 store → React 的 Context + Hooks，或第三方（Zustand/Redux）。Vue 的 指令系统 (v-if, v-for, v-model) → React 全部变成 JS 表达式 + state。Vue 的 单纯前端框架 → Next.js 是 全栈框架（前端 + API + SSR + 部署一体化）。Vue Router 的 显式配置 → Next 的 文件路由（约定大于配置）。

---

## 58. [jsx & React 调试小技巧](https://blog.csdn.net/Lpandeng/article/details/151264297)

本文介绍了React开发的9个实用调试技巧：1) JSX内使用逗号运算符打印变量；2) JSON.stringify格式化展示数据；3) console.table可视化数据；4) React DevTools插件；5) useEffect调试生命周期；6) 临时样式标记组件；7) Error Boundary捕获错误；8) why-did-you-render分析渲染原因；9) useRef记录渲染次数。这些方法能有效提升React调试效率，帮助开发者快速定位问题。

---

## 59. [`IntersectionObserver`延迟加载不在首屏的自动播放视频/图片/埋点/](https://blog.csdn.net/Lpandeng/article/details/151262937)

摘要：IntersectionObserver API 用于监听元素进入/离开视口，替代传统scroll事件提升性能。通过配置root、rootMargin和threshold参数，可实现图片懒加载、无限滚动、广告曝光统计等场景。使用时创建观察器实例，在回调中处理元素可见状态变化。典型应用包括：视口内加载资源、底部触发数据加载、元素曝光埋点及动画触发等，能有效优化页面性能。（150字）

---

## 60. [javascript 国际化方法](https://blog.csdn.net/Lpandeng/article/details/151259800)

JavaScript 的 Intl API 提供了国际化格式化功能，支持数字、货币、日期和相对时间的本地化处理。通过指定地区参数（如'en-US'、'de-DE'），可以自动按当地习惯格式化内容：数字添加分隔符（12,345.678或12.345,678）、货币显示对应符号（$12,345.68或￥12,346）、日期采用本地格式，还能智能转换相对时间（如"yesterday"、"tomorrow"）。这些功能为国际化开发提供了原生支持。

---

## 61. [在 JavaScript 中获取数组最后一项的技巧](https://blog.csdn.net/Lpandeng/article/details/151254075)

两种JavaScript获取数组末位元素的方法：1）使用解构赋值提取length属性并计算末位索引；2）直接使用Array.prototype.at()方法传入-1作为参数。后者更简洁直观，是ES2022新增特性。两种方法都能正确输出结果3。

---

## 62. [使用 `hover:not-[:has(:hover)]` 避免「父元素和子元素同时 hover」时的样式冲突](https://blog.csdn.net/Lpandeng/article/details/151195767)

这篇文章介绍了一个CSS选择器组合:hover:not(:has(:hover))的使用场景。这个技巧可以实现在父元素被悬停时触发效果，但当悬停在子元素时不触发父元素效果。通过一个按钮包含图标的示例演示，当鼠标悬停在按钮本身时背景变色，但悬停在内部图标时不会触发按钮变色。该方案利用了CSS4的:has()伪类（父选择器）和:not()取反伪类，解决了传统CSS中父元素会响应子元素悬停状态的问题。

---

## 63. [corner-shape superellipse()多种图形生成](https://blog.csdn.net/Lpandeng/article/details/151195597)

这个链接展示了一个使用CSS创建圆角形状效果的CodePen示例。代码演示了如何通过CSS的border-radius属性实现不同形状的圆角设计，可能还包含一些动态交互效果。同时引用的corner-shape.com网站可能提供了更多关于CSS形状设计的资源和教程。整个示例简洁地展示了现代前端开发中CSS形状处理的技术实现。

---

## 64. [`＜meter＞ ` 元素 无需 JavaScript/CSS 实现密码强度提示](https://blog.csdn.net/Lpandeng/article/details/151121919)

【摘要】HTML5的<meter>元素可以轻松实现密码强度提示功能，无需JavaScript或CSS。只需合理设置min、max和value属性，浏览器会自动渲染出带颜色指示的强度条。文中通过CodePen示例展示了一个简单的密码强度检测器，当输入密码时，<meter>会根据输入长度动态显示强度变化（弱/中/强），这种原生方案既简洁又高效。

---

## 65. [element-plus el-cascader 动态加载](https://blog.csdn.net/Lpandeng/article/details/149472263)

本文介绍了如何在Element Plus的el-cascader组件中实现动态加载和编辑回显功能。通过lazyLoad异步加载子节点数据，并存储所有节点引用便于快速查找。重点解决了编辑时回显完整路径的问题，包括预加载路径数据、递归加载各级节点等关键逻辑。代码展示了类型定义、动态加载实现、路径预加载方法以及组件使用方式，提供了完整的省市区级联选择解决方案。

---

## 66. [基于 Arco Design UI 封装的 Modal 组件](https://blog.csdn.net/Lpandeng/article/details/144371339)

在日常开发中，Modal 是一个使用频率非常高的 UI 组件。基于 这篇文章 的启发，我编写了一个基于 Arco Design UI 的 Modal 组件封装。我们通过 document.createElement(‘div’) 创建了一个 DOM 容器，并在 document.body 中插入，以便动态渲染 Modal。如果 onOk 返回一个 Promise，则在弹窗确认按钮点击时，显示 loading 状态；通过 update 函数，可以动态更新配置，比如设置 confirmLoading 状态。

---

## 67. [parsing go.mod: module declares its path as: go.mongodb.org/mongo-driver but was required as:....](https://blog.csdn.net/Lpandeng/article/details/140589549)

【代码】parsing go.mod: module declares its path as: go.mongodb.org/mongo-driver but was required as:....

---

## 68. [Mac系统主机名变为bogon的解决方案](https://blog.csdn.net/Lpandeng/article/details/139813522)

首先，“bogon”一词在互联网术语中特指那些不应该出现在公互联网路由表中的IP地址。这些地址通常包括私有IP范围（如192.168.x.x、10.x.x.x和172.16.0.0至172.31.255.255），以及未分配或保留的IP地址空间。当DNS服务器尝试解析这类地址时，可能会返回“bogon”作为主机名，导致您在Mac终端中看到这一非预期的名称。遇到Mac主机名变为“bogon”的情况，不必过于担心。通过上述几步简单的操作，您就可以轻松解决这个问题。

---

## 69. [ts-node](https://blog.csdn.net/Lpandeng/article/details/139747674)

ts-node是一个 TypeScript 执行引擎，它允许您直接运行 TypeScript 代码，而无需先将其编译为 JavaScript。这在开发和测试过程中非常有用，可以提高开发效率。以下是关于ts-node的一些基本信息和使用方法。

---

## 70. [Node.js 中的 **dirname 与 **filename：理解文件路径的神秘面纱](https://blog.csdn.net/Lpandeng/article/details/139686069)

\_dirname是一个字符串，表示当前文件所在目录的绝对路径。这个变量非常有用，当你需要引用同级或上级目录中的文件时，可以避免硬编码路径，从而提高代码的可移植性。无论你的脚本在哪里被执行，**dirname总是指向包含该脚本文件的目录。1.**dirname 是指当前执行脚本所在的目录的路径。2.它总是返回文件所在的目录路径，不包括文件名。3.在模块中使用时，它是动态的，会根据当前模块的位置而变化。

---

## 71. [TypeScript与DOM操作：深入理解相关类型及实战示例](https://blog.csdn.net/Lpandeng/article/details/138757049)

TypeScript允许通过接口扩展来增强现有类型，这对于给DOM元素添加自定义属性非常有用。示例// 输出: Custom Value。

---

## 72. [纯js对比excel小工具](https://blog.csdn.net/Lpandeng/article/details/138295026)

未来，你可以在此基础上扩展更多功能，如导出对比结果、支持更多文件类型等，以满足更广泛的应用需求。

---

## 73. [symbol 类型学习](https://blog.csdn.net/Lpandeng/article/details/137956770)

它不同于常见的字符串、数字等类型，旨在提供一种机制，使得开发者能够在对象中创建不易被外界干扰或误操作的属性。JavaScript 作为一门灵活且功能丰富的编程语言，提供了多种数据类型供开发者构建复杂的应用程序。方法获取），但在日常开发中，它们为对象属性的管理和保护提供了有力工具，有助于构建更加健壮、可维护的代码。对应的属性，开发者能够调整对象与内置操作的交互方式，增强代码的灵活性和可定制性。都是唯一的，但在某些场景下，我们可能需要不同代码模块共享同一个。，为对象属性的管理带来了更高的安全性和定制性。

---

## 74. [csdn文章迁移/迁走历程与实践](https://blog.csdn.net/Lpandeng/article/details/137728223)

csdn 迁移

---

## 75. [在内网环境下成功安装Vue Devtools的曲折历程与解决方案](https://blog.csdn.net/Lpandeng/article/details/137473492)

内网安装vue devtools

---

## 76. [谷歌搜索技巧](https://blog.csdn.net/Lpandeng/article/details/136806375)

谷歌搜索技巧

---

## 77. [看尤雨溪说：为什么Vue3 中应该使用 Ref 而不是 Reactive？](https://blog.csdn.net/Lpandeng/article/details/135774722)

每次有同学学习到vue3的时候，总会问我：“Sunday老师，ref和reactive我们应该用哪个呢？” 我告诉他：“我们应该使用ref，而不是reactive那么此时同学就会有疑惑：“为什么呢？ref还需要.value处理，reactive看起来会更加简单呢？嗯…每当这个时候，我都需要进行一次长篇大论来解释这个问题。不过以后应该不需要了，因为这篇文章将会把这个事情解释的非常清楚…

---

## 78. [一看就会的JS封装](https://blog.csdn.net/Lpandeng/article/details/107367465)

一看就会的JS封装篇 ???????????? JS的三大特性一直是比较难理解的内容，不少初学者甚至有一定经验的大佬都不一定能说的特别的清楚，更多的都是一知半解，而这部分内容又是JS最核心的内容。所以我最近总结了这篇JS封装篇，后面还会陆续发布JS继承篇。希望可以帮到大家。????希望点进来的盆友可以点个赞????哦，你们的支持就是对我最大的鼓励????！！！好吧，让我们回到正题，Let’s go!????????基本概念「封装」 把客观事物封装成抽象的类，隐藏属性和方法，仅对外公开接口。举个

---

## 79. [如何正确判断一个字符串是数值](https://blog.csdn.net/Lpandeng/article/details/123852949)

在网页中，我们从用户输入的内容中获取的值通常是字符串，但是有时候我们希望用户输入的内容一定要能转成数值：userInput.addEventListener('change', (e) => { const value = e.target.value; console.log(typeof value); // string console.assert(isNumeric(value), `Not a numeric value: ${value}`); }...

---

## 80. [Underscore骨骼](https://blog.csdn.net/Lpandeng/article/details/125434553)

【代码】Underscore骨骼。

---

## 81. [elementui el-cascader选择任意一级搭配懒加载使用，单选框radio不会触发懒加载](https://blog.csdn.net/Lpandeng/article/details/129669667)

【代码】elementui el-cascader选择任意一级搭配懒加载使用，单选框radio不会触发懒加载。

---

## 82. [URL 的编码和解码](https://blog.csdn.net/Lpandeng/article/details/128252359)

URL 的编码和解码。

---

## 83. [优化分支语句：状态模式](https://blog.csdn.net/Lpandeng/article/details/128227103)

各位写代码的时候，经常会出现条件判断吧，那么条件判断里面脸最熟的当属 if 了吧，这个东西在我们开始编码的时候，真的是隔一段时间不写，就浑身难受。??但是呢，if 这个东西，哪怕是再简单的判断，也会有隐含问题，而且在代码可读性上，条件判断的效果很不友好，当存在多重判断的时候，简直就是灾难。??所以为了解决条件判断的这些弊端，状态模式应运而生。状态模式??状态模式：当一个对象的内部状态发生改变时，会导致其行为的改变，这看起来像是改变了对象。??我们可以将不同的状态结果封装在状态对象内部，然后该状态对象返回一

---

## 84. [多分支语句优化：策略模式](https://blog.csdn.net/Lpandeng/article/details/128226542)

1、模式定义策略模式，把定义的一组算法封装起来，使其相互之间可以替换。封装的算法具有一定的独立性，不会随客户端变化而变化。2、策略模式 vs. 状态模式从结构上看，策略模式和状态模式很像，也是在内部封装一个对象，然后通过返回的接口对象来实现对内部对象的调用。不同的是，策略模式不需要管理状态，状态之间也没有依赖关系，策略之间可以相互替换，策略对象内部保存的是相互独立的算法。策略模式，就像一个活诸葛，对同一件事情的处理，总有多种可能的计谋，每次都可以随心所欲地选择一种计谋来达到不同种的结果。3、策略模式 举例：

---

## 85. [element UI select 下拉选择无反应 无法选择 Vue设置属性不触发响应](https://blog.csdn.net/Lpandeng/article/details/127370861)

原因: 你在手动触发改变之前,使用了 dialog.forms.roomCode = xxx;而’之前运行了 dialog.forms.roomCode = ‘’;所以dialog.forms.roomCode虽然确实被改变了,但是不过它不是响应式的,所以视图没有更新。场景: 已知El-Select的v-model=‘dialog.forms.roomCode’this.dialog.forms ={ roomCode: “”};$1(ob.value, key, val)去定义响应式的变量)

---

## 86. [git 提交vue代码时遇 代码检查 规范性 报错 导致提交不了](https://blog.csdn.net/Lpandeng/article/details/127248843)

git 提交vue代码时遇 代码检查 规范性 报错 导致提交不了

---

## 87. [在vue中生成唯一id用于v-for:key 可以用Random（）产生吗？](https://blog.csdn.net/Lpandeng/article/details/127248457)

在vue中生成唯一id用于v-for:key 使用Math.random()

---

## 88. [不使用Math.random实现随机数](https://blog.csdn.net/Lpandeng/article/details/125372749)

随机数生成

---

## 89. [使用 TypeScript 常见困惑：interface 和 type 的区别是什么？](https://blog.csdn.net/Lpandeng/article/details/125236297)

当我们使用 TypeScript 时，就会用到 和 ，平时感觉他们用法好像是一样的，没啥区别，都能很好的使用，所以也很少去真正的理解它们之间到底有啥区别。我们开发过经常或这么来定义类型：interface Point { x: number; y: number; }type Point = { x: number; y: number; };或者这样定义： 和 之间的差异不仅仅是次要语法声明。那么，今天我们就来看看这两家伙之间存在啥不可告人的秘密。TypeScript 有 、、 等基本类型。如果

---

## 90. [Yarn安装与使用详细介绍](https://blog.csdn.net/Lpandeng/article/details/123057501)

背景在 Node 生态系统中，依赖通常安装在项目的 node_modules 文件夹中。然而，这个文件的结构和实际依赖树可能有所区别，因为重复的依赖可以合并到一起。npm 客户端把依赖安装到 node_modules 目录的过程具有不确定性。这意味着当依赖的安装顺序不同时，node_modules 目录的结构可能会发生变化。这种差异可能会导致类似“我的电脑上可以运行，别的电脑上不行”的情况，并且通常需要花费大量时间定为与解决。有时候就会遇到这种情况，完整可运行的项目上传到 git 上，别人 pull

---

## 91. [尤大都说Vue3 + script setup + TS + Volar真香，你说香不香？](https://blog.csdn.net/Lpandeng/article/details/120764619)

前两天尤大官宣发布了Vue3.2，支持了好几个很不错的新特性，而且自信放话：<script setup> + TS + Volar = 真香，是时候了想看Vue3.2更新的内容文档的读者可以滑到文章底部点击「阅读原文」相信你已经开始使用或者迫不及待地想尝试Vue3.2了，其实我群里的小伙伴早已经开始使用，而且踩了很多坑了，今天给大家分享一下他的实践投稿文章，希望大家多多支持！正文如下目前setup sugar已经进行了定稿，而vue3 + setup sugar + TS的写法看起来很香，所以我

---

## 92. [vue3 watchEffect](https://blog.csdn.net/Lpandeng/article/details/120708303)

watchEffectwatch : 既要知名监视的属性 又要指明监视的回调watchEffect : 不用指明监视那个属性，监视的回调中用到那个属性就监视那个属性watchEffect有点像computedcomputed注重的计算出来的值（回调函数返回值），必须有returnwatchEffect 更注重过程（回调函数的函数体）不需要写return返回setup(){ let someNodes = reactive({ name:"大",

---

## 93. [vue3 watch](https://blog.csdn.net/Lpandeng/article/details/120707354)

watch监视reactive定义的响应式数据时，oldValue无法正确获取，强制开启了深度监视（deep配置无效）监视reactive定义的响应式数据中的某一个属性时，deep配置有效，setup(){ let num = ref(0), str = ref("strofdn"), persons = reactive({ name:"艾利欧", age:21, work:{ mo:{ award:11

---

## 94. [vue3： vuex (4.x) useStore() 使用； 及useStore() 方法 PC端返回 state ；移动端不返回state](https://blog.csdn.net/Lpandeng/article/details/118969661)

vuex (4.x) useStore() 方法 打印出来 PC端返回 state ；移动端不返回state；state只读import {useStore} from 'vuex'export default { setup(props,context) { const store = useStore() const myStoreData = computed(() => store.state.myStoreData); console.log(store ) /

---

## 95. [vuex actions里方法互相调用](https://blog.csdn.net/Lpandeng/article/details/118928208)

// 假设 getData() 和 getOtherData() 返回的是 Promiseactions: { async actionA ({ commit }) { commit('gotData', await getData()) }, async actionB ({ dispatch, commit }) { await dispatch('actionA') // 等待 actionA 完成 commit('gotOtherData', await ge

---

## 96. [window.location.search 为空?](https://blog.csdn.net/Lpandeng/article/details/118927636)

1，什么是window.location？示例URL：http://b.a.com:88/index.php?name=kang&when=2016#first属性 含义 值protocol: 协议 “http:”hostname: 服务器的名字 “b.a.com”port: 端口 “88”pathname: URL中主机名后的部分 “/index.php”search: "?“后的部分，又称为查询字符串 “?name=kang&when=2016”hash: 返回”#"之后

---

## 97. [Git Bash 上下箭头不生效的解决方案 --- windows解决方案](https://blog.csdn.net/Lpandeng/article/details/115674520)

关于windows 使用 Git Bash 上下箭头不生效有两种解决方法：① 使用数字键盘进行选择对应的选项值：你这里可以输入数字 2 ，然后回车，表示你要选择第 2 个。当然这不是我们最好的处理方式，如果好几个选项每次都要去数一下想要选择的为第几个不是很苦逼…② 使用命令行或者直接更改bash.bashrc第一种：使用命令行的方式创建项目工程，如：之前你使用vue create hello-world 现在应该改成输入 winpty vue.cmd create hello-world，这样你的

---

## 98. [js.md](https://blog.csdn.net/Lpandeng/article/details/115491829)

script 元素async: 会立即下载次脚本，不会妨碍阻塞其他操作，比如下载其他资源和加载其他脚本仅对外部文件有效defer: 表示 脚本可以延迟到文档完全被解析和显示之后再执行；仅对外部脚本有效，兼容性好基本概念typeofjs var message = "some string"; alert(typeof message); // "string" alert(typeof(message)); // "string" alert(typeof 95); // "numb

---

## 99. [这些JavaScript编程黑科技，装逼指南，高逼格代码，让你惊叹不已](https://blog.csdn.net/Lpandeng/article/details/110767274)

1、单行写一个评级组件"★★★★★☆☆☆☆☆".slice(5 - rate, 10 - rate);定义一个变量rate是1到5的值，然后执行上面代码，看图才发现插件什么的都弱爆了2、如何装逼用代码骂别人SB(!(~+[])+{})[--[~+""]+[]]_[~+[]] + ~~!+[]]+({}+[])[[~!+[]]_~+[]3、如何用代码优雅的证明自己NB这个牛逼了console.log(([][]]+[])[+!![]]+([...

---

## 100. [uni-app、H5+、获取指定路径目录下所有文件](https://blog.csdn.net/Lpandeng/article/details/109640185)

plus.io.resolveLocalFileSystemURL( "\_downloads", //指定的目录 function(entry) { var directoryReader = entry.createReader(); //获取读取目录对象 directoryReader.readEntries( function(entries) { //历遍子目录即可 for (var i = 0; i < entries

---

## 101. [uni-app下载文件(plus.downloader.createDownload)](https://blog.csdn.net/Lpandeng/article/details/109597834)

/\*\* _ {url} 下载地址 _ {name} 保存文件时 重命名 _ {cb1,cb2} 下载进度和完成 的回调 _ ：下载大文件“可能”会内存溢出 \* \*/export default (url,name,cb1,cb2) => { let progressVal = 0; var dtask = plus.downloader.createDownload(url,{ filename:"\_downloads/"+name //利用保存

---

## 102. [plus.downloader.createDownload下载默认存放路径](https://blog.csdn.net/Lpandeng/article/details/109595451)

plus.downloader.createDownload下载默认存放路径在哪里（\_download文件夹在哪里）？

---

## 103. [uniapp:slider 报 Ignored attempt to cancel a touchmove event with cancelable=false, for example....](https://blog.csdn.net/Lpandeng/article/details/109258026)

10.24

---

## 104. [【vue】ios中返回到列表页出现空白的问题](https://blog.csdn.net/Lpandeng/article/details/106838375)

问题：ios机器上点击返回列表页的时候，会出现空白现象，触屏一下或者拉动一下，数据才会显示出来，解决方案：给当前组件最外层元素添加以下样式overflow-y: auto;-webkit-overflow-scrolling: touch;position: absolute;top:0;left:0;width:100%;height:100%;...

---

## 105. [html2canvas 在ios 13.4.x 、 13.5.x 微信浏览器中失效无反应](https://blog.csdn.net/Lpandeng/article/details/106824124)

如题：html2canvas 在ios 13.4.x 、 13.5.x 微信浏览器中失效无反应解决方法:html2canvas 回退到rc.4版本后可以了。参考 微信开放社区

---

## 106. [散碎笔记-------](https://blog.csdn.net/Lpandeng/article/details/98052086)

循环Object.keys -> 遍历自身可枚举的属性Object.getOwnPropertyNames -> 获取自身可枚举的属性obj.hasOwnProperty -> 是否自身属性for(let key in obj) -> 遍历自身及原型链上可枚举的属性ps: for(key value of obj) -> es6创造的对各种数据结构统...

---

## 107. [vue中引入swiper(4.0+)，打包出错（ ERROR in static/js/4.bafdba9a08bd02fd1c37.js from UglifyJs Unexpected toke）](https://blog.csdn.net/Lpandeng/article/details/90695260)

vue打包报错： ERROR in static/js/4.bafdba9a08bd02fd1c37.js from UglifyJs Unexpected token: name (Dom7) [./~/\_dom7@2.1.3@dom7/dist/dom7.modular.js:16,0][static/js/4.bafdba9a08bd02fd1c37.js:853,6]在build文件夹中...

---

## 108. [H5-input 弹起键盘遮盖输入框(Android),键盘顶不起来输入框， ios正常](https://blog.csdn.net/Lpandeng/article/details/90262134)

遇到H5页面-input 弹起键盘遮盖输入框(Android),键盘顶不起来输入框， ios正常 的问题用js的resize()方法对浏览器窗口调整大小进行计数：览器窗口的大小时，发生 resize 事件。就可以解决window.addEventListener('resize', () => { if (document.activeElement.tagN...

---

## 109. [vue Computed property "XXX" was assigned to but it has no setter](https://blog.csdn.net/Lpandeng/article/details/89679460)

<div  v-model="xxx"><script>import { mapGetters } from "vuex";computed: {...mapGetters([	"xxx"]),},用vuex数据时 警告：Computed property “XXX” was assigned to but it has no setter第一种尝试–...

---

## 110. [安装mysql和mongoDB](https://blog.csdn.net/Lpandeng/article/details/89190261)

mongoDB:参考mysql:参考参考以上步骤，均已安装成功，未遇到坑。

---

## 111. [vue 自定义指令 -- 图片预览](https://blog.csdn.net/Lpandeng/article/details/88930795)

vue 自定义指令 – 图片预览放大安装npm i lpd-image --save使用在 main.js 中import xxxx from 'lpd-image'在组件中： <img alt="Vue logo" src="./assets/logo.png" v-lpd-image> 默认scale ：1 ，opacity：0.5 <img alt="...

---

## 112. [仿 vue-cli 搭建属于自己的脚手架](https://blog.csdn.net/Lpandeng/article/details/88930740)

仿 vue-cli 搭建属于自己的脚手架实现一个简易的模版 ，可以通过npm 安装仓库地址：传送门

---

## 113. [vue配置多页应用项目模板](https://blog.csdn.net/Lpandeng/article/details/88805023)

最近研究了一下 vue 多页面应用，参考着，也搞了个模板： 模板传送门至于 多页面 、 单页：

---

## 114. [自定义文字云/词云图----基于echarts](https://blog.csdn.net/Lpandeng/article/details/87970294)

demo连接 ：自定义文字云/词云图效果如下：人形态小鸟形态参考 https://github.com/ecomfe/echarts-wordcloud，https://blog.csdn.net/shelbyandfxj/article/details/83243284...

---

## 115. [PHP 判断数据类型](https://blog.csdn.net/Lpandeng/article/details/85227918)

isset()://变量是否已经声明 empty()://变量是否为空 defined()://常量是否已经定义 define() array_key_exists(mixed key, array search)://检查给定的键名或索引是否存在于数组中is_numeric ( mixed var )://检测变量是 否为数字或数字字符串 is_bool():// 检测变量是否是布尔型...

---

## 116. [vue-devtools:Vue.js Devtools inspection is not available because it's in production mode or explicit](https://blog.csdn.net/Lpandeng/article/details/84575298)

vue-devtools安装以后，勾选了“允许访问文件网址”之后还是无法使用有时需要启动多个vue项目有的项目可以用，有的项目虽然左上角V图标是亮着的，但是控制台却不出来vue，（有时，时出来时不出来也有可能是缓存或电脑卡吧。。。）1、勾选了“允许访问文件网址”，还是无法使用：Vue.js is detected on this page. Devtools inspection i...

---

## 117. [vue 报错：Cannot read property 'xxx' of undefined"，但是页面能渲染上数据](https://blog.csdn.net/Lpandeng/article/details/83218646)

有时候会遇到给页面绑定数据的时候，可以绑定成功，但vue warn:xxx属性of undefined，，，如果本组件只是绑定简单的数据倒是可以忽略，如果本组件还引入了其他组件或第三方组件，插件，则就渲染不出来，就需要解决了，&lt;template&gt; ... &lt;span&gt;{{data.xxx.xx}}&lt;/span&gt; ...&lt;/tem...

---

## 118. [vue项目打包后路由视图router-view 不显示](https://blog.csdn.net/Lpandeng/article/details/83218597)

早段时间 ，用脚手架vue-cli 搭建的项目，build后放于服务器上，发现其他资源全部变成静态加载成功，但路由视图为空，Vue.use(VueRouter)const router = new VueRouter({ mode: 'history', base: '/system/', //添加根目录 routes})比如将打包后的dist和inde...

---

## 119. [项目技术点，参考](https://blog.csdn.net/Lpandeng/article/details/82564107)

1 自执行函数 ：http://www.cnblogs.com/TomXu/archive/2011/12/31/2289423.htmlhttps://www.cnblogs.com/jiangshichao/p/7152855.html2 当js里有多个export怎么引入？https://segmentfault.com/q/10100000093725913 VUE -- 全局...

---

## 120. [node开启本地服务，读取本地站点](https://blog.csdn.net/Lpandeng/article/details/80822602)

var http=require('http');var fs=require('fs');var root=&quot;E:/nodeSer&quot;//开启服务var server=http.createServer(function(req,res){ var url=req.url; var file = root+url; console.log(file) fs....

---

## 121. [clipboard.js](https://blog.csdn.net/Lpandeng/article/details/80796311)

平时浏览某些app或网站后，会自动复制吱口令，，实现demo如下js下载地址—密码a00r&lt;!DOCTYPE html&gt;&lt;html&gt; &lt;head&gt; &lt;meta charset="UTF-8"&gt; &lt;title&gt;&lt;/title&gt; &lt;/head&am

---

## 122. [40个JS轮子](https://blog.csdn.net/Lpandeng/article/details/80780138)

1、将彻底屏蔽鼠标右键oncontextmenu=”window.event.returnValue=false”&lt; table border oncontextmenu=return(false)&gt;&lt; td&gt;no&lt; /table&gt; 可用于 Table2. 取消选取、防止复制&lt; body onselectstart=”return fals...

---

## 123. [vue计算属性详解(转)](https://blog.csdn.net/Lpandeng/article/details/80754614)

一、什么是计算属性模板内的表达式非常便利，但是设计它们的初衷是用于简单运算的。在模板中放入太多的逻辑会让模板过重且难以维护。例如：&lt;div id="example"&gt; {{ message.split('').reverse().join('') }}&lt;/div&gt;这里的表达式包含3个操作，并不是很清晰，所以遇到复杂逻辑时应该使用Vue特带的计...

---

## 124. [VueJs探索之watch用法详解(转)](https://blog.csdn.net/Lpandeng/article/details/80754599)

&lt;div id="app"&gt; &lt;input type="text" v-model:value="childrens.name" /&gt; &lt;input type="text" v-model:value="lastName" /&gt; &lt;/div&gt; &lt;s

---

## 125. [本地离线存储localforage](https://blog.csdn.net/Lpandeng/article/details/80713672)

关于 HTMl5的sessionStorage和localStorage–灵活使用传送门localforage 用法类似转载自API1）setItem(key, value, successCallback)：创建一个键，参数是键名、键值、回调函数，回调函数的参数是对应的键值。// Unlike localStorage, you can store non-strings.lo...

---

## 126. [reduce](https://blog.csdn.net/Lpandeng/article/details/80603447)

图列

---

## 127. [vue购物车实例](https://blog.csdn.net/Lpandeng/article/details/80603446)

测试代码1&amp;lt;template&amp;gt; &amp;lt;div id=&quot;my&quot;&amp;gt; 全选&amp;lt;input type=&quot;checkbox&quot; v-model=&quot;checkAll&quot; @change=&quot;change&quot;&amp;gt; &amp

---

## 128. [48 个 JavaScript 代码片段](https://blog.csdn.net/Lpandeng/article/details/80577884)

Anagrams of string（带有重复项） 使用递归。对于给定字符串中的每个字母，为字母创建字谜。使用map（）将字母与每部分字谜组合，然后使用reduce（）将所有字谜组合到一个数组中，最基本情况是字符串长度等于2或1。const anagrams = str =&gt; {if (str.length &lt;= 2) return str.length === 2 ? [s...

---

## 129. [Vue.$nextTick&Vue.nextTick](https://blog.csdn.net/Lpandeng/article/details/80547588)

Vue.nextTick(callback)，当数据发生变化，更新后执行回调。 Vue.$nextTick(callback)，当dom发生变化，更新后执行的回调。 参考&amp;amp;实例

---

## 130. [vue:is属性,keep-alive,slot,watch,插件,动态class,防止页面出现{{}},改变数据取最新值,计算属性,懒加载,全局过滤器,生命周期,自定义指令..等知识点](https://blog.csdn.net/Lpandeng/article/details/80544703)

fliter filter和map forEach includes&amp;amp;find is切换缓存&amp;amp;组件缓存 is属性 keep-alive mount-nexttick. ref1 ref2 slot slot实例...

---

## 131. [script标签的defer和async ---总结](https://blog.csdn.net/Lpandeng/article/details/80230172)

async 与 defer 的差别async 和 defer 标注的 script 都不会暂停HTML解析就立刻被下载,两者都支持onload事件回调来解决需要该脚本来执行的初始化。两者的区别在于执行时的不同：async 脚本在script文件下载完成后会立即执行,并且其执行时间一定在 window的load事件触发之前。这意味着多个async脚本很可能不会按其在页面中的出现次序顺序执...

---

## 132. [js 将汉字转换为GB2312格式的编码](https://blog.csdn.net/Lpandeng/article/details/80224342)

引入js: encodeToGb2312.js下载地址引用此js后，调用 encodeToGb2312(str)即可。eg&lt;input id="q" type="text" /&gt;&lt;input id="button" type="button" value="搜索" /&gt;给以上输入框绑定点击事件，在点击事件中：console.l

---

## 133. [咸鱼pc端搜索功能](https://blog.csdn.net/Lpandeng/article/details/80224068)

咸鱼pc端搜索功能咸鱼pc端无搜索功能，那么如何搜索尼？咸鱼app有搜索功能另一种下面介绍地址栏搜索法： 搜索宝贝在地址栏上输入： https://s.2.taobao.com/list/list.htm?_input_charset=utf8&amp;q=关键词 传送门—— [ 点击搜索宝贝 ] 搜索某用户下所有发布的宝贝地...

---

## 134. [清除node_modules 缓存](https://blog.csdn.net/Lpandeng/article/details/80202028)

当清node_modules 出现某一些包错误时候，查不到原因时候，可以适当的清除缓存试试。删掉重新安装rm -rf node_modulesnpm cache cleannpm install

---

## 135. [Meta http-equiv属性详解(转)](https://blog.csdn.net/Lpandeng/article/details/79090225)

http-equiv顾名思义，相当于http的文件头作用，它可以向浏览器传回一些有用的信息，以帮助正确和精确地显示网页内容，与之对应的属性值为content，content中的内容其实就是各个参数的变量值。 引用meat标签的http-equiv属性语法格式是：＜meta http-equiv="参数" content="参数变量值"＞ ；其中http-equiv属性主要有以下几种参数：1、Exp

---

## 136. [前端性能优化](https://blog.csdn.net/Lpandeng/article/details/79089760)

转自：http://web.jobbole.com/93665/通过性能测速和分析，我们基本可以获取收集到页面上大部分的具体性能数据，如何根据这些数据采取适当的方法和手段对当前的页面进行优化呢？目前来看，前端优化的策略很多，如YSlow（YSlow是Yahoo发布的一款Firefox插件，可以对网站的页面性能进行分析，提出对该页面性能优化的建议）原则等，总结起来主要包括网络加载类、页面渲染类、CS

---

## 137. [app回流---之深度连接linkedme](https://blog.csdn.net/Lpandeng/article/details/79084408)

项目参考：http://m.vancl.com/深度链接（Deep Linking），可以从手机中任何地方将用户导入APP内的指定页面。LinkedME——国内首家企业级深度链接服务提供商，致力于帮助APP解决用户增长（拉新、拉活、留存、转化等）和流量变现等问题。LinkedME,企业级深度链接(Deep Linking)服务平台https://www.linkedme.cc/

---

## 138. [js 去掉 <!--[if gte vml 1]><!--[endif]-->](https://blog.csdn.net/Lpandeng/article/details/79034906)

前端在处理后台用富文本编辑后传来的数据时，带有：<v:shapetype id="\_x0000_t75" coordsize="21600,21600" o:spt="75" o:preferrelative="t" path="m@4@5l@4@11@9@11@9@5xe" filled="f" stroked="f">

---

## 139. [js 生成两个整数之间不重复的n个随机整数](https://blog.csdn.net/Lpandeng/article/details/78974177)

偶遇一个js面试题：编写一个javscript函数 fn，该函数有一个参数 n（数字类型），其返回值是一个数组，该数组内是 n 个随机且不重复的整数，且整数取值范围是 [2, 32]。 如果愿意，请先暂停阅读文章，自己动手写一下这个函数。甲： var fn=function(n){ var arr=[]; n=n&&(+n)>0?(+n).toFixed(0):

---

## 140. [HTMl5的sessionStorage和localStorage--灵活使用](https://blog.csdn.net/Lpandeng/article/details/78955241)

转自：https://www.cnblogs.com/yuzhongwusan/archive/2011/12/19/2293347.htmlhtml5中的Web Storage包括了两种存储方式：sessionStorage和localStorage。sessionStorage用于本地存储一个会话（session）中的数据，这些数据只有在同一个会话中的页面才能访问并且当会话结束

---

## 141. [js处理去掉富文本编辑的html，样式，只显示纯文字内容，以供列表页使用](https://blog.csdn.net/Lpandeng/article/details/78954310)

var description = ' 1.国际保险经纪行业收入分析 2010年全球保险经纪行业市场规模为437.56亿美元，2015年增长至581.3亿美元。 2010-2015年国际保险经纪行业市场规模：亿美元 2.国际保险经纪行业并购分析 保险经纪公司并购较为频繁，2011年并购数量为351件，且呈现增长趋势。一股保险行业的并购风潮正席卷全球各个市场。如意大利投资集团Exor收购

---

## 142. [js对电话和姓名身份证等进行部分隐藏处理](https://blog.csdn.net/Lpandeng/article/details/78933184)

将从后台获取到的数据进行字符串截取，为截取到的位数用*代替，形成这种思路之后我们可以写一个方法，如下function plusXing (str,frontLen,endLen) { var len = str.length-frontLen-endLen;var xing = '';for (var i=0;i<len;i++) {xing+='*';}return str.su

---

## 143. [H5、js、上传头像将图片转换成base64格式的：data:image/png;base64,iVBORw0](https://blog.csdn.net/Lpandeng/article/details/78923008)

$("#img_upload_file").change(function() {            varoFile = this.files[0];            console.log("oFile")            console.log(oFile)            varreader = newFileReader();

---

## 144. [原生js 实现双向数据绑定](https://blog.csdn.net/Lpandeng/article/details/78876265)

{{hello}}    var obj = {};    Object.defineProperty(obj,'hello',{        set:function(val){            document.getElementById('bb').innerHTML = val;            document.getElementById('

---

## 145. [h5(H5)下载功能，用JS在浏览器中创建下载文件](https://blog.csdn.net/Lpandeng/article/details/78851568)

转载：http://www.jb51.net/article/47723.htm但受限于浏览器，很多情况下我们都只能给出个链接，让用户点击打开-》另存为。如下面这个链接：复制代码代码如下:file.js用户点击这个链接的时候，浏览器会打开并显示链接指向的文件内容，显然，这并没有实现我们的需求。HTML5中给a标签增加了一个download属性，只

---

## 146. [js的function传值,字符串无法传值,](https://blog.csdn.net/Lpandeng/article/details/78710441)

在html 中 onclick = xx(变量)，若变量是Number类型，则无问题。若变量是 字符串类型的，则不可以。1 转译2 若用的是模版引擎渲染页面，上面方法就不行了，可以用 &quot；div class="gwDetailWdList" onclick="enterWTDetail( "%=data[i].id%>")">

---

## 147. [jQuery序列化后的表单值转换成Json](https://blog.csdn.net/Lpandeng/article/details/78704817)

$.fn.serializeObject = function(){ var o = {}; var a = this.serializeArray(); $.each(a, function() { if (o[this.name] !== undefined) { if (!o[this.name].push) {

---

## 148. [js获取url传递参数，js获取url？号后面的参数window.location](https://blog.csdn.net/Lpandeng/article/details/78687591)

Script language="javascript">   function GetRequest() {      var url = location.search; //获取url中"?"符后的字串      var theRequest = new Object();      if (url.indexOf("?") != -1) {         var st

---

## 149. [使用swiper 轮播插件ajax 请求加载图片时，无法滑动](https://blog.csdn.net/Lpandeng/article/details/78645424)

因为banner图是动态创建的，在插件开始初始化时，文档流中没用图片，故没有创建相应宽度，通过调整js加载顺序，问题还是没有解决。最后找到swiper插件 api 有属性是可以根据内容变动，自动初始化插件的，添加observer：true后问题解决！var mySwiper = new Swiper ('.swiper-container', {        pagina

---

## 150. [把后台传来的日期时间转化为几天前,几小时前，几分钟前在前端展现](https://blog.csdn.net/Lpandeng/article/details/78623724)

function timeago(dateTimeStamp){ // dateTimeStamp是一个时间毫秒，注意时间戳是秒的形式，在这个毫秒的基础上除以1000，就是十位数的时间戳。13位数的都是时间毫秒。 var minute=1000*60; //把分，时，天，周，半个月，一个月用毫秒表示 var hour=minute*60

---

## 151. [h5移动端输入框随键盘上升](https://blog.csdn.net/Lpandeng/article/details/78579869)

var xxxxxxxx = document.getElementById('#xxx');setInterval(function(){ xxxxxxxx.scrollIntoView(false);},200)Element.scrollIntoView()说是还在试验中的属性，mdn: https://developer.mozilla.org/zh-CN/docs/We

---

## 152. [多个页面共用一个js文件，但是有些页面没有某个元素，导致报错](https://blog.csdn.net/Lpandeng/article/details/78455907)

if(document.getElementById("id")){ alert('对象存在'); ... ...}else{ alert('对象不存在'); ... ...} 参考传送门：https://segmentfault.com/q/1010000011586519

---

## 153. [node-pre-gyp ERR! node-pre-gyp -xxxxxxxxxxxx](https://blog.csdn.net/Lpandeng/article/details/78263079)

参考：http://blog.csdn.net/qq_26819733/article/details/55549241?locationNum=11&fps=1当github上下载别人的vue项目时候，在npm install 时候报错，亲测已解决npm install -g grunt-node-inspector 偶见另一方法：http://www.mamicode.com/inf

---

## 154. [只要三句话就可以实现不定宽高水平垂直居中。](https://blog.csdn.net/Lpandeng/article/details/78217123)

justify-content:center;//子元素水平居中align-items:center;//子元素垂直居中display:-webkit-flex;在父级元素上面加上上面3句话，就可以实现子元素水平垂直居中。

---

## 155. [用windows终端命令删除node_modules用windows终端命令删除文件夹](https://blog.csdn.net/Lpandeng/article/details/78216995)

安装npm install -g rimraf使用cd xxx[include node_modules folder]rimraf nod_modules参考：http://blog.csdn.net/crper/article/details/50458369

---

## 156. [移动端js判断手指滑动方向](https://blog.csdn.net/Lpandeng/article/details/78021186)

var startx, starty; //获得角度 function getAngle(angx, angy) { return Math.atan2(angy, angx) \* 180 / Math.PI; }; //根据起点终点返回方向 1向上 2向下 3向左 4向右 0未滑动 function getDirection(start

---

## 157. [解决npm -v 无反应](https://blog.csdn.net/Lpandeng/article/details/77840585)

删除 账户目录下的.npmrc文件就行了（例：我的目录：C:\Users\Administrator），在C盘搜索.npmrc  然后删除，https://www.oschina.net/question/570769_88967

---

## 158. [ps/Photoshop无需购买，直接安装](https://blog.csdn.net/Lpandeng/article/details/77771828)

windows 按照这个网站一步一步来就行，：http://www.ps265.com/ps/photoshop-cs3-cs5-cs6-5.html

---

## 159. [“青涩不及当初，聚散不由你我”](https://blog.csdn.net/Lpandeng/article/details/76274228)

我们还处于无法选择生活的阶段，为了生活而四处奔波，而我，也不列外。

---

## 160. [了解D3.js-数据可视化](https://blog.csdn.net/Lpandeng/article/details/76139357)

什么是D3.js?D3 的全称是（Data-Driven Documents），顾名思义可以知道是一个被数据驱动的文档。听名字有点抽象，说简单一点，其实就是一个 JavaScript 的函数库，使用它主要是用来做数据可视化的。JavaScript 文件的后缀名通常为 .js，故 D3 也常使用 D3.js 称呼。D3 提供了各种简单易用的函数，大大简化了 JavaScript

---

## 161. [webp如何使用,webp是什么？webp如何生成，](https://blog.csdn.net/Lpandeng/article/details/76039409)

之前项目中使用图片，图标有时候是png,jpg格式的，对于太大的图片处理，其中可以利用一些工具压缩一下，推存网站可以在线压缩也比较省事：https://tinypng.com/对于移动端项目，使用到图片或图标是设计师把其做成矢量图，前端使用时把其当作字体形式使用即可。但如今对于 JPEG、PNG 和 GIF 这些图片格式的优化几乎已经达到了极致， 若想改变现状开辟新局面，便要有釜底抽薪

---

## 162. [使用sass时，如何快速安装ruby环境](https://blog.csdn.net/Lpandeng/article/details/75267502)

参考：http://blog.csdn.net/u012882134/article/details/51685127 下载地址：https://rubyinstaller.org/downloads/下载完，安装 =》运行。即可，在终端运行 ruby -v   查看是否安装成功。

---

## 163. [jq 判断元素到窗口底部的距离](https://blog.csdn.net/Lpandeng/article/details/74025322)

$(window).height();//是文档窗口高度$("div").offset().top//是标签距离顶部高度$(document).scrollTop();//是滚动条高度$("div").height();//是标签高度你要的高度+$("div").height()+[$("div").offset().top-$(document).scrollTop()]=$(window).h

---

## 164. [设置div中文字超出时自动换行和css实现文本超出N行之后显示省略号等](https://blog.csdn.net/Lpandeng/article/details/72885811)

一、对于div强制换行1.（IE浏览器）white-space:normal; word-break:break-all;这里前者是遵循标准。#wrap{white-space:normal; width:200px; }或者#wrap{word-break:break-all;width:200px;}2.（Firefox浏览器）white-space:normal; word-br

---

## 165. [Photoshop投影与CSS中box-shadow的转换](https://blog.csdn.net/Lpandeng/article/details/72778451)

来自：http://www.jb51.net/css/404167.html"混合模式"：Photoshop提供了各式各样的混合模式，但是CSS3阴影只支持正常模式（normal）。"颜色（color）"：阴影颜色。对应于CSS3阴影中的 color 值。"不透明度（opacity）"：阴影的不透明度。对应于CSS3阴影的颜色 rgba() 中的 a 值。"角度

---

## 166. [jquery正则匹配url地址和邮件地址的实例](https://blog.csdn.net/Lpandeng/article/details/72770934)

来自：http://www.45fan.com/bcdm/15096.html这段代码可以分析出文本里的所有超级链接，包含邮件、url、#链接等等，并分别输出为真实链接地址$.fn.tweetify = function() { this.each(function() { $(this).html( $(this).html() .replace(/((ftp|http|

---

## 167. [html img图片不变形等比例缩放,兼容ie6](https://blog.csdn.net/Lpandeng/article/details/72520631)

方法1 img 只定义宽（或高）度可以等比例缩放，外面加个框，设置宽高和 overflow:hidden; 即可方法2 在img标签里面只设置宽，不设置高，图片就会等比例缩放。方法3或者把图片作背景图片。background-position: center center tips:使用max-width:30

---

## 168. [ajax提交整个form表单](https://blog.csdn.net/Lpandeng/article/details/72520583)

在项目开发中，有时提交form表单时不能单单用action或者jQuery的表单提交方法有三种，主要说下第三种第一种：用form自带属性action提交第二种：用jquery提交：$("#formid").submit();第三种：用ajax提交：但如果form表单中数据很多时，不可能一一列出，只需要用$('#yourformid').serialize()就可以了举例如下：$.a

---

## 169. [原生JS封装ajax方法](https://blog.csdn.net/Lpandeng/article/details/72399221)

from:http://www.cnblogs.com/a757956132/p/5603176.html ,/_ 封装ajax函数 _ @param {string}opt.type http连接的方式，包括POST和GET两种方式 _ @param {string}opt.url 发送请求的url _ @param {boolean}opt.async 是否为异步请求，true为异步

---

## 170. [解决JQuery MiniUI前端库到期alert弹窗](https://blog.csdn.net/Lpandeng/article/details/72281935)

form： http://www.chawenti.com/articles/17909.html  :http://www.cnblogs.com/Granger/p/3232342.html前端时间有个项目不想用HTML自己画后台UI。图省事就准备用现成的JS UI库当时初步选择了：ExtJS:功能比较全，但是库比较大，并且学习门槛较高，放弃

---

## 171. [IE9 以下版本浏览器兼容HTML5的方法](https://blog.csdn.net/Lpandeng/article/details/71719871)

最新版本的 Safari、Chrome、Firefox 以及 Opera 支持某些 HTML5 特性。Internet Explorer 9 将支持某些 HTML5 特性。--------------------也不知道这句话是什么时候说的？？？？？？？？？？IE9 以下版本浏览器兼容HTML5的方法，使用百度静态资源的html5shiv包： 载入后，初始化新标签的CS

---

## 172. [Ionic 开发环境搭建（Windows）](https://blog.csdn.net/Lpandeng/article/details/71638714)

出处 ：http://www.jianshu.com/p/b9757a5bcb07Ionic 概述Ionic 官网：http://www.ionicframework.com/Ionic 是一个强大的 HTML5 SDK，它使用 HTML、CSS、Javascript 等 web 技术帮助你快速构建原生风格的移动应用Ionic 目前能支持 iOS 和 And

---

## 173. [解决微信界面返回问题](https://blog.csdn.net/Lpandeng/article/details/71616423)

把代码写在1页面的点击进入下一级的事件中，点击手机自带的返回就会有效果，（事列：所有页面在一个网页中显示，控制显隐）if (window.history && window.history.pushState){$(window).on('popstate', function() {var hashLocation = location.hash;var hashSplit = hashL

---

## 174. [解决微信端浏览器使用window.location.reload()刷新页面不生效](https://blog.csdn.net/Lpandeng/article/details/71518105)

给其请求地址加随机数，只要js认为链接不一样就会再次取新的内容。1、是加随机数。2、加时间戳：（时间戳应该是比随机数更随机的数，保证了每次不一样）window.location.href = "http://b\*\*\*\*.com.r?pfid=1&" + Date.parse(new Date());

---

## 175. [CSS 三角形绘制方法](https://blog.csdn.net/Lpandeng/article/details/71477370)

：from:      http://www.jb51.net/article/42513.htm CSS 三角形绘制方法复制代码代码如下:#triangle-up {    width: 0;    height: 0;    border-left: 50px solid transparent;    border-right: 50px soli

---

## 176. [ie兼容问题,强制使用ie浏览器使用最高版本内核](https://blog.csdn.net/Lpandeng/article/details/71474196)

在IE8浏览器以后版本，都有一个“兼容性视图”，让不少新技术无法使用。那么如何禁止浏览器自动选择“兼容性视图”，强制IE以最高级别的可用模式显示内容呢？下面就介绍一段HTML代码。X-UA-Compatible是一个设置IE浏览器兼容模式的属性，在IE8浏览器之后诞生。IE8或者IE9有很多种模式，比如，IE8有4种模式：IE5.5怪异模式、IE7标准模式、IE8几乎标准模式、IE8标准模

---

## 177. [webstorm 2017 激活pojie,](https://blog.csdn.net/Lpandeng/article/details/71453600)

2017.2.27更新 选择“license server” 输入：http://idea.imsxm.com/2016.2.2 版本的破解方式： 安装以后，打开软件会弹出一个对话框；选择“license server” 输入：http://114.215.133.70:410172016.2.3 版本的破解方式： 目前最新的就是2.3版本，在打开的License Activation

---

## 178. [实现数字从零动态跳动到（规定）最大值或原始值](https://blog.csdn.net/Lpandeng/article/details/71424239)

$(function() { var n1 = 0; var n2 = 0; var n3 = 0; var to1 = 600; //第一个需要显示数字的地方默认最大值 让其从0开始动态达到最大值。 var to2 = 2546; //第二个需要显示数字的地方默认最大值 var to3 = 3002; //第三个需要显示数字的地方默认最大值 functi

---

## 179. [省市区三级联动area](https://blog.csdn.net/Lpandeng/article/details/71422370)

引入 后，用法//省市县三级联动var area = new AreaCtrl("", " ", " ");$(".area").append(area.get());area.loadData();/\*\* _ 省市区三级联动 plugin _ _ Copyright (c) 2014 萧峰 (biweb.cn) _ Dual licensed under the MI

---

## 180. [jq imgview.js](https://blog.csdn.net/Lpandeng/article/details/71420180)

(function($){$.fn.imgview = function(){ var that = $(this);	if($("body>div.imgview").length == 0) creatBox(); function creatBox(){ var str = 'body>div.imgview{position:fixed;top:0px;left:0px;wid

---

## 181. [rem,移动端适配心得2【转载】](https://blog.csdn.net/Lpandeng/article/details/71420107)

随着移动端的发展，手机端的页面应用越来越广泛，所以我们现在更多的是做移动端的页面。但是我们同样要维持pc端，因此难免会遇到许多麻烦。而且现在做移动端适配的方法也有好多种，针对不同的网站我们需要合理的判断，选择全适的方法；第一种方法：整个页面宽高用px写死，让宽度自适应这是最蠢的一个办法，但是实际上我们用得也挺多，它适用于一些页面结构比较复杂的

---

## 182. [rem布局](https://blog.csdn.net/Lpandeng/article/details/71419993)

rem布局非常简单，首页你只需在页面引入这段原生JS代码就可以了(function (doc, win) {var docEl = doc.documentElement,resizeEvt = 'orientationchange' in window ? 'orientationchange' : 'resize',recalc = function () {var clientWi

---

## 183. [一段关于rem适配的js](https://blog.csdn.net/Lpandeng/article/details/71419739)

 !new function(){var e=this;e.width=640;e.fontSize=100;e.widthProportion=function(){ var t=(document.body&amp;&amp;document.body.clientWidth||document.getElementsByTagName("html")[0].offsetWid...

---

## 184. [响应字体大小（移动端）](https://blog.csdn.net/Lpandeng/article/details/71419632)

大前提：1、initial-scale 为 1；2、在项目css中(注意不要被公共的base、common之类的影响了，资源加载顺序也是蛮重要的)，先把html的fontSize设置为 100px（或者加上媒体查询代码）, 避免加载未完成时候样式错乱;html{fontSize:100px}需要全屏的话加上CSShtml{height:100%;position:relative;

---

## 185. [调取微信相册相机](https://blog.csdn.net/Lpandeng/article/details/71268581)

wx.config({ debug: false,//调试模式 appId: '', timestamp: , nonceStr: '', signature: '', jsApiList: ['chooseImage','uploadImage']});wx.ready(function () { // 点击调取相机和相册 $(".img

---

## 186. [jquery.modal.js](https://blog.csdn.net/Lpandeng/article/details/71249136)

/\*\* _ 模态框 Author:雨思 QQ:331406669 Date:2016-09-19 _ $.modal.alert(msg,function(){}); _ $.modal.confirm(msg,function(boolean){}); _ $.modal.prompt(msg,function(false|value){}); \* $.modal.msg(msg,fu

---

## 187. [解决安卓微信浏览器中location.reload 或者 location.href失效的问题【2】](https://blog.csdn.net/Lpandeng/article/details/71249058)

在移动wap中，经常会使用window.location.href去跳转页面，这个方法在绝大多数浏览器中都不会 存在问题，但早上测试的同学会提出了一个bug：在安卓手机的微信自带浏览器中，这个是失效的，并没有跳转；原来的代码：window.location.reload(location.href);初步判断可能是缓存的问题，首先想到的解决办法就是在要跳转的url后面加个时

---

## 188. [解决安卓微信浏览器中location.reload 或者 location.href失效的问题 自动刷新](https://blog.csdn.net/Lpandeng/article/details/71249046)

tips("登录成功",function(){window.location.href="http://\*\*\*.com.cn/repair?pfid=1&"+Date.parse(new Date());});

---

## 189. [js 验证码 倒计时60秒](https://blog.csdn.net/Lpandeng/article/details/71216948)

var mobile = ""; var iCode = ""; var wait = 60; $(function() { $("#btn").click(function() { $(this).css({"border-color":"#ccc","color":"#ccc"}); time(this); var that = $(thi

---

## 190. [微信端用的QQ浏览器， QQ浏览器X5内核问题汇总](https://blog.csdn.net/Lpandeng/article/details/71196346)

重要更新，X5内核即将更新为Blink内核，到时候下面的这些问题将全部被修复。X5内核开发团队也给开发者们提供了不少指引，推荐关注： http://x5.tencent.com/guide?id=2001@2016-04-05常常被人问及微信中使用的X5内核的问题，其实我也不是很清楚，只知道它是基于Android 4.2的webkit，版本号是webkit 534。

---

## 191. [jq 获取用户选择的：性别，所在地 等](https://blog.csdn.net/Lpandeng/article/details/71191687)

//=============客户个人信息修改$(function() { $(".editbtn1").click(function() { var name = $(".right input[class=input]").val(); var Sex = $('input:radio[name="Sex"]:checked').val(); var pr = $('selec

---

## 192. [获取自己的定位（ＧＰＳ）然后转换成百度地图坐标](https://blog.csdn.net/Lpandeng/article/details/71169784)

body, html, #allmap { width: 100%; height: 100%; overflow: hidden; margin: 0; font-family: "微软雅黑"; } --> 浏览器定位 // 百度地图API功能// 获取自己的位置gps

---

## 193. [调取微信相机相册中的图片>发送](https://blog.csdn.net/Lpandeng/article/details/71169722)

wx.config({ debug: false,//调试模式 appId: 'wxc4d4654a04ed05dd', timestamp: 1493876305, nonceStr: 'fjZ3bUEdFztuoWSM', signature: '09db5c20479c943748dc3063e0deb0e293f5eddd', jsApiLi

---

## 194. [如何给自己的网站的评论功能](https://blog.csdn.net/Lpandeng/article/details/62054664)

可以使用第三方评论服务。http://www.pinglun.la/ 评论啦http://www.denglu.cc/pinglun/index.html 灯鹭网http://www.uyan.cc/ 友言多说  http://duoshuo.com/https://www.

---

## 195. [js 资源大全](https://blog.csdn.net/Lpandeng/article/details/60317569)

转自：http://bigdata.evget.com/post/1198.html包管理器管理着 JavaScript 库，并提供读取和打包它们的工具。npm：npm 是 JavaScript 的包管理器。官网Bower：一个 web 应用的包管理器。官网component：能构建更好 web 应用的客户端包管理器。官网spm：全新的静态包管理器。官网

---

## 196. [div css](https://blog.csdn.net/Lpandeng/article/details/60317133)

传送门 https://buluo.qq.com/p/detail.html?bid=314687&pid=3951568-1488176075

---

## 197. [BOM 页面尺寸位置等知识点](https://blog.csdn.net/Lpandeng/article/details/60150064)

var d1 = document.getElementById("d1"); // 1.style属性里面存储的属性值必须是行内的，在内联和外联样式规则里面的这些尺寸是不能被读取的，所以千万不要靠这些值来当做页面上给元素位置尺寸的依据 console.log([d1.style.width, d1.style.height, d1.style.borderWidth]); /

---

## 198. [事件监听](https://blog.csdn.net/Lpandeng/article/details/60149945)

var d1 = document.getElementById("d1"); var d2 = document.getElementById("d2"); // d1.onclick = function(e){ // } 绑定事件 // d1.onclick = null; 解绑事件 // 事件监听，domobj.addEventListener(事件类型, 绑定

---

## 199. [取消事件的默认行为](https://blog.csdn.net/Lpandeng/article/details/60149901)

www.baidu.com var a = document.querySelector("a"); var isFirst = true; a.addEventListener("click", function(){ if (isFirst) { // cancelable表示事件是否可以取消默认行为，这是在事件 对象 在创建的时候就已经决定的

---

## 200. [ionic 修改图标，启动图](https://blog.csdn.net/Lpandeng/article/details/60145596)

只需把resources 中的 安卓和ios 文件包（里面都是图片）删除，然后将其中的两个图片换成相应大小的图片和启动图，configxml中删除相应的安卓ios图片路径（下面实例代码），终端输入一下命令ionic resources —icon ionic resources —splash 就会自动生成。platform 中的图片路径删除platfo

---

## 201. [js 资源大全](https://blog.csdn.net/Lpandeng/article/details/60317569)

转自：http://bigdata.evget.com/post/1198.html包管理器管理着 JavaScript 库，并提供读取和打包它们的工具。npm：npm 是 JavaScript 的包管理器。官网Bower：一个 web 应用的包管理器。官网component：能构建更好 web 应用的客户端包管理器。官网spm：全新的静态包管理器。官网

---

## 202. [div css](https://blog.csdn.net/Lpandeng/article/details/60317133)

传送门 https://buluo.qq.com/p/detail.html?bid=314687&pid=3951568-1488176075

---

## 203. [BOM 页面尺寸位置等知识点](https://blog.csdn.net/Lpandeng/article/details/60150064)

var d1 = document.getElementById("d1"); // 1.style属性里面存储的属性值必须是行内的，在内联和外联样式规则里面的这些尺寸是不能被读取的，所以千万不要靠这些值来当做页面上给元素位置尺寸的依据 console.log([d1.style.width, d1.style.height, d1.style.borderWidth]); /

---

## 204. [事件监听](https://blog.csdn.net/Lpandeng/article/details/60149945)

var d1 = document.getElementById("d1"); var d2 = document.getElementById("d2"); // d1.onclick = function(e){ // } 绑定事件 // d1.onclick = null; 解绑事件 // 事件监听，domobj.addEventListener(事件类型, 绑定

---

## 205. [取消事件的默认行为](https://blog.csdn.net/Lpandeng/article/details/60149901)

www.baidu.com var a = document.querySelector("a"); var isFirst = true; a.addEventListener("click", function(){ if (isFirst) { // cancelable表示事件是否可以取消默认行为，这是在事件 对象 在创建的时候就已经决定的

---

## 206. [ionic 修改图标，启动图](https://blog.csdn.net/Lpandeng/article/details/60145596)

只需把resources 中的 安卓和ios 文件包（里面都是图片）删除，然后将其中的两个图片换成相应大小的图片和启动图，configxml中删除相应的安卓ios图片路径（下面实例代码），终端输入一下命令ionic resources —icon ionic resources —splash 就会自动生成。platform 中的图片路径删除platfo

---

## 207. [JS的十大经典算法排序 》》](https://blog.csdn.net/Lpandeng/article/details/53713503)

http://www.cnblogs.com/dushao/p/6004883.html

---

## 208. [canvas画布之》》》》》》打飞机游戏](https://blog.csdn.net/Lpandeng/article/details/53710982)

开始游戏

---

## 209. [js>>>>范围之内随机数。](https://blog.csdn.net/Lpandeng/article/details/53711237)

var 随机变量  = randFn（20，30）；：产生20-30之间的随机数；；键盘监听：用上下左右键 控制物体上下左右移动移动//键盘监听事件 document.onkeydown = function(e){ switch(e.keyCode){ case 37: //左 hero.left = true; he

---

## 210. [js 》》判断xx（图片等）是否加载成功的方法 》》》》》》》》》打飞机中的代码块](https://blog.csdn.net/Lpandeng/article/details/53711183)

// 游戏资源正在加载 >>isloadingFinish = true; //开始加载所有资源 var imgs = ["img/background.png", "img/bomb.png", "img/bullet1.png", "img/bullet2.png", "img/enemy1.png", "img/enemy2.png", "img/enemy3.png", "img/

---

## 211. [键盘键码一览表](https://blog.csdn.net/Lpandeng/article/details/53710564)

按键键码按键键码A656(数字键盘)102B667(数字键盘)103C678(数字键盘)104D689(数字键盘)105

---

## 212. [js 常见错误类型](https://blog.csdn.net/Lpandeng/article/details/53691742)

（1）SyntaxErrorSyntaxError是解析代码时发生的语法错误// 变量名错误 var 1a; // 缺少括号 console.log 'hello');（2）ReferenceErrorReferenceError是引用一个不存在的变量时发生的错误。unknownVariable // ReferenceError: unknownV

---

## 213. [document.body、document.documentElement和window获取视窗大小的区别](https://blog.csdn.net/Lpandeng/article/details/53674171)

2015-3-27 $(window).height(); 才是窗口的宽高，而且一直不变 document.body.clientHeight，在文档内容有滚动条的时候远大于$(window).height(); 实际例子，向下滑动判断 $(document).height() - $(window).scrollTop() - $(window).height()

---

## 214. [css3动画简介以及动画库animate.css的使用](https://blog.csdn.net/Lpandeng/article/details/53672856)

此博主总结的挺好，不在复制过来 了。。。。http://www.cnblogs.com/2050/p/3409129.html

---

## 215. [css3之canvas 基础](https://blog.csdn.net/Lpandeng/article/details/53644263)

DOCTYPE html>html>head>metacharset="utf-8">title>title>styletype="text/css">#myCanvas{box-shadow:10px 10px10px black;}style>head>body>canvasid="myCanvas" wi

---

## 216. [hbuild 快捷键](https://blog.csdn.net/Lpandeng/article/details/53645294)

图片来自：http://www.bcty365.com/content-146-2530-1.html

---

## 217. [网页布局之》》》》弹性盒子》》》](https://blog.csdn.net/Lpandeng/article/details/53612826)

网页弹性盒子》》》》box-flex 属性  按比例占据父元素的尺寸。定义两个可伸缩的 p 元素。如果父元素的总宽度是 300 像素，则 #p1 的宽度是 100 像素，而 #p2 的宽度是 200 像素：#p1{-moz-box-flex:1.0; /_ Firefox _/-webkit-box-flex:1.0; /_ Safari 和 Chrome _/box-fl

---

## 218. [CSS布局奇葩技巧之--各种居中](https://blog.csdn.net/Lpandeng/article/details/53608579)

居中是我们使用css来布局时常遇到的情况。使用css来进行居中时，有时一个属性就能搞定，有时则需要一定的技巧才能兼容到所有浏览器，本文就居中的一些常用方法做个简单的介绍。注：本文所讲方法除了特别说明外，都是兼容IE6+、谷歌、火狐等主流浏览器的。先来说几种简单的、人畜无害的居中方法1. 把margin设为auto具体来说就是把要居中的元素的margin-left和m

---

## 219. [css选择器中:first-child与:first-of-type的区别](https://blog.csdn.net/Lpandeng/article/details/53608521)

:first-child选择器是css2中定义的选择器，从字面意思上来看也很好理解，就是第一个子元素。比如有段代码：p:first-child  匹配到的是p元素,因为p元素是div的第一个子元素；h1:first-child  匹配不到任何元素，因为在这里h1是div的第二个子元素，而不是第一个；span:first-child  匹配不到任何元素，因为在这里两个

---

## 220. [实现网页图片不断闪烁](https://blog.csdn.net/Lpandeng/article/details/53606234)

暂无描述

---

## 221. [实现网页随机登陆验证码功能](https://blog.csdn.net/Lpandeng/article/details/53606218)

暂无描述

---

## 222. [实现网页图片渐变](https://blog.csdn.net/Lpandeng/article/details/53606192)

暂无描述

---

## 223. [实现网页背景随机变化](https://blog.csdn.net/Lpandeng/article/details/53606144)

暂无描述

---

## 224. [网页中最常用的JS代码（js禁止右键、禁止复制）](https://blog.csdn.net/Lpandeng/article/details/53586913)

body oncopy="returnfalse">  禁止复制input type=""name="" id=""value="" onpaste="returnfalse" />  禁止粘贴

---

## 225. [一些js题](https://blog.csdn.net/Lpandeng/article/details/53543685)

Code Oneif (!("a" in window)) {var a = 1;}alert(a);这个奇怪的代码似乎是这样: “如果window 没有属性a, 定义一个变量a并且赋值1”, 你可能会认为应该alert 1。 实际上，alert的是”undefined”。 为了理解发生了什么，你应该知道JavaScript的四件事。

---

## 226. [js中的tostring()方法](https://blog.csdn.net/Lpandeng/article/details/53582771)

今天看JS学习资料，看到一个toString()方法，在JS中，定义的所有对象都具有toString()方法。Number类型的toString()方法比较特殊，有默认模式和基模式两种。 默认模式的例子：var num1 = 10;var num2 = 10.0;alert(num1.toString());//输出10alert(num2.

---

## 227. [ease,seae-in,ease-in-out,ease-out,效果](https://blog.csdn.net/Lpandeng/article/details/53557838)

值描述linear规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。(匀速)ease规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）（相对于匀速，中间快，两头慢）。ease-in规定以慢速开始的过渡效果（等于 cubic-

---

## 228. [获取自己的定位（ＧＰＳ）然后转换成百度地图坐标](https://blog.csdn.net/Lpandeng/article/details/71169784)

body, html, #allmap { width: 100%; height: 100%; overflow: hidden; margin: 0; font-family: "微软雅黑"; } --> 浏览器定位 // 百度地图API功能// 获取自己的位置gps

---

## 229. [调取微信相机相册中的图片>发送](https://blog.csdn.net/Lpandeng/article/details/71169722)

wx.config({ debug: false,//调试模式 appId: 'wxc4d4654a04ed05dd', timestamp: 1493876305, nonceStr: 'fjZ3bUEdFztuoWSM', signature: '09db5c20479c943748dc3063e0deb0e293f5eddd', jsApiLi

---

## 230. [如何给自己的网站的评论功能](https://blog.csdn.net/Lpandeng/article/details/62054664)

可以使用第三方评论服务。http://www.pinglun.la/ 评论啦http://www.denglu.cc/pinglun/index.html 灯鹭网http://www.uyan.cc/ 友言多说  http://duoshuo.com/https://www.

---

## 231. [项目开发心得](https://blog.csdn.net/Lpandeng/article/details/59119596)

■用例一完全能够运行后再开发用例二。厨房里有一种说法正好可以印证这个问题：“做好一盘菜后你再做下一盘”．对于软件开发来说一个最大的问题就是人们喜欢并行开发多个任务。因为不可避免的，我们设计的功能中总会有一部分会被放弃砍掉，如果提前开发，很可能做无用功。一次只开发一个用例（或很少几个用例，这根据你的开发团队的大小而定）；让这个用例功能完整；让相应的测试用例都能通过；相应的文稳都补齐；只有在当前的用例

---

## 232. [网页夜间模式](https://blog.csdn.net/Lpandeng/article/details/57122927)

.cover{ position:fixed; top: 0px; left: 0px; outline:5000px solid rgba(0, 0, 0, 0.3); z-index: 99999;}fsdgsgsgsg5ter var brightness;//显示遮罩function cover(brightness) {

---

## 233. [ionic笔记(一)](https://blog.csdn.net/Lpandeng/article/details/57080316)

ionic 图标  ：  https://icomoon.io/　　　　　　　　　　　　http://www.cnblogs.com/lazaphy/p/5826417.html　　　　　　　　　　　　https://my.oschina.net/igeeker/blog/378847　　　　　　　　　　　　       //请求        $http.get(".

---

## 234. [由父类index 找子类index](https://blog.csdn.net/Lpandeng/article/details/57080235)

var minIndex = index;      var maxIndex = $(event.target).parents(".bigItem").index();      console.log("大的:" + maxIndex);      console.log("晓得:" + minIndex);

---

## 235. [ionic 视频](https://blog.csdn.net/Lpandeng/article/details/56486736)

八、Angularjs自定义服务 provide里provider方法 以及factory、service方法以及provider供应商的概念Angular 提供了3种方法来创建并注册我们自己的服务。1. ProviderProviders 是唯一一种你可以传进 .config() 函数的 service。当你想要在 service 对象启用之前，先进行模块范围的配置，那就

---

## 236. [解决 ionic 轮播图 第一次加载不出来（需要变动一下大小才可以显示）](https://blog.csdn.net/Lpandeng/article/details/56292738)

$http({  url:"http://59.110.139.104:3000/wy?myUrl="+$scope.url, metheod:"GET"}) .then(function (res) { console.log(res); $scope.data = res.data.top_stories;    console.log($scope.data);

---

## 237. [解决ionic 上拉加载组件 ion-infinite-scroll自动调用多次的问题或禁止第一次加载](https://blog.csdn.net/Lpandeng/article/details/56282726)

ionic 中一个上拉刷新的组件 ion-infinite-scroll，如果页面未填充满页面高度，会自动检测并无限调用多次加载更多的函数；当然，主要会导致首次调用的时候，会执行几次加载更多的函数；解决方案： 在ion-infinite-scroll标签中，设置immediate-check="false"；这个属性设置了:是否在页面加载后立刻触发on-infinite的方

---

## 238. [前端客 中的各种tip](https://blog.csdn.net/Lpandeng/article/details/55517813)

http://www.qdker.com/archives/384.html

---

## 239. [js 一键破解加密网页](https://blog.csdn.net/Lpandeng/article/details/55517771)

javascript :s=document.documentElement.outerHTML;document.write('');document.body.innerText=s; 在浏览器地址中输入。。，，，javascript+copy

---

## 240. [php 字符串拼接](https://blog.csdn.net/Lpandeng/article/details/55194426)

字符串的表示PHP中字符串的表示可以用双引号，也可以用单引号，但是两者之间有些区别。字符串中有变量的时候，单引号仅输出变量名，而不是值：1 php2 $color = "red";3  echo "Roses are$color";4 echo "";5 echo 'Roses are $color';6 ?>　　　　输出：Roses are

---

## 241. [form](https://blog.csdn.net/Lpandeng/article/details/55104307)

刘翔宇  17:26:51【链接】如何通过iframe以post方式提交form表单http://www.cnblogs.com/lazaphy/p/5826417.html刘翔宇  17:28:00【链接】form表单提交到iframe遇到的问题-DemoDoc的个人https://my.oschina.net/igeeker/blog/378847

---

## 242. [php 操作(新浪云)mysql数据库](https://blog.csdn.net/Lpandeng/article/details/55094589)

连接数据库：$conn = new mysqli(SAE_MYSQL_HOST_M, SAE_MYSQL_USER, SAE_MYSQL_PASS , SAE_MYSQL_DB);//读取数据$sql = "SELECT mz, age, gender FROM first";$result = $conn->query($sql);if ($result-

---

## 243. [安装ionic ,android studio,ios 等环境](https://blog.csdn.net/Lpandeng/article/details/54930773)

安装ionic 终端命令：   npm install -g ionic@beta —registry=https://registry.npm.taobao.org　　　　　　　　　　　　  15:42:401环境安装成功之后2：ionic start myapp…..生成项目。，：ionic start myApp sidemenu　　　　　　　　　　　　  16:25:283

---

## 244. [微信公众号](https://blog.csdn.net/Lpandeng/article/details/54585928)

获取全局 的access_token:把下面的appid，secre 换成自己的。，然后回车，就得到了。每过7200秒会失效，，，然后粘贴底部菜单代码即可https://api.weixin.qq.com/cgi-bin/token?grant_type=client_credential&appid=APPID&secret=APPSECRET网页授权：access_to

---

## 245. [微信，新浪云，配置php,验证](https://blog.csdn.net/Lpandeng/article/details/54574514)

header('Content-type:text');define("TOKEN", "weixin");$wechatObj = new wechatCallbackapiTest;if (!isset($\_GET['echostr'])) {    $wechatObj->responseMsg();}else{    $wechatObj->vali

---

## 246. [git](https://blog.csdn.net/Lpandeng/article/details/54138631)

代码与仓库：commit　　　　　　　　　　　　  14:57:05git init  把次文件夹 弄成本地文件夹　　　　　　　　　　　　  14:58:15本地仓库与远程仓库：pull push　　　　　　　　　　　　  15:02:22defaults write com.apple.finder AppleShowAllFiles -boolean true ; ki

---

## 247. [mongodb](https://blog.csdn.net/Lpandeng/article/details/54138615)

mongod --dbpath=/Users/qingyunh5/Desktop/dataBase　　　　　　　　　　　　  10:00:15打开数据库　　　　　　　　　　　　  10:08:39mongo 进入数据库环境　　　　　　　　　　　　  10:09:15mongo 进入数据库环境   对数据库进行增删改查　　　　　　　　　　　　  10:09:47exi

---

## 248. [配置brew 环境](https://blog.csdn.net/Lpandeng/article/details/54096489)

指令：    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

---

## 249. [node.js 和WebStorm](https://blog.csdn.net/Lpandeng/article/details/53955455)

终端：contral+c 停止  contral+c contral+c 退出webstrom 的破解码：http://idea.imsxm.com/node。js    初始化第一个项目  npm init  ：在终端先进入该文件的位置然后   初始化，之后就该文件就有配置文件了安装一个模块 npm install xxx ：如要单纯的安装某个模块就这样。安装一个模块同事记录

---

## 250. [app接口抓包](https://blog.csdn.net/Lpandeng/article/details/53928511)

一级页面http://qt.qq.com/php_cgi/news/php/varcache_getnews.php?id=12&page=0&plat=android&version=9715二级页面http://apps.game.qq.com/lol/Go/video/videoInfo?p1=47616&type=jsonp&p2=MERGE三级页面 根

---

## 251. [监听网络状态](https://blog.csdn.net/Lpandeng/article/details/53928491)

//监听网络状态 document.addEventListener("netchange", onNetChange, false);刘翔宇 09:40:03//监听网络状态 function onNetChange() { var nt = plus.networkinfo.getCurrentType(); switch(nt) { case

---

## 252. [getter ,setter](https://blog.csdn.net/Lpandeng/article/details/53769511)

对象点属性出现在=左边就setter。其他任何地方都叫getter

---

## 253. [canvas 之图片模糊&马赛克](https://blog.csdn.net/Lpandeng/article/details/53748835)

canvas{ border: 1px solid red; } btn 模糊 马赛克 var canvas1 = document.getElementById("vanvas1"); var canvas2 = document.getElementById("vanvas2"); var context1 = ca

---

## 254. [swap函数](https://blog.csdn.net/Lpandeng/article/details/53713755)

你会写几种swap函数？      swap函数估计是一个各种各样程序都会频繁用到的子程序，可是你知道它究竟有多少种不同的写法吗？下面我就列举我知道的几种swap函数来跟大家分享一下。(1)经典型---嫁衣法无论是写程序还是干其他事情，一旦涉及到交换，就总是会遇到第三方。这个第三方可能是公正的监督者，也可能是一个徒为他人做嫁衣的可怜虫。在经典法的交换程序中，我们就需

---
