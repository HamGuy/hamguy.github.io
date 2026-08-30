---
title: "LikeMates (Trovault) · X 收藏与点赞离线管理插件"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "专注于隐私安全的 X (Twitter) 收藏与点赞本地离线管理与即时搜索 Chrome 浏览器扩展插件。"
summary: "解析 LikeMates (Trovault) 的产品设计理念：Manifest V3 架构、纯本地 IndexedDB 存储、多媒体筛选与 Chrome 应用商店 5 星好评交付。"
tags: ["Chrome Extension", "Manifest V3", "TypeScript", "IndexedDB", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 背景与痛点

在日常使用 X (Twitter) 时，用户经常会点赞或收藏大量优质的技术推文、设计灵感、开源项目与视频。然而官方的收藏与点赞功能存在严重痛点：

1. **官方搜索极难用**：无法在自己的 Likes 和 Bookmarks 中进行精准的全文关键词搜索。
2. **推文被删即永久丢失**：原作者销号或删推后，曾收藏的宝贵知识资产瞬间蒸发。
3. **内容杂乱缺乏分类**：图文、视频、链接混杂在一起，难以快速定位。

**LikeMates (Trovault)** 诞生于此：**“Never lose what you loved” —— 纯本地离线同步、多媒体过滤、全文毫秒级索引的 Chrome 扩展插件**。

---

## 🚀 核心功能与特性

- **❤️ 增量与全量离线同步**：自动或手动将 X 上的点赞与书签推文同步到浏览器本地。
- **🔒 100% 本地隐私安全 (IndexedDB)**：所有推文内容、媒体元数据均存储在浏览器本地数据库中，无需任何外部服务器或第三方 API Key。
- **🔍 毫秒级全文检索**：支持按推文正文、作者昵称、Handle 账号即时搜索匹配。
- **📂 智能多媒体分类**：一键过滤 **纯文本 / 图片 / 视频 / 外链**。
- **📅 时间轴时光机**：快速按今天、本周、本月或自定义时间范围回溯历史收藏。

---

## 🖼️ 界面与功能展示

![LikeMates Library](/images/projects/likemates/library.jpg)
![LikeMates Settings](/images/projects/likemates/settings.jpg)

---

## 🏗️ 技术架构 (Manifest V3)

```text
[ X.com 网页上下文 ]
       │ Content Script (DOM 事件与滚动探测)
       ▼
[ Background Service Worker (Manifest V3) ]
       │ 提取推文结构化 JSON (ID, Text, Media, Author, Timestamp)
       ▼
[ 浏览器端 IndexedDB 本地数据库 ]
       │
       ├─► [ SidePanel / Popup 交互界面 (TypeScript + Tailwind CSS) ]
       ├─► [ 本地全文分词检索引擎 ]
       └─► [ JSON / CSV 离线数据导出备份 ]
```

---

## 📈 交付成果与用户口碑

- [x] **Chrome 网上应用店正式上架**，已获 **5.0 满分好评 (★★★★★)**
- [x] 严格遵循 Chrome Manifest V3 最新规范研发与上架审核
- [x] 多语言应用商店物料与本地化适配 (支持中/英/日/德/法/西/韩 7 种语言)
- [x] 完整 PRD 与离线数据备份方案落地

---

## 🔗 安装与体验

- **Chrome 网上应用店**: [https://chromewebstore.google.com/detail/trovault-twitter-likes-bo/jamclmmnnannpcflkjimkogjpmknlgcg](https://chromewebstore.google.com/detail/trovault-twitter-likes-bo/jamclmmnnannpcflkjimkogjpmknlgcg)
- **GitHub 仓库**: [https://github.com/hamguy](https://github.com/hamguy)
