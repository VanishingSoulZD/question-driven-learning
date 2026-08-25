# Research Note：从 Agent Framework 到 Agent Harness —— AI 应用工程师的能力升级路径

## 研究定位

**研究等级：**
L2 决策研究

**预计阅读时间：**
30分钟

**预计研究投入：**
3小时

**选择该等级的原因：**
该主题不仅涉及一个技术概念理解（Agent vs Harness），更直接影响我未来 1～3 年的职业方向选择、学习投入分配和求职定位。

当前我已经具备一定 LLM 应用基础，并正在从传统算法/工程背景转向 Agent 应用工程，因此需要判断：

- Harness 是否只是短期热点？
- 是否值得投入学习？
- 它与我已有学习路线是否连续？
- 我的学习重点应该从 Agent Framework 调整到哪里？

本研究目标不是成为某个 Harness 项目的使用者，而是形成对 **Agent Runtime / Agent Engineering 未来方向的判断能力**。

---

# 从 Agent Framework 到 Agent Harness：AI 应用工程师的能力升级路径

---

# 1. 为什么研究这个问题？

## 1.1 这个问题为什么值得研究？

过去一年，AI 应用开发的主流路径经历了明显变化：

第一阶段：

> 调用大模型 API → 做 Chatbot

第二阶段：

> RAG → Agent → Workflow

第三阶段：

> Agent Runtime → Harness → AI 原生执行系统

早期大家关注：

- GPT-4 / Claude / DeepSeek 等模型能力
- LangChain、LangGraph 等 Agent Framework

但随着模型能力提升，新的问题出现：

> 如何让 Agent 长时间、稳定、安全、自主地完成复杂任务？

例如：

- 一个 Coding Agent 如何连续工作几个小时？
- 一个 Research Agent 如何管理几十轮上下文？
- Agent 执行代码时如何保证安全？
- Agent 失败后如何恢复？
- 多 Agent 如何协作？
- 如何评价 Agent 是否真的变强？

这些问题已经超出了简单 Framework 范畴。

因此出现了：

> Agent Runtime / Agent Harness

这个新的工程方向。

---

## 1.2 它和我的当前阶段有什么关系？

我的职业背景：

- 曾从事图像算法相关工作
- 具备 Python / Golang / C++ 能力
- 做过 RAG、Agent、Evaluation 相关项目
- 当前目标：
  - LLM 应用工程师
  - Agent 应用工程师

我的问题：

过去学习：

- LangGraph
- AutoGen
- CrewAI
- OpenAI Agents SDK

过程中感觉比较枯燥。

原因：

我学习的是：

> “如何调用 Agent Framework”

但没有深入：

> “Agent 为什么能够运行”

Harness 这个概念提供了一个更底层的理解框架。

---

# 2. 我的原始问题

## 2.1 我最初的问题是什么？

我的核心疑问：

### 问题1：

Agent 和 Harness 是不是同一个概念？

例如：

- DeepSeek Harness
- Codex Harness
- OpenClaw
- Hermes Agent
- Claude Code

这些到底属于 Agent 还是 Harness？

---

### 问题2：

Harness 是不是只是 Agent 多了一层模型？

我的初始猜测：

> Agent = Harness + Model？

---

### 问题3：

之前学习的：

- LangGraph
- AutoGen
- CrewAI
- OpenAI Agents SDK

是否仍然有价值？

还是应该转向新的 Harness 方向？

---

### 问题4：

Harness 是否只是最近热点？

还是未来几年 AI 应用工程的重要方向？

---

## 2.2 我的已有认知和假设

当时我的认知：

```text
LLM
 ↓
Agent
 ↓
Agent Framework
 ↓
Agent Application
```

认为：

LangGraph 等框架就是 Agent 的核心技术。

---

现在需要修正：

更准确：

```text
                 AI Application

                       ↑

                 Agent System

                       ↑

       Agent Framework / Agent Runtime

                       ↑

                 Harness Layer

                       ↑

                  Model Layer
```

Framework 只是构建 Agent 的一种方式。

真正长期稳定的是：

- Runtime 思维
- Execution 思维
- Context 思维
- Tool 思维

---

# 3. 基础认知

# 3.1 什么是 Agent？

简单理解：

Agent 是：

> 能够感知环境、进行推理、调用工具、执行行动，并根据反馈继续决策的 AI 系统。

传统 LLM：

```text
User
 ↓
Prompt
 ↓
Model
 ↓
Answer
```

Agent：

```text
User
 ↓
Model
 ↓
Decision
 ↓
Tool
 ↓
Observation
 ↓
Model
 ↓
Next Action
 ↓
...
```

核心变化：

从：

> 生成文本

变成：

> 执行动作。

---

# 3.2 什么是 Harness？

Harness 可以理解为：

