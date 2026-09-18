# FinTech-Rules

Personal AI-assisted software engineering operating system for FinTech, banking, data, APIs, testing, security, DevOps, and Git.
面向 FinTech、银行、数据、API、测试、安全、DevOps 和 Git 的个人 AI 辅助软件工程操作系统。

本仓库不是简单的 coding style guide，而是 AI 辅助开发的项目操作系统：规定 AI 如何启动项目、如何决策、何时询问人类、如何实现、如何验证，以及如何保存项目记忆。
This repository is not merely a coding style guide. It is a project operating system for AI-assisted development: how the AI starts, decides, asks, implements, verifies, and preserves project memory.

## 1. Core Idea / 核心理念

> Discover first. Agree second. Design third. Implement fourth. Verify continuously.
> 先发现，后共识；先设计，再实现；持续验证。

不要从“AI，帮我把这个应用做出来”开始，而要从“使用 FinTech-Rules 对项目执行 Bootstrap”开始。
Do not start with “AI, build this application.” Start with “Bootstrap this project using FinTech-Rules.”

## 2. 10-Step Lifecycle / 十步生命周期

1. Initialize / 初始化
2. Discover / 发现
3. Project Constitution / 项目宪法
4. Architecture / 架构
5. Decision Lock / ADR / 决策锁定
6. Task Planning / 任务规划
→ HUMAN APPROVAL / 人工审批
7. Implementation / 实现
8. Verification / 验证
9. Review / Commit / 审查与提交
10. Memory / Learning / 记忆与学习

前六步建立项目共同契约；后四步执行并持续改进这个契约。
The first six steps establish the shared project contract; the last four execute and continuously improve it.

## 3. Start a New Project / 启动新项目

START_PROJECT.md 是唯一标准启动入口，包含完整启动上下文和启动提示词。
START_PROJECT.md is the single standard startup entry point containing the complete startup context and prompt.

流程 / Process: 1) 提供 FinTech-Rules；2) 提供目标仓库；3) 使用 START_PROJECT.md；4) 完成步骤 1–6；5) 审查基线；6) 批准或修改；7) 才允许正式实现。
## 4. Project Artifacts / 项目核心文件

标准 Bootstrap 项目通常包含：AGENTS.md、README.md、PROJECT_DISCOVERY.md、PROJECT_CONSTITUTION.md、SPEC.md、ARCHITECTURE.md、TASKS.md、CHANGELOG.md、adr/、memory/、src/、tests/ 和 .github/workflows/。
A bootstrapped project normally contains these artifacts. Not every project needs every file; use the smallest appropriate structure.

## 5. Project Constitution / 项目宪法

PROJECT_CONSTITUTION.md 是最重要的项目级治理文件，固定使命、范围、非目标、技术栈、架构、数据、安全、金融、测试、部署、AI 和人工审批规则。
PROJECT_CONSTITUTION.md is the key project-specific governance document covering mission, scope, non-goals, stack, architecture, data, security, financial, testing, deployment, AI, and human approval rules.
它可以具体化 FinTech-Rules，但不得静默弱化核心安全、金融完整性、审计性和验证要求。
It specializes FinTech-Rules but must not silently weaken core safety, financial integrity, auditability, or verification requirements.

## 6. Decision Authority / 决策权限

AI 可自主决定：局部命名、函数拆分、格式化、测试实现细节、小范围行为保持型重构。
AI may normally decide: local naming, function decomposition, formatting, test implementation details, and small behavior-preserving refactors.
AI 必须提出并获批：新依赖、API 契约变化、缓存策略、模块边界、非简单性能架构、重试策略、重大实现权衡。
AI must propose and obtain approval for: new dependencies, API contract changes, caching, module boundaries, non-trivial performance architecture, retry strategy, and material trade-offs.
人工必须审批：金融计算语义、资金/资产状态转换、重大数据库 Schema、认证授权、安全边界、生产部署、真实资金行为、监管报送逻辑和重大架构变化。
Human approval is required for financial calculation semantics, money/asset state transitions, material schema changes, auth architecture, security boundaries, production deployment, real-money behavior, regulatory reporting, and material architecture changes.

## 7. Locked Decisions / 决策锁定

重大决策记录在 ADR 中。后续如需改变，应基于新证据提出新方案，经批准后建立新 ADR，而不是静默改写旧决策。
Material decisions are recorded as ADRs. If change becomes necessary, use new evidence → new proposal → approval → new ADR, rather than silently rewriting the old decision.

## 8. Verification vs Testing / 验证与测试

测试通过不等于系统整体正确。AI 必须报告改了什么、测了什么、通过/失败什么、什么没测、环境限制和剩余风险。
Passing tests do not automatically prove the whole system is correct. The AI must report changes, tests, passes/failures, untested areas, environment limits, and remaining risks.

## 9. FinTech Principles / FinTech 原则

金额使用 Decimal；金融操作幂等；保持审计性；明确状态转换；正确处理重试和重复请求；不得静默丢弃金融失败；按需维护数据血缘；测试舍入和边界；区分业务日期与系统时间；保护秘密和敏感数据；生产变更尽量可回滚。
Use Decimal for monetary calculations; make financial operations idempotent; preserve auditability; model state transitions; handle retries and duplicates; never silently discard financial failures; maintain lineage where required; test rounding/boundaries; distinguish business date from system time; protect secrets; keep production changes reversible where practical.

## 10. Rule Hierarchy / 规则层级

Core Rules → AI Behavior → Technical Rules → Domain Rules → Project Constitution → Task / Implementation Details
核心规则 → AI 行为 → 技术规则 → 领域规则 → 项目宪法 → 任务/实现细节
项目规则可以具体化上层规则，但不得静默弱化更高优先级的安全或金融完整性要求。
Project rules may specialize higher-level rules but must not silently weaken higher-priority safety or financial-integrity requirements.

## 11. Rule Evolution / 规则演进

Project → Failure/Lesson → Document → Generalize → Update FinTech-Rules → Version + Changelog → Future Projects
项目 → 失败/经验 → 文档化 → 提炼 → 更新 FinTech-Rules → 版本与变更记录 → 未来项目受益
只有重复、普适、已充分理解且不会造成不必要约束的经验，才应升级为全局规则。
Only recurring, broadly applicable, sufficiently understood lessons should become global rules.

## 12. Philosophy / 哲学

Correctness over speed / 正确性优先于速度
Clarity over cleverness / 清晰优先于炫技
Explicit decisions over hidden assumptions / 显式决策优先于隐藏假设
Evidence over claims / 证据优先于声明
Human approval for material decisions / 重大决策人工审批
Continuous learning instead of static rules / 持续学习而非静态规则

目标不是消灭人的判断，而是让 AI 辅助开发变得可重复、可审计、可维护，并越来越可靠。
The goal is not to eliminate human judgment, but to make AI-assisted development repeatable, auditable, maintainable, and increasingly reliable.