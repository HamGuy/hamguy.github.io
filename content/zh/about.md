---
title: "关于我"
description: "HamGuy 是谁？软件工程师、Apple 生态与跨端开发者、技术作者。"
summary: "关于 HamGuy - 背景、专注领域、全景技术栈与联系方式。"
layout: "page"
---

<style>
  .about-hero {
    font-size: 1.15rem;
    line-height: 1.8;
    color: var(--content);
    margin-bottom: 2rem;
  }

  .about-grid-2 {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
    gap: 1.5rem;
    margin: 1.5rem 0 2.5rem 0;
  }

  .about-card {
    background: var(--entry);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 1.5rem;
    transition: all 0.25s ease;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.03);
  }

  .about-card:hover {
    transform: translateY(-3px);
    border-color: var(--accent-brand);
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.06);
  }

  .about-card h3 {
    margin-top: 0;
    margin-bottom: 0.75rem;
    font-size: 1.15rem;
    font-weight: 700;
    color: var(--primary);
  }

  .about-card p {
    margin: 0;
    font-size: 0.95rem;
    color: var(--secondary);
    line-height: 1.6;
  }

  .skills-matrix {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1.25rem;
    margin: 1.5rem 0 2.5rem 0;
  }

  .skill-block {
    background: var(--entry);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.25rem;
  }

  .skill-block h4 {
    margin: 0 0 0.6rem 0;
    font-size: 0.95rem;
    font-weight: 700;
    color: var(--primary);
    font-family: 'JetBrains Mono', monospace;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .skill-pill {
    padding: 3px 9px;
    background: var(--code-bg);
    border: 1px solid var(--border);
    border-radius: 6px;
    font-size: 0.8rem;
    font-family: 'JetBrains Mono', monospace;
    color: var(--secondary);
  }

  .connect-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
    gap: 1rem;
    margin: 1.5rem 0 2.5rem 0;
  }

  .connect-card {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem 1.25rem;
    background: var(--entry);
    border: 1px solid var(--border);
    border-radius: 12px;
    text-decoration: none !important;
    color: var(--primary) !important;
    transition: all 0.25s ease;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.9rem;
    font-weight: 600;
  }

  .connect-card:hover {
    transform: translateY(-2px);
    border-color: var(--accent-brand);
    color: var(--accent-brand) !important;
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.05);
  }
</style>

<div class="about-hero">
  <p>
    我是一名<strong>软件工程师与技术极客</strong>，热爱 <strong>Apple 原生生态 (iOS & macOS)</strong>、<strong>AI 辅助编程与开发者工具</strong>，并在业余时间持续探索实用、轻量且注重隐私的个人项目。
  </p>
</div>

---

## 核心关注与技术方向

<div class="about-grid-2">
  <div class="about-card">
    <h3>Apple 原生生态与跨端开发</h3>
    <p>深度实践现代 Swift、SwiftUI、Flutter 与 Vision OCR 视觉计算，打造丝滑高效的原生与跨平台应用体验。</p>
  </div>
  <div class="about-card">
    <h3>AI Agent 开发者工具链</h3>
    <p>探索大模型工具集成、Model Context Protocol (MCP) 服务端协议与 Claude Code / Gemini 等智能体的自动化环境配置。</p>
  </div>
  <div class="about-card">
    <h3>自建基建与私有化部署</h3>
    <p>基于 Docker、Linux 服务器与 NAS 搭建稳健的个人 HomeLab、数据存储与自动化服务。</p>
  </div>
  <div class="about-card">
    <h3>持续公开写作与分享</h3>
    <p>坚持记录技术踩坑、架构设计心得与业余开发过程中的复盘反思，与开发者社区共同成长。</p>
  </div>
</div>

---

## 全景技术栈

<div class="skills-matrix">
  <div class="skill-block">
    <h4>平台与系统</h4>
    <div class="skill-tags">
      <span class="skill-pill">iOS</span>
      <span class="skill-pill">macOS</span>
      <span class="skill-pill">Android</span>
      <span class="skill-pill">小程序</span>
      <span class="skill-pill">Linux Server</span>
      <span class="skill-pill">NAS / HomeLab</span>
      <span class="skill-pill">Web</span>
    </div>
  </div>
  <div class="skill-block">
    <h4>编程语言</h4>
    <div class="skill-tags">
      <span class="skill-pill">Swift</span>
      <span class="skill-pill">Dart</span>
      <span class="skill-pill">Rust</span>
      <span class="skill-pill">Python</span>
      <span class="skill-pill">TypeScript</span>
      <span class="skill-pill">Shell</span>
      <span class="skill-pill">Go</span>
    </div>
  </div>
  <div class="skill-block">
    <h4>框架与生态</h4>
    <div class="skill-tags">
      <span class="skill-pill">Flutter</span>
      <span class="skill-pill">SwiftUI</span>
      <span class="skill-pill">微信小程序</span>
      <span class="skill-pill">UIKit</span>
      <span class="skill-pill">Combine</span>
      <span class="skill-pill">Node.js</span>
      <span class="skill-pill">Hugo</span>
    </div>
  </div>
  <div class="skill-block">
    <h4>AI 与智能体生态</h4>
    <div class="skill-tags">
      <span class="skill-pill">Gemini</span>
      <span class="skill-pill">Antigravity</span>
      <span class="skill-pill">Claude Code</span>
      <span class="skill-pill">Qwen (通义千问)</span>
      <span class="skill-pill">DeepSeek</span>
      <span class="skill-pill">GPT-4o</span>
      <span class="skill-pill">MCP Protocol</span>
      <span class="skill-pill">Vision OCR</span>
      <span class="skill-pill">Ollama</span>
    </div>
  </div>
  <div class="skill-block">
    <h4>基建、DevOps 与工具</h4>
    <div class="skill-tags">
      <span class="skill-pill">Docker</span>
      <span class="skill-pill">NAS / Self-Hosting</span>
      <span class="skill-pill">Linux</span>
      <span class="skill-pill">Xcode</span>
      <span class="skill-pill">Git</span>
      <span class="skill-pill">VS Code</span>
      <span class="skill-pill">Cursor</span>
    </div>
  </div>
</div>

---

## 保持连接与交流

<div class="connect-grid">
  <a href="https://github.com/hamguy" target="_blank" rel="noopener noreferrer" class="connect-card">
    <span>GitHub</span>
    <span>@hamguy &rarr;</span>
  </a>
  <a href="https://x.com/hamguy315" target="_blank" rel="noopener noreferrer" class="connect-card">
    <span>X (Twitter)</span>
    <span>@hamguy315 &rarr;</span>
  </a>
  <a href="https://www.linkedin.com/in/hamguy/" target="_blank" rel="noopener noreferrer" class="connect-card">
    <span>LinkedIn</span>
    <span>HamGuy &rarr;</span>
  </a>
  <a href="mailto:wangrui15@gmail.com" class="connect-card">
    <span>邮箱联系</span>
    <span>发送邮件 &rarr;</span>
  </a>
  <a href="/index.xml" class="connect-card">
    <span>RSS 订阅</span>
    <span>立即订阅 &rarr;</span>
  </a>
</div>

---

> *"保持好奇，构建有价值的产品，持续输出与交付。"*