> 支撑 Agent 执行任务的运行环境和控制系统。

它负责：

- Agent Loop
- 状态管理
- Context 管理
- Tool 调用
- Memory
- Session
- Sandbox
- Permission
- Subagent
- Scheduling
- Evaluation

简单比喻：

| 类比             | 对应    |
| ---------------- | ------- |
| 人               | Agent   |
| 大脑             | Model   |
| 身体、工具、环境 | Harness |

模型负责：

> 思考

Harness负责：

> 让思考能够产生现实行动。

---

# 3.3 Agent 和 Harness 的关系

不是：

```
Agent ≠ Harness
```

更准确：

```
Agent = Model + Harness + Environment
```

其中：

Model：

负责：

- 推理
- 生成
- 判断

Harness：

负责：

- 执行
- 控制
- 管理

Environment：

负责：

- 文件
- 网络
- API
- 软件系统

---

# 3.4 为什么 Harness 会出现？

因为模型能力提升以后：

简单 Agent 已经不够。

过去：

```text
一次回答
```

现在：

```text
连续数小时工作
```

需要解决：

## 长任务

例如：

代码开发：

- 分析项目
- 修改代码
- 运行测试
- 修复 Bug
- 提交结果

---

## 上下文管理

问题：

几十轮以后：

- Prompt 爆炸
- 信息丢失

需要：

- Memory
- Summarization
- Compaction

---

## 工具执行

Agent 不只是聊天。

需要：

- Shell
- Browser
- Database
- API
- MCP

---

## 安全

Agent 可以执行代码。

需要：

- Sandbox
- Permission
- Isolation

---

因此 Harness 成为必要基础设施。

---

# 4. 领域生态/分类

## 4.1 Agent Framework

定位：

> 帮助开发者快速构建 Agent。

代表：

| 项目              | 定位                         |
| ----------------- | ---------------------------- |
| LangGraph         | Agent Workflow / State Graph |
| AutoGen           | Multi-Agent                  |
| CrewAI            | Role-based Agent             |
| OpenAI Agents SDK | Agent SDK                    |

特点：

优势：

- 快速开发
- 抽象较高

局限：

- 不一定解决生产 Runtime 问题

---

## 4.2 Agent Runtime / Harness

定位：

> 让 Agent 真正运行。

代表：

| 项目             | 定位                   |
| ---------------- | ---------------------- |
| DeepSeek Harness | 开源 Harness           |
| Codex Harness    | Coding Agent Runtime   |
| OpenClaw         | Agent Runtime Platform |
| Hermes Agent     | Personal Agent Runtime |

关注：

- Loop
- State
- Tool
- Context
- Execution

---

## 4.3 Agent 产品

定位：

> 面向用户的完整 Agent。

代表：

| 产品        | 类型           |
| ----------- | -------------- |
| Claude Code | Coding Agent   |
| Codex       | Coding Agent   |
| Cursor      | AI IDE Agent   |
| OpenClaw    | Personal Agent |

产品内部通常包含：

Agent + Harness。

---

# 5. 关键方案/产品/方法分析

---

# 5.1 DeepSeek Harness

## 是什么？

开源 Agent Harness。

核心理念：

> Everything is a Plugin

---

## 解决什么问题？

解决：

如何构建一个可扩展 Agent Runtime。

---

## 核心能力

包括：

- Agent Loop
- Plugin System
- Tool System
- Session
- Storage
- Sandbox
- Skill

---

## 优势

适合学习：

- Harness 架构
- Runtime 设计
- Plugin 化思想

---

## 局限

目前：

- 仍快速迭代
- API 不稳定

不应该把具体代码作为长期技能。

---

## 适合谁？

适合：

- Agent 工程师
- AI Infra 工程师
- 想理解 Agent 内部机制的人

---

# 5.2 Codex Harness

## 是什么？

OpenAI Codex 背后的 Agent Runtime。

---

## 核心价值

不是学习代码细节。

而是理解：

> 一个生产级 Coding Agent 如何运行。

---

关注：

- Agent Loop
- App Server
- 多客户端复用
- 工具执行
- 长任务管理

---

## 适合谁？

适合：

想理解：

> AI 原生软件开发环境

的人。

---

# 5.3 LangGraph

## 是什么？

Agent Framework。

---

## 核心价值

它帮助理解：

- State
- Workflow
- Durable Execution
- Human-in-the-loop

---

## 对我的意义

不是最终目标。

而是：

> 理解 Runtime 思想的重要工具。

---

# 5.4 OpenClaw / Hermes

定位：

完整 Agent Runtime。

价值：

用于比较不同设计：

- Memory
- Skill
- Tool
- Session
- Subagent

---

# 6. 我的理解和判断

## 6.1 事实

### 事实1：

