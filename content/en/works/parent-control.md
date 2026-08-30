---
title: "ParentControl Guard · OpenWrt Parental Control System"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "A fine-grained parental control and network behavior management system for OpenWrt routers powered by Go and Linux kernel L7 DPI."
summary: "An in-depth case study of ParentControl Guard: architecture design, kernel-level DPI enforcement, anti-bypass mechanisms, and cross-platform companion apps."
tags: ["OpenWrt", "Go", "DPI", "SwiftUI", "Networking", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 Background & Motivation

In home networks, managing children's screen time and preventing addiction to mobile games or short-form video apps is a common challenge for parents. However, conventional solutions suffer from fundamental limitations:

1. **DNS-Based Filtering Is Fragile**: Easily bypassed by switching to private DNS, DoH (DNS-over-HTTPS), or DoT (DNS-over-TLS on port 853/443).
2. **Transparent Proxy Conflicts**: OpenWrt routers often run routing proxies (such as OpenClash or Passwall), which intercept traffic before standard firewall rules take effect.
3. **Privacy Concerns in Commercial Solutions**: Most proprietary routers send unencrypted browsing logs to cloud vendors.

**ParentControl Guard** was engineered to solve these issues: **100% on-device execution, kernel-level packet inspection, lightweight single-binary deployment, and multi-layered anti-bypass defense**.

---

## 🚀 Key Features & Architectural Goals

- **🎮 Kernel-Level L7 DPI Engine**: Leverages `kmod-oaf` in the Netfilter `mangle` table `PREROUTING` chain (highest priority) to identify and drop packets from games, short videos, and streaming services before proxy interception.
- **⏱️ Flexible Time Scheduling & Quota System**: Configurable multi-interval lockout schedules (supporting overnight intervals), Token Bucket daily active usage quotas, and instant lock with temporary reward extensions (+15m/+30m/+1h).
- **🛡️ Robust Anti-Bypass Protections**: Enforces Google/Bing/Baidu SafeSearch, blocks rogue DoH/DoT ports, and detects randomized MAC addresses.
- **📱 Standalone Responsive Web UI**: Single Go binary with embedded assets and 8 international languages, secured by a 4-digit PIN lock.
- **🍏 Native Companion Apps with Shared Swift Core**: Native iOS (SwiftUI) and Android apps sharing a pure Swift business and networking engine (`ParentControlCore`) via C-FFI / JNI.
- **☁️ Dual Cloud Relay Modes**: Supports Cloudflare Workers (Serverless + KV) and self-hosted Go WebSocket relays for sub-second remote control outside the home network without a public IP.

---

## 🏗️ System Architecture & Data Pipeline

```text
[ Client Devices on LAN ]
       │ (Raw IP Traffic)
       ▼
[ Netfilter: mangle PREROUTING ] ───► [ kmod-oaf L7 DPI Signature Matcher ]
       │                                              │ (Blacklisted App Detected)
       ├──────────────────────────────────────────────┴──► [ Immediate DROP / REJECT ]
       ▼ (Permitted Safe Traffic)
[ Forwarding / Routing / Proxy ]

─────────────────────────────────────────────────────────────────────────────
[ Go Daemon (ParentControl Guard) ]
       ├── Local SQLite & Configuration Storage
       ├── Embedded Web Console
       ├── Token Bucket Active-Duration Calculator
       └── WebSocket Client ◄───► [ Cloudflare Workers Relay ] ◄───► [ Mobile App ]
```

---

## 🖼️ User Interface & Showcase

### 1. Modern Web Dashboard Overview

![Dashboard Overview](/images/projects/parent-control/02_dashboard_overview.png)

### 2. LAN Device Discovery & Real-Time Management

![LAN Devices](/images/projects/parent-control/03_lan_devices.png)

### 3. Kernel DPI Application Signature Library

![DPI Signatures](/images/projects/parent-control/04_dpi_signatures.png)

### 4. Rule Configuration & PIN Security Lock

![Edit Member Rules](/images/projects/parent-control/05_edit_member_rules.png)
![PIN Lock](/images/projects/parent-control/01_pin_lock.png)

---

## 🛠️ Engineering Highlights

1. **Zero External Dependency Binary**: Uses Go `embed.FS` to bundle all web assets into a single lightweight binary, ensuring effortless installation on flash-constrained router hardware.
2. **Noise-Filtering Traffic Algorithm**: Background push notifications and WebSocket heartbeats are filtered out so that only real human interactive usage counts toward the daily screen quota.
3. **Cross-Platform Swift Core**: Rather than rewriting network state machines twice, the core logic is written in Swift and exposed to Android via C-FFI / JNI.

---

## 📈 Implementation Status

- [x] Multi-architecture OpenWrt packages (`x86_64`, `aarch64`, `arm`, `mips`)
- [x] Kernel L7 DPI signature matching & packet dropping
- [x] Responsive Web console with PIN lock screen
- [x] Multi-language localization (EN / ZH / JA / DE / FR / ES / RU / ZHTW)
- [x] Cloudflare Workers bidirectional relay
- [x] Native SwiftUI client integration

---

## 🔗 Links

- **Project Type**: Proprietary Gateway System (Private Deployment)
- **Platform**: OpenWrt 21.02 - 23.05
