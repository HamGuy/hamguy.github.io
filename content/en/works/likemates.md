---
title: "LikeMates (Trovault) · X Likes & Bookmarks Local Manager"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "A privacy-first Chrome browser extension to sync, organize, and full-text search your X (Twitter) likes and bookmarks locally."
summary: "An in-depth case study of LikeMates (Trovault): Chrome Manifest V3 architecture, 100% on-device IndexedDB storage, media filtering, and 5-star rating on the Chrome Web Store."
tags: ["Chrome Extension", "Manifest V3", "TypeScript", "IndexedDB", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 Background & Motivation

While browsing X (formerly Twitter), users frequently like and bookmark high-value engineering threads, design inspirations, code repositories, and video demos. However, the default experience has severe drawbacks:

1. **Inadequate Search Capabilities**: Native X search does not allow accurate keyword filtering across personal bookmarks.
2. **Permanent Data Loss on Deletion**: If an author deletes a tweet or deactivates their account, bookmarked insights vanish forever.
3. **Unsorted Clutter**: Media, links, and text are mixed without granular media categorization.

**LikeMates (Trovault)** was built under the motto **“Never lose what you loved”**: **Local-first synchronization, media filtering, and sub-second offline search in a Chrome extension**.

---

## 🚀 Key Features

- **❤️ Incremental & Full Sync**: Automatically or on-demand sync liked and bookmarked tweets directly from X.
- **🔒 100% On-Device Privacy (IndexedDB)**: All tweet texts, author handles, and media metadata are stored in the browser's local IndexedDB. Zero external servers or third-party API keys required.
- **🔍 Sub-Second Full-Text Search**: Instantly query your archive by keyword across tweet bodies, author names, and handles.
- **📂 Smart Media Filters**: Instant 1-click filtering by **Images**, **Videos**, **Links**, and **Pure Text**.
- **📅 Time Machine Navigation**: Easily filter items by today, this week, this month, or custom date ranges.

---

## 🖼️ Interface Showcase

![LikeMates Library](/images/projects/likemates/library.jpg)
![LikeMates Settings](/images/projects/likemates/settings.jpg)

---

## 🏗️ Architecture (Manifest V3)

```text
[ X.com Web Page Context ]
       │ Content Script (DOM Observer & Stream Parser)
       ▼
[ Background Service Worker (Manifest V3) ]
       │ Structured Tweet Normalization
       ▼
[ Browser-Local IndexedDB ]
       │
       ├─► [ SidePanel / Popup UI (TypeScript + Tailwind CSS) ]
       ├─► [ Local Tokenized Search Engine ]
       └─► [ JSON / CSV Export Pipeline ]
```

---

## 📈 Shipping, Validation & Ratings

- [x] **Live on Chrome Web Store** with **5.0 Star Rating (★★★★★)**
- [x] Engineered to Chrome Extension Manifest V3 specifications
- [x] Multi-language store listings and UI localization (7 languages: EN / ZH / JA / DE / FR / ES / KO)
- [x] Offline export & data portability features

---

## 🔗 Install & Links

- **Chrome Web Store**: [https://chromewebstore.google.com/detail/trovault-twitter-likes-bo/jamclmmnnannpcflkjimkogjpmknlgcg](https://chromewebstore.google.com/detail/trovault-twitter-likes-bo/jamclmmnnannpcflkjimkogjpmknlgcg)
- **GitHub Repository**: [https://github.com/hamguy](https://github.com/hamguy)
