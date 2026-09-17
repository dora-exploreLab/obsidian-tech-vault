---
title: "Agent Harness 运行时架构"
aliases: ["AgentHarness", "智能体脚手架"]
type: "concept"
domain: "AI"
up_link: "[[06.10 - 人工智能与智能体图谱 (AI & Agent MOC)]]"
related_links:
  - "[[ReAct 认知循环范式]]"
  - "[[MCP 模型上下文协议]]"
  - "[[分布式一致性与幂等锁]]"
tags:
  - knowledge-graph
  - atomic-concept
  - agent
---

# ⚡ Agent Harness 运行时架构

## 📌 本质阐释
Agent Harness 是驾驭大语言模型与外部工具交互的**底层稳态底盘**。它负责在脆弱的非确定性模型推理与确定性的操作系统/网络之间，构建起指数退避、遥测埋点与自纠错容错闭环。

## 🧬 核心机制
1. **统一动作分发 (Unified Act Dispatcher)**：所有副作用操作收拢为 `act(actionName, payload, executor)`；
2. **反思自愈 (Reflect & Heal)**：当大模型输出不合规时，自动追问重试，拒绝单次硬崩溃；
3. **指标观测 (Telemetry)**：耗时、Token 与调用状态全链路审计。

## 🕸️ 图谱关联网络
- 上级中枢：[[06.10 - 人工智能与智能体图谱 (AI & Agent MOC)]]
- 认知驱动：[[ReAct 认知循环范式]]
- 外部集成：[[MCP 模型上下文协议]]
- 存储防线：[[分布式一致性与幂等锁]]