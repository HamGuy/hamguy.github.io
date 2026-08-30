---
title: "KiddiVision · Smart Android TV AI Tutoring System"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "An immersive AI-powered voice companion and educational TV system built for Android TV (Android 12+ / Sony TV)."
summary: "An in-depth case study of KiddiVision: Go high-performance local server, Edge-TTS streaming audio, Pinyin RubyText for kids literacy, and D-pad focus management."
tags: ["Android TV", "Kotlin", "Compose", "Go", "Edge-TTS", "AI", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 Background & Motivation

While smart TVs feature the largest and most captivating screen in the living room, most educational TV applications remain passive video players with clunky mobile-port interfaces.

Key pain points:
1. **Poor Remote Control UX**: Mobile apps ported to TV have awkward navigation and sluggish focus indicators.
2. **Lack of Conversational Interaction**: Children cannot spontaneously ask questions about science or literature videos.
3. **Complex TV Text Input**: Entering long AI API keys using a TV remote is tedious and error-prone.

**KiddiVision** was designed specifically for living-room education: **Native TV focus interactions, instant QR code smartphone configuration, real-time streaming voice tutoring, and anti-hotlink video parsing**.

---

## 🚀 System Features & Architecture

- **📺 Kotlin + Jetpack Compose for TV Client**:
  - D-Pad focus optimization with smooth visual highlights and recommended follow-up questions.
  - **Pinyin RubyText**: Displays pronunciation guides above Chinese characters to help young children read independently.
  - **Media3 ExoPlayer**: Direct video stream playback with custom Referer header injection for educational video platforms.
  - **Dual-Mode Remote Interaction**: Hold `[OK]` to speak and converse with AI characters in real-time.

- **🚀 Go High-Performance LAN Server (`server/`)**:
  - Single binary deployment with zero Python virtual environment overhead.
  - **📱 Instant Smartphone QR Configuration**: TV displays a dynamic QR code; parents scan with their smartphone to configure API keys (DeepSeek / Qwen / OpenAI) with instant live hot-reloading.
  - **🎙️ Edge-TTS Real-Time Streaming**: Low-latency chunked audio synthesis over WebSockets using child-friendly neural voices.
  - **📚 Structured Knowledge Graph**: Curated science and literature modules with seamless LLM augmentation.

---

## 🖼️ Showcase & Topology

![KiddiVision Banner](/images/projects/kiddi-vision/kiddi_banner.svg)

```text
[ Parent's Smartphone ]
       │ Scans QR Code (HTTP 8080)
       ▼
[ Go Backend (server/) ] ◄──────────► [ AI LLM APIs (DeepSeek / Qwen / OpenAI) ]
       │                                     │
       ├─► [ Edge-TTS Streaming Voice ]      │
       │                                     │
       ▼ (WebSocket Real-Time Stream)        ▼
[ Android TV Client (Kotlin + Compose for TV) ]
       ├── Media3 ExoPlayer (Video Stream)
       ├── RubyText (Pinyin Typography)
       └── Remote Control Focus & Audio Pipeline
```

---

## 🛠️ Engineering Challenges & Highlights

1. **Audio Focus & Remote Lifecycle**: When the child presses the remote to ask a question, the video background audio fades out automatically and restores seamlessly after speech interaction completes.
2. **Lightweight Pinyin Layout Component**: Custom Jetpack Compose layout ensuring crisp font rendering without Canvas redraw penalties.
3. **Seamless Zero-Config LAN Pairing**: Built-in mDNS discovery enables zero-friction phone-to-TV hot synchronization.

---

## 📈 Implementation Status

- [x] Go high-performance server & WebSocket streaming channel
- [x] Smartphone dynamic QR code pairing and configuration dashboard
- [x] Edge-TTS real-time audio chunk streaming
- [x] Jetpack Compose for TV interface & RubyText component
- [x] Media3 ExoPlayer video pipeline integration

---

## 🔗 Links

- **GitHub Repository**: [https://github.com/hamguy](https://github.com/hamguy)