Agent Framework 和 Harness 不是同一个层级。

Framework：

解决：

> 如何构建 Agent。

Harness：

解决：

> 如何让 Agent 稳定运行。

---

### 事实2：

LangGraph、AutoGen 等学习仍然有价值。

因为其中包含：

- State
- Workflow
- Agent Loop

这些思想不会消失。

---

### 事实3：

未来 Agent 工程的重要问题会从：

“如何调用模型”

转向：

“如何管理 Agent 执行”。

---

# 6.2 我的分析

我的原路线：

```
LLM Application Engineer
 ↓
Agent Framework
 ↓
Agent Application
```

现在升级为：

```
LLM Application Engineer
 ↓
Agent Engineer
 ↓
Agent Runtime / Harness Understanding
 ↓
Agent Infrastructure
```

这是能力深化。

不是换方向。

---

# 6.3 我的个人判断

对于我：

不应该成为：

> Harness 某个项目专家。

因为：

项目会变化。

应该成为：

> 理解 Agent Runtime 原理，并能够构建 Agent 系统的人。

长期价值：

来自：

- Runtime 思维
- Context Engineering
- Tool System
- Evaluation
- Infrastructure

而不是：

- LangGraph API
- DeepSeek Harness API

---

# 7. 对我的意义

## 7.1 职业价值

提升方向：

从：

> LLM 应用开发

升级：

> Agent 工程

未来岗位：

- Agent Engineer
- LLM Application Engineer
- AI Workflow Engineer
- AI Platform Engineer

---

## 7.2 技术成长价值

能够把已有能力重新组合：

已有：

- Python
- Backend
- RAG
- Evaluation
- Docker
- Redis

对应：

- Runtime
- Memory
- Session
- Sandbox
- Evaluation

---

## 7.3 收入价值

相比普通：

“会调用 API 的 AI 应用工程师”

理解：

- Agent Runtime
- Infrastructure

竞争力更强。

---

## 7.4 长期战略价值

未来 AI 工作方式可能从：

人操作软件

变成：

人管理 Agent。

因此：

理解 Agent Runtime 类似过去理解：

- 操作系统
- 浏览器
- 云计算平台

具有长期价值。

---

# 8. 下一步行动

## 第一阶段：研究 Harness 架构

目标：

理解：

> Agent Runtime 是什么。

实践：

DeepSeek Harness。

重点：

不要读全部源码。

回答：

1. Agent Loop在哪里？
2. State在哪里？
3. Tool如何调用？
4. Plugin如何设计？
5. Session如何保存？
6. Sandbox如何实现？

---

## 第二阶段：研究 Codex Harness

目标：

理解生产级 Agent。

重点：

阅读：

- Harness Engineering
- Codex Architecture
- App Server

关注：

- 长任务
- 工具执行
- 多客户端

---

## 第三阶段：自己实现 Mini Agent Runtime

这是最重要阶段。

项目目标：

实现：

- Agent Loop
- Tool Calling
- Session
- Memory
- MCP
- Skills
- Evaluation
- Tracing

形成个人作品。

---

## 第四阶段：重新学习 Framework

顺序：

1. LangGraph
2. OpenAI Agents SDK

目标：

理解：

> Framework 如何封装 Runtime。

---

# 9. 来源和延伸阅读

## 必读

### 1. DeepSeek Harness

用途：

理解开源 Harness 架构。

重点：

- Plugin System
- Runtime Design

### 2. OpenAI Harness Engineering

用途：

理解未来 AI 原生工程模式。

重点：

- Agent 工作环境设计
- Feedback Loop

### 3. OpenAI Codex Harness

用途：

理解生产级 Coding Agent。

重点：

- Agent Loop
- App Server

---

## 扩展阅读

### LangGraph 文档

用途：

理解：

- State
- Graph
- Durable Execution

### OpenAI Agents SDK 文档

用途：

理解：

- Tools
- Handoff
- Guardrails

### OpenClaw / Hermes Agent

用途：

横向比较：

- Personal Agent Runtime
- Skill System
- Memory System

---

# 最终结论

对于我的当前阶段：

**学习方向没有改变，而是升级。**

不是：

> 从 LLM/Agent 转向 Harness。

而是：

> 从学习如何使用 Agent，升级到理解和构建 Agent 系统。

我的最佳定位：

短期：

> LLM / Agent Application Engineer

中期：

> Agent Engineer

长期：

> Agent Runtime / AI Infrastructure Engineer

当前最值得投入的不是某一个框架，而是：

> **围绕 Agent Runtime、Harness、Context、Tools、Evaluation 建立系统认知，并通过自己的 Mini Harness 项目完成能力沉淀。**

这条路线能够最大程度复用我过去的技术积累，同时提高未来 AI 时代的长期竞争力。
