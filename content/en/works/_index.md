---
title: "Works & Projects"
description: "A showcase of personal side projects, AI intelligence pipelines, developer tools, and creative utilities built by HamGuy."
summary: "Personal side projects, AI market intelligence engines, macOS tools, OpenWrt systems, and developer utilities."
layout: "page"
---

<style>
  .portfolio-intro {
    font-size: 1.1rem;
    color: var(--secondary);
    margin-bottom: 2rem;
    line-height: 1.6;
  }
  
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(360px, 1fr));
    gap: 1.8rem;
    margin: 2rem 0;
  }

  .project-card {
    background: var(--entry);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 1.5rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transition: all 0.25s ease;
    box-shadow: 0 2px 8px rgba(0,0,0,0.04);
  }

  .project-card:hover {
    transform: translateY(-4px);
    border-color: var(--primary);
    box-shadow: 0 8px 24px rgba(0,0,0,0.08);
  }

  .project-header {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin-bottom: 1rem;
  }

  .project-icon {
    width: 52px;
    height: 52px;
    border-radius: 12px;
    object-fit: cover;
    background: var(--code-bg);
    border: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 15px;
    font-weight: 700;
    color: var(--primary);
    flex-shrink: 0;
    font-family: 'JetBrains Mono', monospace;
  }

  .project-title {
    margin: 0;
    font-size: 1.25rem;
    font-weight: 700;
  }

  .project-category {
    font-size: 0.8rem;
    color: var(--secondary);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-top: 2px;
    font-family: 'JetBrains Mono', monospace;
  }

  .project-desc {
    font-size: 0.95rem;
    color: var(--secondary);
    line-height: 1.55;
    margin-bottom: 1.25rem;
    flex-grow: 1;
  }

  .project-tech {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 1.25rem;
  }

  .tech-badge {
    font-size: 0.75rem;
    padding: 3px 8px;
    background: var(--code-bg);
    border: 1px solid var(--border);
    border-radius: 6px;
    font-family: 'JetBrains Mono', monospace;
    color: var(--primary);
  }

  .project-links {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    padding-top: 1rem;
    border-top: 1px solid var(--border);
  }

  .btn-link {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    padding: 6px 12px;
    border-radius: 8px;
    font-size: 0.85rem;
    font-weight: 600;
    text-decoration: none !important;
    background: var(--primary);
    color: var(--theme) !important;
    transition: opacity 0.2s ease;
  }

  .btn-link.secondary {
    background: var(--code-bg);
    color: var(--primary) !important;
    border: 1px solid var(--border);
  }

  .btn-link:hover {
    opacity: 0.85;
  }

  .section-title {
    font-size: 1.5rem;
    font-weight: 700;
    margin-top: 3rem;
    margin-bottom: 1rem;
    padding-bottom: 0.5rem;
    border-bottom: 1px solid var(--border);
  }
</style>

<div class="portfolio-intro">
  A curated collection of personal side projects, AI intelligence pipelines, smart hardware utilities, developer tools, and creative experiments built by HamGuy.
</div>

<h2 class="section-title">AI Intelligence &amp; Market Pipelines</h2>

<div class="projects-grid">
  <!-- DemandRadar AI -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">DR</div>
        <div>
          <h3 class="project-title">DemandRadar AI</h3>
          <div class="project-category">Market Intelligence &amp; NLP Decision Engine</div>
        </div>
      </div>
      <p class="project-desc">
        An autonomous market intelligence pipeline that ingests multi-source unstructured developer demand streams, extracts verifiable pain points, and applies LLM-driven confidence scoring to surface high-potential SaaS &amp; DevTools opportunities.
      </p>
      <div class="project-tech">
        <span class="tech-badge">AI Pipeline</span>
        <span class="tech-badge">NLP Clustering</span>
        <span class="tech-badge">LLM Scoring</span>
        <span class="tech-badge">FastAPI</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/demand-radar/" class="btn-link">Case Study &rarr;</a>
      <span class="btn-link secondary">Private Pipeline</span>
    </div>
  </div>

  <!-- NicheHunter -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">NH</div>
        <div>
          <h3 class="project-title">NicheHunter</h3>
          <div class="project-category">AI Vertical Market Research Workbench</div>
        </div>
      </div>
      <p class="project-desc">
        An intelligent market analysis workbench designed to dissect niche software segments, evaluate competitive density, identify white-space differentiation, and generate structured feasibility reports using LLM workflows.
      </p>
      <div class="project-tech">
        <span class="tech-badge">Market Analysis</span>
        <span class="tech-badge">LLM Workflows</span>
        <span class="tech-badge">Python</span>
        <span class="tech-badge">Workbench</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/niche-hunter/" class="btn-link">Case Study &rarr;</a>
      <span class="btn-link secondary">Private Workbench</span>
    </div>
  </div>

  <!-- OnlyBots -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">OB</div>
        <div>
          <h3 class="project-title">OnlyBots</h3>
          <div class="project-category">Multi-Agent Content Orchestration</div>
        </div>
      </div>
      <p class="project-desc">
        An autonomous multi-agent content generation and workflow orchestration pipeline powered by Qwen and Hermes LLM models, featuring automated topic clustering, candidate generation, and multi-channel pipeline dispatching.
      </p>
      <div class="project-tech">
        <span class="tech-badge">Multi-Agent</span>
        <span class="tech-badge">Qwen LLM</span>
        <span class="tech-badge">Workflow</span>
        <span class="tech-badge">Automation</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/onlybots/" class="btn-link">Case Study &rarr;</a>
      <span class="btn-link secondary">24/7 Agent Flow</span>
    </div>
  </div>
