---
title: "ParentControl Guard · OpenWrt 家长控制卫士"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "基于 Go 与 Linux 内核级 L7 DPI 深度包检测的 OpenWrt 细粒度家长控制与上网行为安全管理系统。"
summary: "深度解析 ParentControl Guard 系统的设计背景、内核 DPI 技术选型、防绕过架构及跨平台客户端实现。"
tags: ["OpenWrt", "Go", "DPI", "SwiftUI", "Networking", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 项目背景与初衷

在家庭网络环境中，青少年过度沉迷网络游戏、短视频与社交媒体是许多家长面临的痛点。然而市面上的传统方案存在诸多局限：

1. **传统 DNS 拦截容易绕过**：只需手动修改手机 DNS 或使用 DoH/DoT (853/443端口) 即可轻易失效。
2. **旁路代理劫持冲突**：家庭软路由普遍运行 OpenClash / Passwall 等透明代理工具，传统 IP/域名规则无法在代理前截流。
3. **商业方案臃肿且依赖云端**：许多商业路由器需要上传完整上网记录到第三方服务器，存在严重隐私泄露风险。

**ParentControl Guard** 由此诞生：**100% 本地运行、内核级精准识别、单二进制轻量部署、多层立体防绕过**的开源级软路由家长控制系统。

---

## 🚀 核心设计目标与系统特性

- **🎮 内核级 L7 DPI 引擎**：基于 `kmod-oaf` 内核模块与协议特征库，在数据包到达代理前于 `mangle` 表 `PREROUTING` 第一优先级截杀，精准识别数百款主流游戏、短视频与直播平台。
- **⏱️ 多时段计划与活跃限额**：支持跨夜时段定时锁网，结合真实人机交互流量的 Token Bucket 每日使用额度，支持一键临时断网与奖励加时。
- **🛡️ 严苛防绕过体系**：强制锁定 Google/Bing/Baidu 青少年 SafeSearch，封锁外部公共 DoH/DoT 端口，有效防范随机 MAC 地址欺骗。
- **📱 响应式 Web 控制台**：单 Go 二进制文件内嵌全部静态资源与 8 国语言包，4 位数字 PIN 锁安全保护。
- **🍏 原生跨平台移动端**：iOS (SwiftUI) 与 Android 原生客户端，通过 C-FFI / JNI 共享纯 Swift 跨平台业务与网络核心 (`ParentControlCore`)。
- **☁️ 双模式云端中继**：支持 Cloudflare Workers 无服务器中继或自建 Go WebSocket 中继，家长在 4G/5G 外网环境下无需公网 IP 即可远程秒级管控。

---

## 🏗️ 系统架构与数据流转

```text
[ 局域网终端设备 ]
       │ (原始流量)
       ▼
[ Linux 内核 Netfilter: mangle PREROUTING ] ───► [ kmod-oaf L7 DPI 协议特征检测 ]
       │                                                    │ (匹配黑名单特征)
       ├────────────────────────────────────────────────────┴──► [ 立即 DROP / REJECT ]
       ▼ (放行安全流量)
[ 路由转发 / 透明代理 / 出网 ]

─────────────────────────────────────────────────────────────────────────────
[ Go 守护进程 (ParentControl Daemon) ]
       ├── 本地 SQLite / 配置存储
       ├── 内嵌 Web 控制台 (支持手机端 / 桌面端)
       ├── 活跃时长 Token Bucket 计算引擎
       └── WebSocket 客户端 ◄───► [ Cloudflare Workers / 云端中继 ] ◄───► [ 家长手机 App ]
```

---

## 🖼️ 系统界面与功能预览

### 1. 现代化 Web 控制台与主看板

![主控制台概览](/images/projects/parent-control/02_dashboard_overview.png)

### 2. 局域网设备管理与实时状态

![局域网设备管理](/images/projects/parent-control/03_lan_devices.png)

### 3. 内核级 L7 DPI 应用特征库与封禁规则

![DPI 应用特征库](/images/projects/parent-control/04_dpi_signatures.png)

### 4. 成员多时段规则配置与安全锁屏

![成员规则配置](/images/projects/parent-control/05_edit_member_rules.png)
![PIN 安全锁屏](/images/projects/parent-control/01_pin_lock.png)

---

## 🛠️ 技术攻坚与亮点

1. **零外部依赖的 Go 单文件部署**：通过 Go 1.16+ `embed.FS` 将前端 Vue/HTML 资源全量打包至单一二进制文件，在 OpenWrt 存储受限（如 128MB Flash）设备上也能秒级安装运行。
2. **真实人机交互流量心跳过滤**：针对微信/后台推送长连接持续产生的微弱心跳包，研发了底噪流量过滤算法，只有产生真实人机交互数据流时才计入活跃使用时长。
3. **跨平台 Swift 核心复用**：移动端没有采用繁琐的双平台重复编写网络与协议层，而是利用 Swift 的跨平台 C-FFI 能力，让 Android 端通过 JNI 调用同一套 Swift 状态管理核心。

---

## 📈 当前完成度

- [x] OpenWrt 21.02 / 22.03 / 23.05 架构编译支持 (`x86_64`, `aarch64`, `arm`, `mips`)
- [x] 内核级 L7 DPI 协议识别与精准丢包拦截
- [x] 现代化响应式 Web 控制台与 PIN 密码锁
- [x] 8 种国际化语言支持 (中/英/日/德/法/西/俄/繁)
- [x] Cloudflare Workers / Go WebSocket 云端双向中继
- [x] 纯 SwiftUI iOS 客户端原型与跨平台核心联调

---

## 🔗 相关链接

- **项目属性**: 自研软路由系统（私有化部署，未开源）
- **运行平台**: OpenWrt 21.02 - 23.05
