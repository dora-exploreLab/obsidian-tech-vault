---
title: "ReAct 认知循环范式"
aliases: ["ReAct", "Reasoning and Acting"]
type: "concept"
domain: "AI"
up_link: "[[06.10 - 人工智能与智能体图谱 (AI & Agent MOC)]]"
related_links:
  - "[[Agent Harness 运行时架构]]"
tags:
  - knowledge-graph
  - atomic-concept
  - reasoning
---

# 🔄 ReAct 认知循环范式

## 📌 本质阐释
ReAct (Reason + Act) 将**推理分析（Reasoning）**与**环境行动（Acting）**协同融合。智能体不仅输出动作，且在每次行动前显式表达思维过程，并在获得环境反馈后进行自我调整。

## 🧬 核心执行环路
```text
[观察 Observation] ──► [思考 Thought] ──► [行动 Action] ──► [执行反馈 Result]
         ▲                                                          │
         └──────────────────────────────────────────────────────────┘
```

## 🕸️ 图谱关联网络
- 上级中枢：[[06.10 - 人工智能与智能体图谱 (AI & Agent MOC)]]
- 落地容器：[[Agent Harness 运行时架构]]