---
title: "Building in Public: From iOS Apps to AI Developer Tools"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "A reflection on shipping indie products, navigating the Apple ecosystem, and integrating modern AI agent workflows."
summary: "Reflections on building Sesamo, CCSwitch, and CCSetup — what I learned from native Swift development, developer pain points, and shipping fast."
tags: ["Swift", "Indie Dev", "macOS", "AI Tools"]
categories: ["Indie Development", "Engineering"]
showToc: true
TocOpen: true
---

## Introduction

As an independent software engineer, nothing compares to the feeling of identifying a real-world friction point and turning it into a polished, lightweight native utility.

Over the past few years, my focus has gravitated toward two deeply exciting areas:

1. **Native Apple Ecosystem Engineering**: Leveraging modern Swift, SwiftUI, and Vision OCR to create lightning-fast iOS and macOS experiences.
2. **AI Tooling & Agent Workflows**: Building streamlined environments, menu bar switches, and automation scripts for AI assistants like Claude Code.

---

## Crafting Focused Solutions

### 1. Sesamo: Solving the 2FA Friction

Many users waste seconds everyday switching screens and manually copying Microsoft verification codes. With **Sesamo**, the goal was simple: zero latency, privacy-first on-device OCR recognition.

```swift
import Vision
import SwiftUI

func recognizeVerificationCode(from image: CGImage) async throws -> String? {
    let request = VNRecognizeTextRequest()
    request.recognitionLevel = .accurate
    request.usesLanguageCorrection = false
    
    let handler = VNImageRequestHandler(cgImage: image, options: [:])
    try handler.perform([request])
    
    guard let observations = request.results else { return nil }
    return extractNumericCode(from: observations)
}
```

### 2. CCSwitch: Seamless API Environment Management

When working extensively with CLI tools and different API endpoints, managing environment variables manually is error-prone. **CCSwitch** lives quietly in the macOS menu bar, allowing one-click environment switching.

```bash
# Rapid Claude Code configuration with CCSetup
curl -fsSL https://hamguy.xyz/ccsetup/install.sh | bash
```

---

## Key Takeaways

| Principle | Traditional Approach | Indie Builder Approach |
| :--- | :--- | :--- |
| **Architecture** | Heavy multi-layer frameworks | Lightweight, native APIs |
| **Privacy** | Cloud telemetry & data logging | 100% On-device execution |
| **Iteration Speed** | Monthly release cycles | Continuous shipping in public |

> The best software is not the one with the most features, but the one that solves a specific pain point so effortlessly you forget it was ever hard.

---

## What Lies Ahead

In upcoming posts, I will dive deeper into:
- Native SwiftUI performance profiling and memory optimizations
- Best practices for structuring Model Context Protocol (MCP) servers
- Lessons learned while launching independent apps on the App Store and Google Play

Stay tuned and feel free to connect via [X / Twitter](https://x.com/hamguy315) or [GitHub](https://github.com/hamguy).
