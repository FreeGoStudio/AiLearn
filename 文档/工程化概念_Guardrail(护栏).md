# Guardrail 介绍
> “限制 AI 不要乱来”

本质：

> AI Safety + AI Constraint

# 为什么必须 Guardrail

LLM 天生会：

* 幻觉
* 编造
* 越权
* 输出危险内容
* 被 Prompt Injection

所以：

> 不加护栏的 Agent 很危险。

# Guardrail 常见类型

## 1. Input Guardrail（输入护栏）
防止危险输入。

例如：

> 忽略之前所有规则

这是典型：

* Prompt Injection

示例

系统：
```
检测：
- jailbreak
- prompt injection
- 敏感词
```
发现危险：

> 直接拒绝。

## 2. Output Guardrail（输出护栏）

检查 AI 输出。

例如：

```
是否包含：
- 密码
- 身份证
- SQL DROP
- 恶意代码
```

### 在 Coding Agent 中很重要

例如：

> rm -rf /

Agent 就不应该执行。

## 3. Tool Guardrail（工具护栏）
限制 AI 调工具。

例如：

```
AI 不能：
- 删除数据库
- 转账
- 发生产邮件
```

必须：

* 用户确认
* 权限校验

## 4. Permission Guardrail（权限护栏）

类似 RBAC。

例如：

```
普通用户
不能访问管理员数据
```

AI 本身不能突破权限系统。

## 5. Scope Guardrail（范围护栏）

限制 AI 的能力边界。

例如：

```
Claude Code:
只能访问当前项目目录
```

这其实就是一种 Guardrail。

# Guardrail 的工程实现

## Prompt Layer

最基础：

```
禁止输出...
禁止执行...
```

但最弱。

因为：

> Prompt 不是安全机制。

## Middleware Layer

真正工程里更常见。

```
用户输入
→ 安全检查
→ AI
→ 输出检查
→ 用户
```

## Tool Layer

最重要。

例如：

```
AI 请求：
删除文件

系统：
是否允许？
```

类似：

> Capability-based Security


