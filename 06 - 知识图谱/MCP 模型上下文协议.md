---
title: "MCP 模型上下文协议"
aliases: ["MCP", "Model Context Protocol"]
type: "concept"
domain: "AI"
up_link: "[[06.10 - 人工智能与智能体图谱 (AI & Agent MOC)]]"
related_links:
  - "[[Agent Harness 运行时架构]]"
  - "[[现代全栈网络分流路由]]"
tags:
  - knowledge-graph
  - atomic-concept
  - protocol
---

# 🔌 MCP 模型上下文协议 (Model Context Protocol)

## 📌 本质阐释
MCP 是由 Anthropic 主导提出的开放通信协议，旨在统一 AI 智能体与本地数据源、开发工具及外部 API 之间的双向交互接口，类似现代软件开发中的通用驱动协议（LSP）。

## 🧬 核心拓扑
- **MCP Host**：智能体运行时宿主；
- **MCP Client**：请求客户端与上下文连接器；
- **MCP Server**：隔离暴露工具、资源与 Prompt 模版的独立服务进程。

## 🕸️ 图谱关联网络
- 上级中枢：[[06.10 - 人工智能与智能体图谱 (AI & Agent MOC)]]
- 调度基座：[[Agent Harness 运行时架构]]
- 网络基础：[[现代全栈网络分流路由]]