</div>

<h2 class="section-title">Gateway &amp; Smart Devices</h2>

<div class="projects-grid">
  <!-- ParentControl Guard -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">PCG</div>
        <div>
          <h3 class="project-title">ParentControl Guard</h3>
          <div class="project-category">OpenWrt Gateway / Parental Control</div>
        </div>
      </div>
      <p class="project-desc">
        A fine-grained parental control and network behavior management system for OpenWrt routers. Built with a Go daemon and Linux kernel L7 DPI (Deep Packet Inspection), offering embedded responsive Web UI, Token Bucket quota limits, anti-bypass enforcement, and native iOS/Android companion apps.
      </p>
      <div class="project-tech">
        <span class="tech-badge">Go</span>
        <span class="tech-badge">Linux Kernel DPI</span>
        <span class="tech-badge">OpenWrt</span>
        <span class="tech-badge">SwiftUI</span>
        <span class="tech-badge">Cloudflare Workers</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/parent-control/" class="btn-link">Case Study &rarr;</a>
      <span class="btn-link secondary">OpenWrt 21.02 - 23.05</span>
    </div>
  </div>

  <!-- KiddiVision -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">KD</div>
        <div>
          <h3 class="project-title">KiddiVision</h3>
          <div class="project-category">Android TV / AI Tutoring System</div>
        </div>
      </div>
      <p class="project-desc">
        An immersive AI-powered voice companion and educational TV system for Android TV (Android 12+ / Sony TV). Powered by a high-performance Go backend, real-time Edge-TTS streaming, Pinyin RubyText for early literacy, Bilibili video stream parsing, and mobile QR code configuration.
      </p>
      <div class="project-tech">
        <span class="tech-badge">Kotlin</span>
        <span class="tech-badge">Compose for TV</span>
        <span class="tech-badge">Go Backend</span>
        <span class="tech-badge">Edge-TTS</span>
        <span class="tech-badge">Media3 ExoPlayer</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/kiddi-vision/" class="btn-link">Case Study &rarr;</a>
      <span class="btn-link secondary">Android TV 12+</span>
    </div>
  </div>

  <!-- Blinq (QuickOpen) -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <img src="/images/projects/blinq/logo.png" alt="Blinq Logo" class="project-icon" onerror="this.outerHTML='<div class=\'project-icon\'>BLQ</div>'">
        <div>
          <h3 class="project-title">Blinq (QuickOpen)</h3>
          <div class="project-category">Enterprise VPN Automation Suite</div>
        </div>
      </div>
      <p class="project-desc">
        A lightweight automated enterprise VPN connectivity tool with instant TOTP calculation, local AES-256-GCM credential encryption, and OpenWrt router split-tunneling (Split-Tunneling).
      </p>
      <div class="project-tech">
        <span class="tech-badge">Go</span>
        <span class="tech-badge">OpenConnect</span>
        <span class="tech-badge">Security</span>
        <span class="tech-badge">Split-Tunneling</span>
        <span class="tech-badge">OpenWrt</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/blinq/" class="btn-link">Case Study &rarr;</a>
      <a href="https://getblinq.app" class="btn-link secondary" target="_blank" rel="noopener noreferrer">getblinq.app ↗</a>
    </div>
  </div>
</div>

<h2 class="section-title">Developer Tools &amp; macOS Utilities</h2>

