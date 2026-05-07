# HarnessEngineering 介绍
在 AI Agent 语境下，Harness Engineering 可以理解成：

> “围绕大模型，构建一整套可执行、可约束、可观察、可扩展的运行框架。”

重点是：

> 真正让 Agent 能稳定工作的是 Harness，不是模型本身。

很多人误以为：

> LLM = Agent

实际上更接近：

> Agent = LLM + Harness

其中：

* LLM 负责“思考/生成”
* Harness 负责“让它真的能干活”

就像人类大脑再聪明，没有：

* 工具
* 记忆
* 工作流
* 权限
* 环境
* 规则

也什么都做不了。

# Harness 到底是什么

可以把它理解成：

> Agent 的“工程外骨骼”。

类似：

* 操作系统
* 中间件
* 工作流引擎
* 工具调度层
* 安全层
* 上下文管理层

的组合。

# 为什么会出现 Harness Engineering

因为大家发现：

> 模型能力 ≠ Agent能力

很多 Agent 失败：

不是模型太笨。

而是：

* 上下文混乱
* 工具不会用
* Prompt 漂移
* 没有状态管理
* 无法恢复执行
* 没有验证
* 没有权限控制
* 没有长期记忆
* workflow 不稳定

于是行业开始意识到：

> “Agent 最大的问题是工程问题。”

这就是 Harness Engineering 出现的背景。

# Harness 的核心组成

一个完整 Harness 通常包括：

## 1. Context Harness（上下文管理）

负责：

> 给模型什么上下文

包括：

* RAG
* Memory
* CLAUDE.md
* 项目规则
* 当前任务
* 历史会话
* Code Index

例如：

```
Claude Code
↓
读取 CLAUDE.md
↓
读取 docs/
↓
索引代码
↓
拼接 Prompt
↓
再调用模型
```

这里：

> “拼接上下文”的系统

就是 Harness 的一部分。

## 2. Tool Harness（工具系统）

负责：

> 让模型调用外部能力

比如：

* shell
* git
* browser
* database
* test runner
* Unity Editor
* Blender
* Stable Diffusion

例如 Claude Code：

```
Agent
  → shell
  → grep
  → edit file
  → run test
```

这部分就是 Tool Harness。

## 3. Workflow Harness（工作流）

负责：

> Agent 怎么执行任务

例如：

```
需求分析
  ↓
拆任务
  ↓
生成代码
  ↓
运行测试
  ↓
失败修复
  ↓
再次测试
  ↓
提交 git
```

这其实已经不是 Prompt。

而是：

> 工程流水线

了。

## 4. Guardrail Harness（护栏）

负责：

> 限制 Agent 做危险事情

例如：

* 禁止删数据库
* 禁止 rm -rf
* 禁止泄露 secrets
* 限制文件范围
* 限制 token 消耗
* 限制网络访问

Claude Code 的 sandbox 就属于这个。

## 5. Evaluation Harness（评估系统）

负责：

> Agent 到底做得对不对

例如：

* 自动测试
* benchmark
* golden dataset
* 回归测试
* AI-as-Judge
* output validation

否则：

> Agent 只是在“看起来能运行”

实际上可能已经把系统搞坏了。

## 6. Runtime Harness（运行时）

负责：

> Agent 的生命周期管理

包括：

* 状态恢复
* 长任务
* checkpoint
* retry
* queue
* 并发
* task graph

这部分很多人完全没意识到。

但真正的企业 Agent 都很重视这个。

# Claude Code 为什么强

很多人以为：

> Claude 模型比别人强。

实际上：

Claude Code 强的一大原因是：

## Harness 很强

包括：

* Code Index
* 文件系统访问
* shell
* patch
* workflow
* sandbox
* 上下文压缩
* tool routing
* 长任务恢复

这些才是真正关键的。

# Vibe Coding 为什么容易失败

因为很多人只有：

> Prompt

没有：

> Harness

于是会出现：

* AI 越写越乱
* 架构漂移
* 风格不一致
* 不知道项目规则
* 重复代码
* 上下文爆炸
* 修 bug 修出更多 bug

这本质是：

缺乏工程化 Harness

# 项目中的实践
这些本质上是在做 Harness Engineering
```
CLAUDE.md
docs/
workflow
模块边界
架构规则
```

不是在“写 Prompt”。

是在：

> 给 AI 构建工程运行环境

# 未来趋势

未来 AI Coding 很可能会变成：

```
小模型能力差距
<
Harness 工程能力差距
```

也就是说：

未来真正竞争力不是：

> 谁 Prompt 更会写

而是：

> 谁的 Harness 更成熟

这也是为什么：

* Cursor
* Claude Code
* Devin
* OpenHands
* Codex CLI

本质都在拼：

> Agent Harness System

不是单纯拼模型。

# 接下来我的研究路线

```
AI Engineering
    ↓
Agent Engineering
    ↓
Harness Engineering
```
