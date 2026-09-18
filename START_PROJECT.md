# START PROJECT / 启动项目

标准启动入口 / Standard startup entry point

本文件是使用 FinTech-Rules 启动 AI 辅助项目的单一、版本化入口。
This file is the single, version-controlled entry point for starting an AI-assisted project with FinTech-Rules.

## 使用方式 / How to use

1. 将 FinTech-Rules 提供给 AI coding agent。 / Make FinTech-Rules available to the AI coding agent.
2. 将目标项目仓库提供给同一个 agent。 / Make the target project repository available to the same agent.
3. 使用下面的启动提示词。 / Use the startup prompt below.
4. 暂时不要要求 AI 编写大量业务代码。 / Do not ask the AI to write substantial application code yet.
5. 完成 Bootstrap 和人工审批门禁。 / Complete Bootstrap and the human approval gate.
6. 审批后再进入正式实现。 / Only then authorize implementation.

## Standard Startup Prompt / 标准启动提示词

我希望使用我的 FinTech-Rules 工程操作系统启动一个新项目。
I want to start a new project using my FinTech-Rules engineering operating system.

FinTech-Rules 是本项目的上层工程操作系统和治理依据。
FinTech-Rules is the governing engineering operating system for this project.

Bootstrap the project. / 请执行项目 Bootstrap。

Do not write substantial application code yet. / 暂时不要编写大量正式业务代码。

First read and follow: README.md, AGENTS.md, rules/00-core.md, rules/01-ai-behavior.md, rules/02-development-workflow.md, rules/90-ai-project-bootstrap.md, all relevant technical/FinTech/data/API/testing/security/DevOps/Git rules, relevant templates, and existing project memory/decisions.
首先读取并遵循：README.md、AGENTS.md、核心规则、AI 行为规则、开发流程、Bootstrap 规则、所有相关技术/FinTech/数据/API/测试/安全/DevOps/Git 规则、相关模板，以及已有项目记忆和决策。

### 1. Initialize / 初始化
检查仓库、代码、技术栈、依赖、配置、测试、CI/CD、部署和 Git 状态，并创建或更新 BOOTSTRAP_REPORT.md。
Inspect the repository, code, stack, dependencies, configuration, tests, CI/CD, deployment, and Git state; create or update BOOTSTRAP_REPORT.md.

### 2. Discover / 项目发现
明确问题、用户、主要用户旅程、范围、非目标、数据、金融/监管属性、技术要求和成功标准；创建或更新 PROJECT_DISCOVERY.md；明确列出未决问题。
Determine the problem, users, journeys, scope, non-goals, data, financial/regulatory characteristics, technical requirements, and success criteria; create or update PROJECT_DISCOVERY.md; explicitly list unresolved questions.

### 3. Project Constitution / 项目宪法
创建或更新 PROJECT_CONSTITUTION.md，定义使命、范围、非目标、技术栈、架构原则、数据/安全/金融规则、测试/部署要求、AI 工作规则和人工审批要求。
Create or update PROJECT_CONSTITUTION.md with mission, scope, non-goals, stack, architecture principles, data/security/financial rules, testing/deployment requirements, AI working rules, and human approval requirements.

### 4. Architecture / 架构设计
提出系统架构，定义组件、职责、数据流、API 边界、数据库、外部集成、信任边界、故障边界、可观测性和部署模型；创建或更新 ARCHITECTURE.md；不得静默做出重大架构决策。
Propose the architecture and define components, responsibilities, data flows, API boundaries, database, external integrations, trust boundaries, failure boundaries, observability, and deployment; create or update ARCHITECTURE.md; do not silently make material architectural decisions.

### 5. ADR / 重大决策锁定
识别需要 ADR 的重大决策，并记录背景、拟议决策、替代方案、权衡、后果和状态。已接受的重大决策不得被静默推翻。
Identify material decisions requiring ADRs and record context, decision, alternatives, trade-offs, consequences, and status. Do not silently reverse accepted material decisions.