<div class="projects-grid">
  <!-- CCSwitch -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <img src="/ccswitch/AppIcon.png" alt="CCSwitch Icon" class="project-icon" onerror="this.outerHTML='<div class=\'project-icon\'>CCS</div>'">
        <div>
          <h3 class="project-title">CCSwitch for Mac</h3>
          <div class="project-category">macOS Menu Bar Utility</div>
        </div>
      </div>
      <p class="project-desc">
        An elegant macOS menu bar app to toggle Claude Code API endpoints, authentication tokens, and environment configurations in one click. Lightweight and designed for AI-native workflows.
      </p>
      <div class="project-tech">
        <span class="tech-badge">Swift</span>
        <span class="tech-badge">AppKit</span>
        <span class="tech-badge">Claude Code</span>
        <span class="tech-badge">macOS</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/ccswitch/" class="btn-link">Case Study &rarr;</a>
      <a href="/ccswitch/" class="btn-link secondary">Product Page</a>
    </div>
  </div>

  <!-- CCSetup -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">SET</div>
        <div>
          <h3 class="project-title">CCSetup</h3>
          <div class="project-category">CLI Bootstrapper &amp; Toolkit</div>
        </div>
      </div>
      <p class="project-desc">
        Automated installer and quickstart script for Claude Code. Bootstraps runtime dependencies, authentication keys, multi-model routing, and Model Context Protocol (MCP) server registries.
      </p>
      <div class="project-tech">
        <span class="tech-badge">Shell Script</span>
        <span class="tech-badge">Claude Code</span>
        <span class="tech-badge">MCP Protocol</span>
        <span class="tech-badge">Automation</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/ccsetup/" class="btn-link">Quickstart Guide</a>
      <a href="https://github.com/hamguy" class="btn-link secondary" target="_blank" rel="noopener noreferrer">Source Code</a>
    </div>
  </div>
</div>

<h2 class="section-title">Mobile Apps &amp; Browser Extensions</h2>

<div class="projects-grid">
  <!-- Sesamo -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <img src="/sesamo/AppIcon.png" alt="Sesamo Icon" class="project-icon" onerror="this.outerHTML='<div class=\'project-icon\'>SSM</div>'">
        <div>
          <h3 class="project-title">Sesamo</h3>
          <div class="project-category">iOS / Android Utility</div>
        </div>
      </div>
      <p class="project-desc">
        Zero-latency on-device OCR camera scanner specifically engineered for Microsoft Authenticator 2-number verification prompts. Eliminates manual screen switching with instant local computer vision.
      </p>
      <div class="project-tech">
        <span class="tech-badge">Swift</span>
        <span class="tech-badge">SwiftUI</span>
        <span class="tech-badge">Vision OCR</span>
        <span class="tech-badge">On-Device AI</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/sesamo/" class="btn-link">Case Study &rarr;</a>
      <a href="/sesamo/" class="btn-link secondary">Product Page</a>
      <a href="https://apps.apple.com/app/sesamo/id6746903273" class="btn-link secondary" target="_blank" rel="noopener noreferrer">App Store</a>
    </div>
  </div>

  <!-- LikeMates (Trovault) -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">LM</div>
        <div>
          <h3 class="project-title">LikeMates (Trovault)</h3>
          <div class="project-category">Chrome Extension (Manifest V3)</div>
        </div>
      </div>
      <p class="project-desc">
        A privacy-first Chrome extension to sync, organize, and full-text search your X (Twitter) likes and bookmarks locally. Features media filtering (Images/Videos/Links), temporal filters, and 100% on-device IndexedDB storage.
      </p>
      <div class="project-tech">
        <span class="tech-badge">Chrome Extension</span>
        <span class="tech-badge">Manifest V3</span>
        <span class="tech-badge">TypeScript</span>
        <span class="tech-badge">IndexedDB</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/likemates/" class="btn-link">Case Study &rarr;</a>
      <a href="https://chromewebstore.google.com/detail/trovault-twitter-likes-bo/jamclmmnnannpcflkjimkogjpmknlgcg" class="btn-link secondary" target="_blank" rel="noopener noreferrer">Chrome Store (★★★★★)</a>
    </div>
  </div>
</div>

<h2 class="section-title">Web &amp; AI Creative Experiments</h2>

<div class="projects-grid">
  <!-- GPT-4o Image Guide -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">AI</div>
        <div>
          <h3 class="project-title">GPT-4o Image Prompt Guide</h3>
          <div class="project-category">Interactive AI Handbook</div>
        </div>
      </div>
      <p class="project-desc">
        An interactive visual handbook for GPT-4o image generation. Demonstrates prompt formulas, lighting styles, camera angles, aesthetic directions, and parameter tuning.
      </p>
      <div class="project-tech">
        <span class="tech-badge">HTML5 / CSS3</span>
        <span class="tech-badge">Prompt Engineering</span>
        <span class="tech-badge">GPT-4o</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/gpt4o-image.html" class="btn-link" target="_blank">Open Guide</a>
    </div>
  </div>

  <!-- Company Registration Lookup -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">CR</div>
        <div>
          <h3 class="project-title">UN &amp; US Company Registration Lookup</h3>
          <div class="project-category">Web Data Utility</div>
        </div>
      </div>
      <p class="project-desc">
        A quick lookup and verification tool for public enterprise registration information, business scope, and corporate filing status.
      </p>
      <div class="project-tech">
        <span class="tech-badge">JavaScript</span>
        <span class="tech-badge">Web API</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/un-us-company.html" class="btn-link" target="_blank">Open Tool</a>
    </div>
  </div>
</div>
