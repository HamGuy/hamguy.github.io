---
title: "作品与项目"
description: "HamGuy 在业余时间构建的个人独立项目、AI 市场洞察系统、OpenWrt 智能硬件、macOS 工具与极客实验。"
summary: "个人项目、AI 数据智能管道、OpenWrt 系统、Android TV 伴学应用与 macOS 效率工具展示。"
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
  精选个人在业余时间设计与开发的独立产品、AI 市场洞察系统、OpenWrt 智能网关、Android TV 伴学应用与 macOS 效率工具。
</div>

<h2 class="section-title">智能数据管道与市场洞察 (AI &amp; Data Pipelines)</h2>

<div class="projects-grid">
  <!-- DemandRadar AI -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">DR</div>
        <div>
          <h3 class="project-title">DemandRadar AI</h3>
          <div class="project-category">全球软件需求与商业机会洞察系统</div>
        </div>
      </div>
      <p class="project-desc">
        基于大模型语义分析与证据链提取的全球软件需求挖掘、痛点聚类与商业机会决策引擎。从多源非结构化技术讨论流中提炼高置信度商机，为出海选品提供确定性打分。
      </p>
      <div class="project-tech">
        <span class="tech-badge">AI Pipeline</span>
        <span class="tech-badge">NLP 语义聚类</span>
        <span class="tech-badge">LLM 评分模型</span>
        <span class="tech-badge">FastAPI</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/zh/works/demand-radar/" class="btn-link">项目详解 &rarr;</a>
      <span class="btn-link secondary">私有化部署</span>
    </div>
  </div>

  <!-- NicheHunter -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">NH</div>
        <div>
          <h3 class="project-title">NicheHunter</h3>
          <div class="project-category">垂直利基赛道 AI 辅助研究工作台</div>
        </div>
      </div>
      <p class="project-desc">
        专为垂直利基市场打造的深度剖析与商业可行性评估工作台。内置利基评估模型与 LLM 自动化分析工作流，快速完成竞品全景拆解、壁垒评估与立项研报生成。
      </p>
      <div class="project-tech">
        <span class="tech-badge">市场量化评估</span>
        <span class="tech-badge">LLM 工作流</span>
        <span class="tech-badge">Python</span>
        <span class="tech-badge">交互工作台</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/zh/works/niche-hunter/" class="btn-link">项目详解 &rarr;</a>
      <span class="btn-link secondary">内部工具</span>
    </div>
  </div>

  <!-- OnlyBots -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">OB</div>
        <div>
          <h3 class="project-title">OnlyBots</h3>
          <div class="project-category">多智能体协同与内容自动化生成平台</div>
        </div>
      </div>
      <p class="project-desc">
        基于 Qwen / Hermes 大模型驱动的自主多智能体协作平台。专职角色 Agent 协同完成话题自动挖掘、专业内容深度生成、质量交叉核查与多渠道分发排期。
      </p>
      <div class="project-tech">
        <span class="tech-badge">Multi-Agent</span>
        <span class="tech-badge">Qwen 大模型</span>
        <span class="tech-badge">工作流编排</span>
        <span class="tech-badge">自动化流水线</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/zh/works/onlybots/" class="btn-link">项目详解 &rarr;</a>
      <span class="btn-link secondary">24h 智能体流</span>
    </div>
  </div>
</div>

<h2 class="section-title">智能网关与大屏设备</h2>

