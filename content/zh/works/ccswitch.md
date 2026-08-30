---
title: "CCSwitch for Mac · Claude Code 菜单栏切换器"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "常驻 macOS 菜单栏的一键式 Claude Code API 端点、Token 及环境配置切换利器。"
summary: "CCSwitch for Mac 项目复盘：极简 macOS 菜单栏原生架构、AI 开发者 CLI 工作流提效与多模型路由管理。"
tags: ["macOS", "Swift", "AppKit", "Claude Code", "DevTools", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 背景与痛点

随着 **Claude Code**、Cursor 以及各类 AI Agent 在日常编程开发中的普及，很多高频开发者会面临多套 API 环境共存的情况：

1. **多厂商 / 多中继端点频繁切换**：如 Anthropic 官方、自建中转网关、第三方代理或国内镜像源。
2. **多账号与 Token 额度轮换**：不同项目需要使用不同组织的 API Key 或配额账号。
3. **手动修改环境变量极度繁琐**：每次都需要在 `~/.zshrc` 或 `~/.claude.json` 中繁琐复制粘贴，极易遗留或改错。

**CCSwitch for Mac** 专为 AI 辅助编程的开发者设计：**常驻 macOS 顶部菜单栏，轻轻一点，毫秒级切换 Claude Code 运行环境**。

---

## 🚀 核心功能与特性

- **⚡ 菜单栏一键切换**：随时随地通过全局状态栏图标展开配置列表，点击即切。
- **🔒 本地安全存储**：API Tokens 严格保存在本地加密文件或系统 Keychain 中，零云端上传。
- **🛠️ 自动同步与即时生效**：自动同步修改终端环境变量与 Claude Code 配置文件，无需重启终端。
- **💻 极致轻巧原生**：采用纯 Swift + AppKit 编写，内存占用低于 15MB，无 Electron 臃肿包袱。

---

## 🏗️ 菜单栏核心逻辑

```swift
import AppKit

final class StatusBarController: NSObject {
    private var statusItem: NSStatusItem!
    private var menu: NSMenu!
    
    override init() {
        super.init()
        setupStatusBar()
    }
    
    private func setupStatusBar() {
        statusItem = NSStatusBar.system.statusItem(withLength: NSStatusItem.variableLength)
        if let button = statusItem.button {
            button.image = NSImage(named: "MenuBarIcon")
            button.imagePosition = .imageOnly
        }
        buildMenu()
    }
    
    func switchEnvironment(to env: ClaudeEnvironment) {
        ClaudeConfigManager.shared.apply(env)
        updateActiveIndicator(for: env)
    }
}
```

---

## 📈 交付成果

- [x] macOS 12+ (Apple Silicon & Intel) 原生适配
- [x] 专属产品展示页：[https://hamguy.xyz/ccswitch/](/ccswitch/)
- [x] 开源社区配套工具 [CCSetup](/ccsetup/) 联动

---

## 🔗 相关链接

- **产品官网**: [https://hamguy.xyz/ccswitch/](/ccswitch/)
- **GitHub 源码**: [https://github.com/hamguy](https://github.com/hamguy)
