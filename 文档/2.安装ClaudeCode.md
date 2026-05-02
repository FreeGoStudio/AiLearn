# 介绍

Claude Code 是 Anthropic 推出的一种面向开发者的 AI 编程工具 / Agent 形态产品，可以理解为"带执行能力的代码助手"，但它比传统补全工具更进一步。

## 目标
准备使用Claude Code 搭配 DeepSeek 模型来使用, 也可以配置其他的模型, 方式差不多.

## 主要特性

- **代码理解与生成**：能够理解上下文并生成高质量代码片段
- **项目感知**：能够访问和理解整个项目结构
- **执行能力**：可以实际执行代码并获取反馈
- **问题修复**：自动检测并修复代码问题
- **多语言支持**：支持多种编程语言

## 方式一：通过 VS Code 扩展市场

### 前置条件

1. 安装 VS Code 编辑器

https://code.visualstudio.com/

2. 获取 DeepSeek API 密钥

https://platform.deepseek.com/api_keys

### 安装步骤

1. **打开 VS Code**
2. **打开扩展市场**
   - 使用快捷键 `Ctrl+Shift+X`（Windows）或 `Cmd+Shift+X`（Mac）
   - 或点击左侧边栏的"扩展"图标
3. **搜索 Claude Code**
   - 在搜索框中输入 "Claude Code for VS Code"
4. **点击安装**
   - 找到官方(Anthropic
)扩展，点击"Install"按钮
5. **配置 API 密钥**
   - 打开 VS Code 设置（`Ctrl+,`）
   - 搜索 "claude code", 找到"Claude Code"
   - 找到 "Claude Code: Environment Variables" 配置项
   - 点击 "在 setting.json 文件中编辑"
   - 按以下内容修改json文件中的内容

将
```json
"claudeCode.environmentVariables": [
],
```
改为
```json
"claudeCode.environmentVariables": [
    {
        "name": "ANTHROPIC_BASE_URL",
        "value": "https://api.deepseek.com/anthropic"
    },
    {
        "name": "ANTHROPIC_AUTH_TOKEN",
        "value": "<你的 DeepSeek API Key>"
    },
    {
        "name": "ANTHROPIC_MODEL",
        "value": "deepseek-v4-pro[1m]"
    },
    {
        "name": "ANTHROPIC_DEFAULT_OPUS_MODEL",
        "value": "deepseek-v4-pro[1m]"
    },
    {
        "name": "ANTHROPIC_DEFAULT_SONNET_MODEL",
        "value": "deepseek-v4-pro[1m]"
    },
    {
        "name": "ANTHROPIC_DEFAULT_HAIKU_MODEL",
        "value": "deepseek-v4-flash"
    },
    {
        "name": "CLAUDE_CODE_SUBAGENT_MODEL",
        "value": "deepseek-v4-flash"
    },
    {
        "name": "CLAUDE_CODE_EFFORT_LEVEL",
        "value": "max"
    },
],
```
6. **验证安装**
   - 在侧边栏应该能看到 Claude Code 的图标
   - 点击图标打开 Claude Code 面板
   - 点击 New session, 就能创建 Claude 会话

### 方式二：Node.js 安装 Claude Code

### 前置条件

1. Node.js 18.0 或更高版本

https://nodejs.org/en

2. 获取 DeepSeek API 密钥

https://platform.deepseek.com/api_keys

### 安装步骤

1. 在 cmd 或 powershell中运行以下命令
```bash
# 全局安装 Claude Code CLI
npm install -g @anthropic-ai/claude-code

# 验证安装, 如果现实版本号, 说明安装成功, 例如:2.1.122 (Claude Code)
claude --version
```

2. 配置环境变量
```
$env:ANTHROPIC_BASE_URL="https://api.deepseek.com/anthropic"
$env:ANTHROPIC_AUTH_TOKEN="<你的 DeepSeek API Key>"
$env:ANTHROPIC_MODEL="deepseek-v4-pro[1m]"
$env:ANTHROPIC_DEFAULT_OPUS_MODEL="deepseek-v4-pro[1m]"
$env:ANTHROPIC_DEFAULT_SONNET_MODEL="deepseek-v4-pro[1m]"
$env:ANTHROPIC_DEFAULT_HAIKU_MODEL="deepseek-v4-flash"
$env:CLAUDE_CODE_SUBAGENT_MODEL="deepseek-v4-flash"
$env:CLAUDE_CODE_EFFORT_LEVEL="max"
```

## 使用基础

### 创建新的 Claude Code 会话

1. 在 VS Code 中打开 Claude Code 面板
2. 点击"New Chat"或"新建会话"
3. 输入你的问题或需求
4. Claude Code 会分析项目上下文并提供建议

-----------------------------
以下内容未确定

## 使用方式

### 方式一：命令行直接使用

```bash
# 在项目目录中启动 Claude Code
cd your-project
claude-code

# 指定特定文件获取帮助
claude-code analyze src/main.ts

# 运行特定命令
claude-code fix src/app.js
```

### 方式二：在项目中使用

```bash
# 在项目中本地安装（推荐用于团队项目）
npm install --save-dev claude-code

# 在 package.json 中添加脚本
# 然后运行：
npm run claude-code
```

### 常用命令

- `claude-code analyze <file>` - 分析文件并提供建议
- `claude-code fix <file>` - 自动修复文件中的问题
- `claude-code test <file>` - 为文件生成测试代码
- `claude-code explain <file>` - 解释代码的功能
- `claude-code refactor <file>` - 重构代码以提高可读性

## 高级配置

### 创建本地配置文件

在项目根目录创建 `.claude-code.json`：

```json
{
  "apiKey": "your-api-key",
  "model": "claude-3-5-sonnet",
  "temperature": 0.7,
  "maxTokens": 2048,
  "context": {
    "includeNodeModules": false,
    "ignoredPaths": ["node_modules", "dist", "build"]
  }
}
```

### 环境变量配置

```bash
# 设置环境变量（推荐用于敏感信息）
export CLAUDE_CODE_API_KEY=your-api-key
export CLAUDE_CODE_MODEL=claude-3-5-sonnet
```

---