<div class="projects-grid">
  <!-- ParentControl Guard -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">PCG</div>
        <div>
          <h3 class="project-title">ParentControl Guard</h3>
          <div class="project-category">OpenWrt 路由器 / 家长控制卫士</div>
        </div>
      </div>
      <p class="project-desc">
        专为 OpenWrt 固件打造的细粒度家长控制与上网行为安全管理系统。核心采用高效 Go 守护进程配合 Linux 内核级 L7 DPI 深度包检测，支持单文件内嵌 Web 控制台、防绕过拦截机制与原生 iOS / Android 客户端。
      </p>
      <div class="project-tech">
        <span class="tech-badge">Go</span>
        <span class="tech-badge">Linux 内核 DPI</span>
        <span class="tech-badge">OpenWrt</span>
        <span class="tech-badge">SwiftUI</span>
        <span class="tech-badge">Cloudflare Workers</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/zh/works/parent-control/" class="btn-link">项目详解 &rarr;</a>
      <a href="https://github.com/hamguy" class="btn-link secondary" target="_blank" rel="noopener noreferrer">GitHub</a>
    </div>
  </div>

  <!-- KiddiVision -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">KD</div>
        <div>
          <h3 class="project-title">KiddiVision (童视智汇)</h3>
          <div class="project-category">Android TV / 智能 TV 伴学系统</div>
        </div>
      </div>
      <p class="project-desc">
        专为儿童与 Android TV（Android 12+ / Sony 智能电视）打造的沉浸式 AI 语音伴学系统。采用 Go 高性能局域网服务、Edge-TTS 实时流式语音合成、生词拼音注音组件（RubyText）、B 站视频直链解析与手机扫码快捷配置。
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
      <a href="/zh/works/kiddi-vision/" class="btn-link">项目详解 &rarr;</a>
      <a href="https://github.com/hamguy" class="btn-link secondary" target="_blank" rel="noopener noreferrer">GitHub</a>
    </div>
  </div>

  <!-- Blinq (QuickOpen) -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <img src="/images/projects/blinq/logo.png" alt="Blinq Logo" class="project-icon" onerror="this.outerHTML='<div class=\'project-icon\'>BLQ</div>'">
        <div>
          <h3 class="project-title">Blinq (QuickOpen)</h3>
          <div class="project-category">企业 VPN 极速自动化连接套件</div>
        </div>
      </div>
      <p class="project-desc">
        轻量级极速企业 VPN 自动化拨号工具，支持 TOTP 动态验证码自动填充、AES-256-GCM 本地凭证安全加密与 OpenWrt 软路由透明分流 (Split-Tunneling)。
      </p>
      <div class="project-tech">
        <span class="tech-badge">Go</span>
        <span class="tech-badge">OpenConnect</span>
        <span class="tech-badge">安全加密</span>
        <span class="tech-badge">软路由分流</span>
        <span class="tech-badge">OpenWrt</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/zh/works/blinq/" class="btn-link">项目详解 &rarr;</a>
      <a href="https://getblinq.app" class="btn-link secondary" target="_blank" rel="noopener noreferrer">产品官网</a>
      <a href="https://github.com/hamguy" class="btn-link secondary" target="_blank" rel="noopener noreferrer">GitHub</a>
    </div>
  </div>
</div>

<h2 class="section-title">开发者工具与 macOS 效率套件</h2>

<div class="projects-grid">
  <!-- CCSwitch -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <img src="/ccswitch/AppIcon.png" alt="CCSwitch Icon" class="project-icon" onerror="this.outerHTML='<div class=\'project-icon\'>CCS</div>'">
        <div>
          <h3 class="project-title">CCSwitch for Mac</h3>
          <div class="project-category">macOS 菜单栏效率工具</div>
        </div>
      </div>
      <p class="project-desc">
        一键切换 Claude Code 的 API 端点、认证 Tokens 及环境配置。常驻 macOS 菜单栏，极简轻巧，专为日常使用 AI 辅助编码的开发者打造。
      </p>
      <div class="project-tech">
        <span class="tech-badge">Swift</span>
        <span class="tech-badge">AppKit</span>
        <span class="tech-badge">Claude Code</span>
        <span class="tech-badge">macOS</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/zh/works/ccswitch/" class="btn-link">项目详解 &rarr;</a>
      <a href="/ccswitch/" class="btn-link secondary">工具主页</a>
      <a href="https://github.com/hamguy" class="btn-link secondary" target="_blank" rel="noopener noreferrer">GitHub</a>
    </div>
  </div>

  <!-- CCSetup -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">SET</div>
        <div>
          <h3 class="project-title">CCSetup</h3>
          <div class="project-category">CLI 环境配置套件</div>
        </div>
      </div>
      <p class="project-desc">
        Claude Code 极速初始化安装与一键配置工具。自动化配置 Node.js 运行时、安全认证密钥、多模型路由与 MCP 扩展生态。
      </p>
      <div class="project-tech">
        <span class="tech-badge">Shell Script</span>
        <span class="tech-badge">Claude Code</span>
        <span class="tech-badge">MCP Protocol</span>
        <span class="tech-badge">Automation</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/ccsetup/" class="btn-link">使用指南</a>
      <a href="https://github.com/hamguy" class="btn-link secondary" target="_blank" rel="noopener noreferrer">源码查看</a>
    </div>
  </div>
