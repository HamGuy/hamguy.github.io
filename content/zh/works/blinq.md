---
title: "Blinq (QuickOpen) · 极速企业 VPN 自动化连接套件"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "轻量级极速企业 VPN 自动化拨号工具，支持 TOTP 动态验证码自动填充、AES-256-GCM 本地安全加密与软路由分流。"
summary: "解析 Blinq (QuickOpen) 的架构设计：解决企业 2FA 动态口令频繁重连痛点、Go 单二进制跨平台实现、本地凭证加密与软路由 Split-Tunneling 分流方案。"
tags: ["Go", "VPN", "Security", "OpenConnect", "Networking", "CLI", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 背景与痛点

在企业远程办公（WFH）或开发调试场景中，工程师经常需要连接基于 **“固定密码 + Google Authenticator 动态 2FA 验证码”** 认证的企业内网 VPN（如 Cisco AnyConnect / OpenConnect）。

**日常痛点**：
1. **频繁断连手动输入极其痛苦**：动态验证码每 30 秒变更，VPN 频繁重连时每次都需拿起手机打开 Authenticator 手动输入，打断心流。
2. **高版本 iOS / 真机调试抓包受限**：iOS 设备直接连接 VPN 后无法使用 Charles/Proxyman 抓包调试内网接口。
3. **软路由原生 LuCI 不支持动态 2FA**：路由器后台仅能保存静态密码，无法自动重连需要 2FA 的企业网络。

**Blinq (QuickOpen)** 诞生于此：“**Blink and you're in.**” —— **全自动计算 TOTP 动态码、本地 AES-256 安全加密存储凭证、秒级一键连接并支持软路由全屋局域网分流 (Split-Tunneling)**。

---

## 🚀 核心功能与特性

- **⚡ 一键极速连通**：基于 RFC 6238 标准自动计算 TOTP 6 位动态码，无缝配合固定密码自动注入 OpenConnect 进程，实现秒级连通。
- **🔒 AES-256-GCM 本地加密存储**：所有账号密码与 TOTP 密钥均在本地加密，数据绝不上传云端，保障企业级凭证安全。
- **🌐 软路由透明分流 (Split-Tunneling)**：支持部署在 OpenWrt 软路由上，自动配置 `tun0` 虚接口与 `dnsmasq` 域名分流，实现家庭局域网内所有设备（包括 iPhone/iPad/电视）免装客户端透明访问企业内网。
- **💻 跨平台轻量支持**：纯 Go 编写单二进制文件，零依赖，跨平台支持 macOS (Apple Silicon & Intel)、Linux 与 Windows。

---

## 🖼️ 界面与视觉预览

![Blinq Preview](/images/projects/blinq/preview.webp)

---

## 🏗️ 系统架构与网络拓扑

```text
[ 开发者电脑 / 局域网设备 ]
       │
       ▼
[ Blinq 核心引擎 (Go) ]
       ├── AES-256-GCM 本地凭证解密
       ├── RFC 6238 TOTP 动态码实时生成
       └── OpenConnect 进程自动调起与管道注入
       │
       ▼
[ VPN 虚拟网卡 (tun0) ]
       │
       ├─► [ 域名 / IP 分流规则 (Split-Tunneling) ] ──► [ 企业内网服务 ]
       └─► [ 常规流量直连 ] ─────────────────────────► [ 公网互联网 ]
```

---

## 🛠️ 研发攻坚与技术亮点

1. **安全加密凭证体系**：设计了基于用户主密码/设备特征派生密钥的 AES-256-GCM 加密配置文件结构，既保证了便捷自动填充，又防止凭证在本地被恶意程序直接窥探。
2. **软路由网络分流与 DNS 防污染**：结合 `vpnc-script` 与 `dnsmasq` 规则，仅将企业内网域名与特定网段路由至 VPN 隧道，其余全网流量保持原生高速直连。

---

## 📈 交付成果与落地

- [x] macOS / Linux / Windows 跨平台 CLI 二进制构建与自动化打包流水线
- [x] OpenWrt 软路由一键透明分流脚本与守护方案
- [x] 现代化产品官方独立站点上线：[https://getblinq.app](https://getblinq.app)

---

## 🔗 相关链接

- **产品官网**: [https://getblinq.app](https://getblinq.app)
