---
title: "CCSwitch for Mac · Claude Code Menu Bar Environment Switcher"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "A lightweight macOS menu bar utility for one-click switching between Claude Code API endpoints, tokens, and routing environments."
summary: "An in-depth case study of CCSwitch for Mac: native Swift/AppKit menu bar architecture, CLI developer productivity, and AI proxy management."
tags: ["macOS", "Swift", "AppKit", "Claude Code", "DevTools", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 Background & Motivation

As AI coding assistants like **Claude Code** become daily drivers in software development, power users frequently juggle multiple API environments:

1. **Multiple Endpoints & Proxies**: Switching between Anthropic official endpoints, private gateways, and self-hosted routing proxies.
2. **Account & Token Rotation**: Managing separate billing keys across enterprise, open-source, and personal projects.
3. **Friction of Manual Configs**: Modifying `~/.zshrc` or `~/.claude.json` by hand is cumbersome and prone to typos.

**CCSwitch for Mac** was designed for AI-native engineering: **Lives quietly in the macOS menu bar, enabling instant environment switching in a single click**.

---

## 🚀 Key Features

- **⚡ Instant Menu Bar Switching**: Access all configured profiles anywhere on macOS via the system menu bar.
- **🔒 Secure Local Storage**: Keeps sensitive API tokens encrypted on-device with zero cloud telemetry.
- **🛠️ Immediate Terminal Sync**: Updates active environment variables and configuration files on-the-fly without terminal restarts.
- **💻 Ultra-Lightweight Native App**: Built in pure Swift + AppKit with memory footprint under 15MB.

---

## 🏗️ Menu Bar Implementation

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

## 📈 Deliverables & Integration

- [x] Native macOS 12+ (Universal Binary for Apple Silicon & Intel)
- [x] Dedicated Landing Page: [https://hamguy.xyz/ccswitch/](/ccswitch/)
- [x] Interoperability with [CCSetup](/ccsetup/) CLI bootstrapper

---

## 🔗 Links

- **Landing Page**: [https://hamguy.xyz/ccswitch/](/ccswitch/)