</div>

<h2 class="section-title">移动端应用与浏览器插件</h2>

<div class="projects-grid">
  <!-- Sesamo -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <img src="/sesamo/AppIcon.png" alt="Sesamo Icon" class="project-icon" onerror="this.outerHTML='<div class=\'project-icon\'>SSM</div>'">
        <div>
          <h3 class="project-title">Sesamo</h3>
          <div class="project-category">iOS / Android 实用工具</div>
        </div>
      </div>
      <p class="project-desc">
        专为解决微软 Authenticator 验证码繁琐切换而设计的屏幕 OCR 扫描器。通过设备端本地视觉识别技术，秒级捕捉屏幕中的 2 位匹配码，彻底告别来回切换 App。
      </p>
      <div class="project-tech">
        <span class="tech-badge">Swift</span>
        <span class="tech-badge">SwiftUI</span>
        <span class="tech-badge">Vision OCR</span>
        <span class="tech-badge">On-Device AI</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/zh/works/sesamo/" class="btn-link">项目详解 &rarr;</a>
      <a href="/sesamo/" class="btn-link secondary">产品主页</a>
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
          <div class="project-category">Chrome 扩展插件 (Manifest V3)</div>
        </div>
      </div>
      <p class="project-desc">
        专注于隐私安全的 X (Twitter) 收藏与点赞离线管理 Chrome 浏览器插件。支持全量推文本地同步、多媒体类型筛选（图片/视频/链接）、全文即时搜索与纯本地 IndexedDB 存储。
      </p>
      <div class="project-tech">
        <span class="tech-badge">Chrome Extension</span>
        <span class="tech-badge">Manifest V3</span>
        <span class="tech-badge">TypeScript</span>
        <span class="tech-badge">IndexedDB</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/zh/works/likemates/" class="btn-link">项目详解 &rarr;</a>
      <a href="https://chromewebstore.google.com/detail/trovault-twitter-likes-bo/jamclmmnnannpcflkjimkogjpmknlgcg" class="btn-link secondary" target="_blank" rel="noopener noreferrer">Chrome 商店 (★★★★★)</a>
      <a href="https://github.com/hamguy" class="btn-link secondary" target="_blank" rel="noopener noreferrer">GitHub</a>
    </div>
  </div>
</div>

<h2 class="section-title">Web 与 AI 创意实践</h2>

<div class="projects-grid">
  <!-- GPT-4o Image Guide -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">AI</div>
        <div>
          <h3 class="project-title">GPT-4o 图像生成指南</h3>
          <div class="project-category">交互式 AI 提示词手册</div>
        </div>
      </div>
      <p class="project-desc">
        深入探索 GPT-4o 视觉能力与绘图生成的交互式提示词手册。包含丰富构图、光影技巧、风格示例与参数解析。
      </p>
      <div class="project-tech">
        <span class="tech-badge">HTML5 / CSS3</span>
        <span class="tech-badge">Prompt Engineering</span>
        <span class="tech-badge">GPT-4o</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/gpt4o-image.html" class="btn-link" target="_blank">在线浏览手册</a>
    </div>
  </div>

  <!-- Company Registration Lookup -->
  <div class="project-card">
    <div>
      <div class="project-header">
        <div class="project-icon">CR</div>
        <div>
          <h3 class="project-title">联合国与美国公司注册信息查询</h3>
          <div class="project-category">Web 数据查询工具</div>
        </div>
      </div>
      <p class="project-desc">
        快速便捷的企业公开注册信息、经营范围及登记状态查询验证工具。
      </p>
      <div class="project-tech">
        <span class="tech-badge">JavaScript</span>
        <span class="tech-badge">Web API</span>
      </div>
    </div>
    <div class="project-links">
      <a href="/works/un-us-company.html" class="btn-link" target="_blank">打开工具</a>
    </div>
  </div>
</div>
