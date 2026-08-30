---
title: "Blinq (QuickOpen) · Automated Enterprise VPN Connectivity Suite"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "A lightweight, automated enterprise VPN connection tool with TOTP auto-generation, AES-256-GCM local encryption, and router split-tunneling."
summary: "An in-depth case study of Blinq (QuickOpen): automating 2FA dynamic OTP authentication, Go single-binary architecture, encrypted credential storage, and OpenWrt split-tunneling."
tags: ["Go", "VPN", "Security", "OpenConnect", "Networking", "CLI", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 Background & Problem

When working remotely (WFH) or conducting cross-environment debugging, developers frequently connect to enterprise VPNs (e.g., Cisco AnyConnect / OpenConnect) authenticated with **"Static Passwords + Google Authenticator Dynamic 2FA OTPs"**.

**Everyday Friction**:
1. **Repetitive Manual Reconnection**: Dynamic OTPs change every 30 seconds; reconnecting requires manually checking a smartphone app multiple times a day.
2. **Mobile Debugging Roadblocks**: Connecting an iOS device directly to a VPN often breaks local proxy inspection tools (Charles/Proxyman).
3. **Router LuCI Incompatibility with 2FA**: Standard OpenWrt router interfaces only store static passwords and cannot reconnect to 2FA-protected corporate gateways.

**Blinq (QuickOpen)** was engineered under the slogan: **“Blink and you're in.”** — **Instant TOTP calculation, local AES-256 encrypted credential management, and one-click connection with OpenWrt split-tunneling**.

---

## 🚀 Key Features & Architecture

- **⚡ Sub-Second Auto-Authentication**: Generates RFC 6238 TOTP codes on the fly and streams credentials directly into OpenConnect processes without manual intervention.
- **🔒 AES-256-GCM On-Device Encryption**: Secures user credentials and TOTP seeds locally with AES-256-GCM. Zero telemetry or external credential leakage.
- **🌐 Transparent Router Split-Tunneling**: Integrates seamlessly with OpenWrt routers via `tun0` virtual interfaces and `dnsmasq` rule engines, allowing all LAN devices (including test iPhones and TVs) to access internal enterprise resources transparently.
- **💻 Cross-Platform & Zero Dependencies**: Single binary written in pure Go, supporting macOS (Apple Silicon & Intel), Linux, and Windows.

---

## 🖼️ Interface Showcase

![Blinq Preview](/images/projects/blinq/preview.webp)

---

## 🏗️ System Topology

```text
[ Developer Workstation / LAN Devices ]
       │
       ▼
[ Blinq Core Engine (Go) ]
       ├── AES-256-GCM Local Credential Decryption
       ├── RFC 6238 TOTP Dynamic Code Calculation
       └── OpenConnect Process Automation & Pipeline Injection
       │
       ▼
[ VPN Virtual Interface (tun0) ]
       │
       ├─► [ Domain & Subnet Split-Tunneling ] ──► [ Enterprise Internal Network ]
       └─► [ Default Traffic Direct Routing ] ──► [ Public Internet ]
```

---

## 🛠️ Engineering Highlights

1. **Hardened Local Credential Vault**: Combines machine-derived keys and user passphrases to encrypt configuration blobs with AES-256-GCM.
2. **Smart DNS & Split Routing**: Custom `vpnc-script` hooks and `dnsmasq` rules prevent DNS pollution while preserving Gigabit-speed public browsing.

---

## 📈 Shipping & Deliverables

- [x] Cross-platform CLI binaries and automated build packaging
- [x] OpenWrt daemon script and transparent split-tunneling setup
- [x] Dedicated product landing page live at [https://getblinq.app](https://getblinq.app)

---

## 🔗 Links

- **Product Website**: [https://getblinq.app](https://getblinq.app)
- **GitHub Repository**: [https://github.com/hamguy](https://github.com/hamguy)