### 6. TASKS / 任务规划
创建或更新 TASKS.md，将项目拆分为 Epic、Feature、Task、Subtask，并定义验收标准、影响组件、依赖、测试、安全和金融考虑。
Create or update TASKS.md. Break the project into Epics, Features, Tasks, and Subtasks with acceptance criteria, affected components, dependencies, tests, and security/financial considerations.

### 7. HUMAN APPROVAL GATE / 人工审批门禁
在正式实现前停止，总结项目基线，列出需要人工批准的事项，并等待我的批准或修改意见。
Stop before substantial implementation, summarize the project baseline, list decisions requiring human approval, and wait for approval or requested changes.

### 8. Implement / 实现
审批后，一次只执行一个已批准任务。编码前读取 Constitution、Architecture、相关 ADR、Task 和适用规则。不得臆造需求、API、依赖、数据库字段或业务规则。
After approval, work one approved task at a time. Before coding, read the Constitution, Architecture, relevant ADRs, Task, and applicable rules. Do not invent requirements, APIs, dependencies, database fields, or business rules.

### 9. Verify / 验证
按适用情况执行 formatter、linter、类型检查、单元/集成/E2E/安全/回归/金融/幂等/故障测试，并准确报告验证证据。没有实际执行的测试不得声称已验证。
Run applicable formatting, linting, type checking, unit/integration/E2E/security/regression/financial/idempotency/failure tests and report exact evidence. Never claim verification that was not actually performed.

### 10. Review, Commit, Learn / 审查、提交、学习
检查 diff、秘密信息、调试代码、测试、安全、金融正确性和架构变化；做逻辑清晰的 Git commit；更新项目记忆、ADR、事故复盘和文档；只有必要时才将经验升级为全局规则。
Review diffs, secrets, debug code, tests, security, financial correctness, and architecture changes; make logical commits; update memory, ADRs, incident reviews, and docs; promote lessons to global rules only when justified.

## Decision Authority / 决策权限

AI 可自主决定 / AI may normally decide: 局部命名、格式化、局部函数拆分、测试实现细节、小范围不改变行为的重构。
AI must propose and obtain approval: 新依赖、API 契约、缓存策略、模块边界、非简单性能架构、重试策略、重大实现权衡。
Human approval is required: 金融计算语义、资金/资产状态转换、重大数据库 Schema、认证授权架构、安全边界、生产部署策略、真实资金行为、监管报送逻辑、重大架构变化、任何弱化 FinTech-Rules 的要求。
When uncertain about a material requirement, architecture decision, security boundary, financial behavior, or regulatory interpretation: DO NOT GUESS. Surface the uncertainty and ask me.
当不确定重大需求、架构、安全、金融行为或监管解释时：不要猜测，明确指出不确定性并询问我。

## Bootstrap Complete / Bootstrap 完成标准

- BOOTSTRAP_REPORT.md
- PROJECT_DISCOVERY.md
- PROJECT_CONSTITUTION.md
- ARCHITECTURE.md
- material ADRs identified / 已识别重大 ADR
- TASKS.md
- testing strategy / 测试策略
- security baseline / 安全基线
- AI/human decision authority / AI 与人工决策权限
- unresolved material questions resolved or explicitly recorded / 重大未决问题已解决或明确记录
- human approval completed / 已完成人工审批

## Why this file exists / 为什么需要这个文件

Rules define how the engineering system operates. This file defines how a human starts the system with AI. The startup context is therefore version-controlled rather than left only in chat.
Rules 定义工程系统如何运行；本文件定义人类如何与 AI 一起启动系统。因此启动上下文进入版本控制，而不是只存在于聊天中。

START_PROJECT.md → FinTech-Rules → Bootstrap → Constitution → Architecture + ADR → TASKS → Human Approval → Implementation → Verification → Memory/Learning
