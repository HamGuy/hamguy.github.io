---
title: "Sesamo · 屏幕验证码 OCR 秒级识别工具"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "专为解决微软 Authenticator 验证码繁琐切换而设计的本地视觉 OCR 扫描器（iOS / Android）。"
summary: "解析 Sesamo 的产品设计初衷、设备端 Vision OCR 零延迟识别与跨平台工程实践。"
tags: ["iOS", "Swift", "SwiftUI", "Vision OCR", "Android", "Product", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 背景与痛点

在使用微软企业账户（Microsoft Entra ID / Office 365）登录时，系统常要求在电脑屏幕上查看一个 2 位随机数字，然后打开手机上的 Authenticator 点击匹配数字。

**日常痛点**：
- 很多时候手机屏幕停留在其他应用，需要切换多步；或者在电脑屏幕上扫一眼后容易记错；
- 频繁的 2FA 确认打断了心流，尤其对于每天需要反复登录各类企业系统的开发者和职场人。

**Sesamo**（取名自“芝麻开门” Sesame）诞生于这个极度精准的痛点：**拿起手机对准屏幕，零延迟本地 OCR 自动识别匹配码并提示，1 秒完成验证流程**。

---

## 🚀 核心特性

- **⚡ 毫秒级端侧视觉识别**：基于 Apple 原生 **Vision Framework** 与设备端 CoreML 模型，视频流逐帧本地分析，无任何网络请求，隐私 100% 安全。
- **🎯 智能防抖与高容错匹配**：自动过滤屏幕反光、摩尔纹和非数字干扰字符，秒级锁定 2 位数字目标。
- **📱 极简轻量交互**：应用冷启动时间低于 0.2 秒，相机对准屏幕瞬间完成识别与触觉震动反馈。
- **🌐 跨平台发布**：同时支持 iOS (App Store) 与 Android (Google Play)。

---

## 🏗️ 核心代码实现

```swift
import Vision
import SwiftUI

final class CodeScannerEngine: ObservableObject {
    @Published var detectedCode: String?
    
    private lazy var textRequest: VNRecognizeTextRequest = {
        let request = VNRecognizeTextRequest { [weak self] request, error in
            guard let results = request.results as? [VNRecognizedTextObservation] else { return }
            self?.processObservations(results)
        }
        request.recognitionLevel = .accurate
        request.usesLanguageCorrection = false
        request.customWords = ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9"]
        return request
    }()
    
    func analyzeFrame(_ sampleBuffer: CMSampleBuffer) {
        guard let pixelBuffer = CMSampleBufferGetImageBuffer(sampleBuffer) else { return }
        let handler = VNImageRequestHandler(cvPixelBuffer: pixelBuffer, orientation: .up)
        try? handler.perform([textRequest])
    }
}
```

---

## 📈 交付成果与数据

- [x] iOS App Store 审核通过并正式上架
- [x] Google Play 商店正式上架
- [x] 独立产品落地页上线：[https://hamguy.xyz/sesamo/](https://hamguy.xyz/sesamo/)

---

## 🔗 下载与体验

- **官方主页**: [https://hamguy.xyz/sesamo/](/sesamo/)
- **App Store**: [https://apps.apple.com/app/sesamo/id6746903273](https://apps.apple.com/app/sesamo/id6746903273)
- **Google Play**: [https://play.google.com/store/apps/details?id=xyz.hamguy.sesamo](https://play.google.com/store/apps/details?id=xyz.hamguy.sesamo)
