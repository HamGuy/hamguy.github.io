---
title: "Sesamo · Instant On-Device 2FA Code OCR Scanner"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "A fast, privacy-first mobile OCR scanner designed to eliminate friction in Microsoft 2FA verification workflows (iOS & Android)."
summary: "An in-depth case study of Sesamo: product problem-solving, zero-latency on-device Vision OCR, and cross-platform mobile release."
tags: ["iOS", "Swift", "SwiftUI", "Vision OCR", "Android", "Product", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 Background & Problem

When logging into Microsoft corporate accounts (Microsoft Entra ID / Office 365), users are regularly prompted with a 2-digit verification number on their computer screen that must be matched in Microsoft Authenticator on their phone.

**Everyday Friction**:
- Constant context switching between laptop and smartphone.
- Distraction and cognitive overhead when logging into internal dev dashboards dozens of times a day.

**Sesamo** was crafted to solve this exact friction point: **Point the phone camera at the screen, and instant on-device OCR identifies the 2-digit code in sub-second time with haptic confirmation**.

---

## 🚀 Key Features

- **⚡ Sub-Second On-Device Vision**: Built with Apple's **Vision Framework** and native ML models. Processes camera frames entirely on-device with zero network latency and 100% data privacy.
- **🎯 Moiré & Screen Reflection Filtering**: Custom heuristics to filter out screen scan lines, ambient glare, and surrounding alphanumeric noise.
- **📱 Instant Cold Start**: Sub-0.2s launch time to immediately focus and capture the verification prompt.
- **🌐 Cross-Platform Release**: Available on both the iOS App Store and Google Play.

---

## 🏗️ Core Implementation

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

## 📈 Shipping & Deliverables

- [x] Approved and live on the Apple App Store
- [x] Approved and live on Google Play
- [x] Dedicated product landing page: [https://hamguy.xyz/sesamo/](/sesamo/)

---

## 🔗 Links & Downloads

- **Product Landing Page**: [https://hamguy.xyz/sesamo/](/sesamo/)
- **App Store**: [https://apps.apple.com/app/sesamo/id6746903273](https://apps.apple.com/app/sesamo/id6746903273)
- **Google Play**: [https://play.google.com/store/apps/details?id=xyz.hamguy.sesamo](https://play.google.com/store/apps/details?id=xyz.hamguy.sesamo)
