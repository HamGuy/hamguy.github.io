---
title: "OnlyBots · Autonomous Multi-Agent Content Orchestration Platform"
date: 2026-08-30T10:00:00+08:00
draft: false
author: "HamGuy"
description: "An autonomous multi-agent content generation and workflow orchestration pipeline powered by Qwen and Hermes LLM models."
summary: "An in-depth case study of OnlyBots: multi-agent role orchestration, automated topic discovery, quality review loops, and multi-channel dispatch pipelines."
tags: ["Multi-Agent", "Qwen", "LLM", "Python", "Workflow", "Automation", "Side Project"]
categories: ["Projects", "Engineering"]
showToc: true
TocOpen: true
---

## 🎯 Background & Motivation

In the generative AI era, relying on manual prompting or single-agent monolithic architectures fails to sustain high-frequency, high-quality content pipelines across multiple channels.

Key limitations of single-agent approaches:
1. **Role Overload**: Forcing a single prompt to handle topic discovery, drafting, fact-checking, and formatting results in generic, repetitive outputs.
2. **Lack of Feedback Loops**: Without dedicated critique and refinement agents, content lacks depth and human nuance.
3. **Disconnected Dispatching**: Generated outputs are isolated from scheduling queues and publishing pipelines.

**OnlyBots** was designed to explore **autonomous multi-agent collaborative workflows**: **Simulating an editorial pipeline with specialized agents (Discovery, Creator, Critic, Formatter) to achieve end-to-end automated content synthesis**.

---

## 🚀 System Architecture & Key Features

- **🤖 Specialized Multi-Agent Role Orchestration**:
  - **Discovery Agent**: Scans technical streams around the clock, clustering discussions and identifying high-engagement core topics.
  - **Creator Agent**: Leverages Qwen and Hermes LLMs to craft contextual, in-depth narratives tailored to target developer personas.
  - **Critic Agent**: Reviews draft outputs for factual consistency, logical flow, readability, and de-AI phrasing.

- **📦 Intelligent Candidate Queue & Dispatcher**:
  - Automatically files vetted content into an interactive staging queue, supporting 1-click manual reviews or autonomous scheduled publishing.

- **🔌 Extensible Tool & Protocol Integration**:
  - Integrates with MCP (Model Context Protocol) tool servers, enabling agents to dynamically invoke external search, data lookups, and specialized sub-tasks.

---

## 🏗️ Multi-Agent Pipeline Topology

```text
[ Global Technical Discussion & News Feeds ]
       │
       ▼
[ 1. Discovery Agent (Topic Clustering & Relevance Filtering) ]
       │ (Selected High-Value Core Topics)
       ▼
[ 2. Creator Agent (Contextual Drafting / Qwen & Hermes LLMs) ]
       │ (Initial Draft)
       ▼
[ 3. Critic & Fact-Check Agent (Verification & Nuanced Polishing) ]
       │ (Quality-Scored & Approved)
       ▼
[ 4. Dispatcher Pipeline (Candidate Queue & Staging Box) ]
       │
       ▼
[ Visual Management Dashboard & Multi-Channel Distribution ]
```

---

## 🛠️ Engineering Highlights

1. **State Machine & Decoupled Messaging**: Each agent maintains isolated contextual memory and role boundaries, communicating asynchronously over an internal event bus.
2. **Heterogeneous Model Routing**: Routes high-volume filtering to lightweight models while reserving reasoning-heavy models for creative drafting and critique, optimizing cost and latency.

---

## 📈 Implementation Status

- [x] Multi-agent orchestration engine & event messaging bus
- [x] Customized drafting and verification workflows with Qwen & Hermes
- [x] Interactive candidate staging queue and multi-platform scheduler
- [x] Stable 24/7 self-hosted HomeLab deployment

---

## 🔗 Project Status

- **Type**: Proprietary multi-agent automation platform
- **Deployment**: Running privately on self-hosted infrastructure
