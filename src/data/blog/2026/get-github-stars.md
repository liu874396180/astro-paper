---
author: lpd
pubDatetime: 2026-01-10T14:32:14.000+08:00
modDatetime:
title: 几种获取自己github账户下已star项目的方案实践
featured: false
draft: false
tags:
  - github stars
  - project
description: 几种获取github star项目的方案，生成直观的star项目列表，以便快速方便的查阅
---

## 目录

## 方案一：getMyGithubStars（一次性爬取）

**GitHub 地址**：https://github.com/liu874396180/getMyGithubStars

**描述**：获取自己账号下所有 star 的项目，在本地生成 md 文档列表

## 方案二：getUserStarsToPage（定时爬取）

**GitHub 地址**：https://github.com/liu874396180/getUserStarsToPage

**演示页面**：https://get-user-stars-to-page.vercel.app/

**描述**：定时抓取 Stars 项目，快速访问并检索项目

## 方案三：使用 Notion 管理 GitHub Star 项目

**GitHub 地址**：https://github.com/liu874396180/github-notion-star

**效果预览**：

- 演示链接：https://www.notion.so/Github-Notion-Star-2e3d73fa802581fe8c1bf240d1c36bc1?source=copy_link
- 预览图：

![预览图](https://i.loli.net/2021/10/08/ioRfaZWerTgBuAO.png)

**描述**：使用 Notion 创建一个数据库，将 GitHub Star 项目添加到数据库中，并使用 Notion 的 API 获取数据，将数据保存到数据库中，并使用 Notion 的 Web 页面进行展示。
