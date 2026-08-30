---
title: "About Me"
description: "Who is HamGuy? Independent Developer, Apple ecosystem builder, and tech writer."
summary: "About HamGuy - Background, projects, tech stack, and ways to connect."
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
    I'm a <strong>software engineer & tech enthusiast</strong> passionate about the <strong>Apple ecosystem (iOS & macOS)</strong>, <strong>AI developer tooling</strong>, and crafting useful side projects and tools in my spare time.
  </p>
</div>

---

## Focus & Core Domains

<div class="about-grid-2">
  <div class="about-card">
    <h3>Apple Ecosystem &amp; Cross-Platform (Flutter)</h3>
    <p>Building high-performance native iOS, macOS, and Flutter cross-platform applications using modern Swift, SwiftUI, Dart, Combine, and the Vision framework.</p>
  </div>
  <div class="about-card">
    <h3>AI Agent Tooling & Workflows</h3>
    <p>Designing streamlined developer environments, Model Context Protocol (MCP) integrations, and lightweight automation utilities for assistants like Claude Code.</p>
  </div>
  <div class="about-card">
    <h3>Privacy-First Architecture</h3>
    <p>Prioritizing on-device execution, zero unnecessary telemetry, and user data ownership across every product shipped.</p>
  </div>
  <div class="about-card">
    <h3>Building & Writing in Public</h3>
    <p>Sharing technical deep-dives, postmortems, architecture patterns, and thoughts on the indie software journey.</p>
  </div>
</div>

---

## Technical Stack

<div class="skills-matrix">
  <div class="skill-block">
    <h4>Platforms</h4>
    <div class="skill-tags">
      <span class="skill-pill">iOS</span>
      <span class="skill-pill">macOS</span>
      <span class="skill-pill">Android</span>
      <span class="skill-pill">Mini Programs</span>
      <span class="skill-pill">Linux Server</span>
      <span class="skill-pill">NAS / HomeLab</span>
      <span class="skill-pill">Web</span>
    </div>
  </div>
  <div class="skill-block">
    <h4>Languages</h4>
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
    <h4>Frameworks &amp; UI</h4>
    <div class="skill-tags">
      <span class="skill-pill">Flutter</span>
      <span class="skill-pill">SwiftUI</span>
      <span class="skill-pill">WeChat Mini Program</span>
      <span class="skill-pill">UIKit</span>
      <span class="skill-pill">Combine</span>
      <span class="skill-pill">Node.js</span>
      <span class="skill-pill">Hugo</span>
    </div>
  </div>
  <div class="skill-block">
    <h4>AI &amp; Agent Ecosystem</h4>
    <div class="skill-tags">
      <span class="skill-pill">Gemini</span>
      <span class="skill-pill">Antigravity</span>
      <span class="skill-pill">Claude Code</span>
      <span class="skill-pill">Qwen</span>
      <span class="skill-pill">DeepSeek</span>
      <span class="skill-pill">GPT-4o</span>
      <span class="skill-pill">MCP Protocol</span>
      <span class="skill-pill">Vision OCR</span>
      <span class="skill-pill">Ollama</span>
    </div>
  </div>
  <div class="skill-block">
    <h4>Infra, DevOps &amp; Tools</h4>
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

## Connect & Collaborate

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
    <span>Email</span>
    <span>Send Email &rarr;</span>
  </a>
  <a href="/index.xml" class="connect-card">
    <span>RSS Feed</span>
    <span>Subscribe &rarr;</span>
  </a>
</div>

---

> *"Stay curious, build things that matter, and never stop shipping."*
