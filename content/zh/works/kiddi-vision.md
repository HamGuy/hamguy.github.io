---
title: "KiddiVision (童视智汇) · 智能 TV 伴学系统"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "专为儿童与 Android TV（Android 12+ / Sony 智能电视）打造的沉浸式 AI 语音互动与课程伴学系统。"
summary: "解析 KiddiVision 智能 TV 伴学系统：Go 高性能局域网服务、Edge-TTS 流式语音、生词拼音注音组件与遥控器焦点优化。"
tags: ["Android TV", "Kotlin", "Compose", "Go", "Edge-TTS", "AI", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 项目背景与初衷

随着 AI 大模型和智能家居的普及，电视作为客厅最大的一块屏幕，其互动方式却长期停留在传统的视频点播阶段。传统儿童教育 App 在电视上面临诸多痛点：

1. **大屏遥控器交互体验差**：手机移植应用在电视上难以选焦，操作极其生硬。
2. **缺乏即时互动与语音问答**：孩子观看科普或古诗视频时遇到疑问无法随手提问。
3. **配置大模型门槛高**：在电视端使用遥控器输入冗长复杂的 API Key 和服务地址极其痛苦。

**KiddiVision (童视智汇)** 针对家庭客厅大屏场景专门研发：**专为 TV 优化的原生交互、手机扫码即配大模型、实时语音流式伴学与防盗链视频解析**。

---

## 🚀 核心设计目标与系统特性

- **📺 Kotlin + Jetpack Compose for TV 原生大屏客户端**：
  - 针对大屏与遥控器进行深度焦点优化，支持 D-Pad 方向键丝滑选焦与推荐追问。
  - **拼音注音组件 (`RubyText`)**：在核心生词上方提供精准注音（如“电荷 diàn hè”、“戟 jǐ”），辅助低龄儿童自主认字与阅读。
  - **Media3 ExoPlayer**：无缝播放 B 站科普视频流，支持防盗链 Header 注入与全屏画中画联动。
  - **遥控器双模语音**：长按遥控器 `[OK/确认]` 键触发麦克风推流，松开即刻与 AI 语音角色对话。

- **🚀 Go 高性能局域网伴学服务 (`server/`)**：
  - 极简部署：单一 Go 二进制文件，无复杂 Python 虚拟环境依赖，秒级启动。
  - **📱 手机扫码热同步**：TV 端显示动态二维码，家长微信或浏览器扫码直接进入配置后台，填写 API Key（DeepSeek / 通义千问 / OpenAI 等）后毫秒级热同步到电视。
  - **🎙️ Edge-TTS 儿童音色流式推流**：采用微软晓晓（`zh-CN-XiaoxiaoNeural`）等亲切音色，通过 WebSocket 实时分片朗读，极大降低端到端首字延迟。
  - **📺 课程知识图谱**：内置小学科学、语文古诗词与恐龙航天百科，支持本地兜底与大模型智能拓展。

---

## 🖼️ 界面与架构展示

![KiddiVision Banner](/images/projects/kiddi-vision/kiddi_banner.svg)

```text
[ 智能手机 (家长) ]
       │ 扫码访问配置后台 (HTTP 8080)
       ▼
[ Go 伴学服务端 (server/) ] ◄───────► [ 大模型 API (DeepSeek / Qwen / OpenAI) ]
       │                                     │
       ├─► [ Edge-TTS 语音流式合成 ]         │
       │                                     │
       ▼ (WebSocket 实时推流)                ▼
[ Android TV 客户端 (Kotlin + Compose for TV) ]
       ├── Media3 ExoPlayer (B 站视频直链播放)
       ├── RubyText (拼音注音展示)
       └── 遥控器焦点 & 语音录制交互
```

---

## 🛠️ 技术攻坚与亮点

1. **TV 遥控器与音频焦点管理**：在 Android TV 上长按遥控器触发录音时，系统自动对正在播放的课程视频执行淡出静音，录音结束即刻恢复背景音，保证收音清晰度。
2. **生词拼音排版组件**：在 Jetpack Compose 中实现轻量高效的拼音文字对照布局（Ruby 注音），避免复杂 Canvas 绘制带来的重绘性能开销。
3. **免公网 IP 的局域网秒级扫码配置**：服务端内置 mDNS 与局域网 IP 自动广播，TV 端动态生成带局域网签名的二维码，家长手机零门槛配网。

---

## 📈 当前完成度

- [x] Go 高性能伴学服务与 WebSocket 双向通道
- [x] 家长手机端动态扫码配置后台
- [x] Edge-TTS 语音流式推送与播放
- [x] Compose for TV 界面、RubyText 拼音注音与焦点管理
- [x] Media3 ExoPlayer 视频流与防盗链 Header 适配

---

## 🔗 相关链接

- **GitHub 仓库**: [https://github.com/hamguy](https://github.com/hamguy)
