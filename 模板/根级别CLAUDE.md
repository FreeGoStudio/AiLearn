# CLAUDE.md

## 项目说明

你正在开发 XXX 项目, 包含以下功能:

* XXX
* XXX
* XXX

## 技术栈

* 语言：C#
* UI：WPF
* 架构：Clean Architecture
* 存储：JSON（当前不使用数据库）

## 架构规则

分层结构：

* XXX.Core：领域模型层
* XXX.Contracts: 契约层
* XXX.Application：应用服务层
* XXX.Infrastructure：数据存储层

依赖关系：

* Core → 不允许依赖任何层
* Contracts → Core
* Application → Core, Contracts
* Infrastructure → Core, Contracts, Application

禁止违反依赖方向。

## 限制

* 不要实现未要求的功能
* 不要引入新的框架或第三方库
* 不要修改无关代码
* 不要移动文件结构

## 执行策略

- 允许自动修改 src/ 下的代码
- 不需要每次确认文件编辑
- 允许运行 dotnet build / run

## 编码原则

* 保持代码简单清晰
* 使用明确的命名
* 避免过度设计
* 类和方法尽量小

## 工作流程

每次必须按以下步骤执行：

1. 先说明将要做的内容
2. 只实现当前要求的功能
3. 不修改其他模块
4. 最后总结改动

## 行为规则

* 如果需求不清楚，先提问
* 如果任务过大，拆分为小任务
* 优先保证正确性，而不是完整性

## 完成标准

任务完成必须满足：

* 能正常编译
* 无明显错误
* 符合当前需求
* 没有引入额外改动
