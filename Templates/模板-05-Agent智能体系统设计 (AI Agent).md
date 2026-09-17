---
title: "{{title}}"
created: "{{date}}"
architecture: "ReAct / Multi-Agent / LangGraph / Plan-and-Solve"
protocol: "MCP (Model Context Protocol) / Function Calling"
tags:
  - agent
  - llm
  - automation
---

# 🤖 Agent 系统架构：{{title}}

## 🎯 Agent 定位与角色设定 (System Persona)
> 设定 Agent 的专业职责、输入边界、工作原则。

## 🧩 核心认知架构
```text
[用户输入] ──► [规划器 Planner] ──► [工具决策 Tool Calling] ──► [执行反馈 Environment]
                     ▲                                                    │
                     └──────────────── [反思与记忆 Reflection] ───────────┘
```
1. **规划层 (Planning)**：(ReAct 循环 / 动态分解子任务 / 自我纠错)
2. **记忆层 (Memory)**：
   - 短期上下文管理 (Scratchpad)
   - 长期记忆 (Vector DB / RAG / 知识图谱)
3. **工具层 (Tool Execution & MCP)**：
   - 对接哪些外部工具 / API？
   - MCP Server 协议实现与接口定义

## 🛠️ 工具与 Function Schema
```json
{
  "name": "execute_command",
  "description": "执行指定的系统运维命令并返回输出",
  "parameters": {
    "type": "object",
    "properties": {
      "command": {"type": "string", "description": "要运行的 shell 命令"}
    },
    "required": ["command"]
  }
}
```

## 🔄 多智能体协作拓扑 (如适用)
- **Role A (主控/规划)**：
- **Role B (执行/检索)**：
- **Role C (评审/质检)**：

## 📊 评估指标与实测效果 (Eval)
- 任务完成成功率 (Success Rate)：
- 平均 Token 开销与响应延迟：
- 典型成功案例与失效反思：
