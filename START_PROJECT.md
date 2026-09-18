# START PROJECT

This is the standard startup context for using FinTech-Rules with an AI coding agent.

Use this file when starting a new project. The purpose is to give the AI one stable entry point instead of repeatedly explaining the operating model in chat.

## How to use

1. Make this FinTech-Rules repository available to the AI coding agent.
2. Make the target project repository available to the same agent.
3. Give the AI the startup prompt below.
4. Do not ask it to start coding at the same time.
5. Complete the bootstrap and human approval gate.
6. Only then authorize implementation.

---

# Standard Startup Prompt

Copy the following prompt into your AI coding agent:

```text
I want to start a new project using my FinTech-Rules engineering operating system.

The FinTech-Rules repository is the governing engineering operating system for this project.

Bootstrap the project.

Do not write substantial application code yet.

First read and follow the FinTech-Rules repository, especially:
- README.md
- AGENTS.md
- rules/00-core.md
- rules/01-ai-behavior.md
- rules/02-development-workflow.md
- rules/90-ai-project-bootstrap.md
- all relevant technical, FinTech, data, API, testing, security, DevOps, and Git rules
- relevant templates
- any existing project memory or decisions

Then execute the Project Bootstrap Protocol:

1. Initialize
   - inspect the repository;
   - understand the existing code, stack, dependencies, configuration, tests, CI/CD, deployment, and Git state;
   - create or update BOOTSTRAP_REPORT.md.

2. Discover
   - conduct Project Discovery;
   - determine the problem, users, primary user journeys, scope, non-goals, data, financial/regulatory characteristics, technical requirements, and success criteria;
   - create or update PROJECT_DISCOVERY.md;
   - explicitly list unresolved questions.

3. Establish Project Constitution
   - create or update PROJECT_CONSTITUTION.md;
   - define the project mission, scope, non-goals, technology stack, architecture principles, data/security/financial rules, testing/deployment requirements, AI working rules, and human approval requirements.

4. Design Architecture
   - propose the system architecture;
   - define major components, responsibilities, data flows, API boundaries, database approach, external integrations, trust boundaries, failure boundaries, observability, and deployment model;
   - create or update ARCHITECTURE.md;
   - do not silently make material architectural decisions.

5. Lock Material Decisions
   - identify decisions that require ADRs;
   - for each material decision, provide context, proposed decision, alternatives, trade-offs, consequences, and status;
   - do not silently reverse an accepted decision later.

6. Plan Tasks
   - create or update TASKS.md;
   - break the project into Epics, Features, Tasks, and Subtasks;
   - define acceptance criteria, affected components, dependencies, tests, and security/financial considerations.

7. HUMAN APPROVAL GATE
   - stop before substantial implementation;
   - summarize the proposed project baseline;
   - clearly list decisions requiring my approval;
   - wait for my approval or requested changes.

Only after I approve the project baseline:

8. Implement
   - work one approved task at a time;
   - before coding, read the Constitution, Architecture, relevant ADRs, Task, and applicable rules;
   - make small, reviewable changes;
   - do not invent requirements, APIs, dependencies, database fields, or business rules.

9. Verify
   - run applicable formatter, linter, type checker, unit tests, integration tests, E2E tests, security checks, regression tests, and financial/idempotency/failure tests where applicable;
   - report exactly what was and was not verified;
   - never claim a test or external integration was verified unless it actually was.

10. Review, Commit, and Learn
   - inspect the diff;
   - check for unrelated changes, secrets, debug code, missing tests, security issues, financial correctness issues, and undocumented architecture changes;
   - make logical Git commits;
   - update project memory, ADRs, incident reviews, and documentation;
   - promote recurring, broadly applicable lessons into FinTech-Rules only when justified.

Decision authority:

AI may normally decide:
- local naming;
- formatting;
- local function decomposition;
- test implementation details;
- small behavior-preserving refactors.

AI must propose and obtain approval for:
- new dependencies;
- API contract changes;
- caching strategy;
- module boundary changes;
- non-trivial performance architecture;
- retry strategy;
- material implementation trade-offs.

Human approval is required for:
- financial calculation semantics;
- money/asset state transitions;
- material database schema changes;
- authentication/authorization architecture;
- security boundary changes;
- production deployment policy;
- real-money transaction behavior;
- regulatory reporting logic;
- material architecture changes;
- weakening any FinTech-Rules requirement.

When uncertain about a material requirement, architecture decision, security boundary, financial behavior, or regulatory interpretation:
DO NOT GUESS. Surface the uncertainty and ask me.

Do not write substantial application code until I approve the project baseline.
```

---

# What "Bootstrap Complete" Means

Before substantial implementation, the project should have:

- [ ] BOOTSTRAP_REPORT.md
- [ ] PROJECT_DISCOVERY.md
- [ ] PROJECT_CONSTITUTION.md
- [ ] ARCHITECTURE.md
- [ ] material ADRs identified
- [ ] initial TASKS.md
- [ ] testing strategy
- [ ] security baseline
- [ ] AI/human decision authority defined
- [ ] unresolved material questions resolved or explicitly accepted as assumptions
- [ ] human approval completed

Not every project needs every document in exactly this form. The AI should use the smallest appropriate structure while preserving the intent of the operating system.

# Why This File Exists

The rules define **how the system should operate**.

This file defines **how a human starts the system with an AI**.

Keeping the startup context in one file prevents the initial conversation from becoming another undocumented source of project rules.

The intended chain is:

```
START_PROJECT.md
      ↓
FinTech-Rules
      ↓
Project Bootstrap
      ↓
Project Constitution
      ↓
Architecture + ADR
      ↓
Task Plan
      ↓
Human Approval
      ↓
Implementation
      ↓
Verification
      ↓
Memory / Learning
```

The startup prompt is intentionally explicit. Once the AI reliably follows the protocol, it can become shorter because the detailed behavior already lives in FinTech-Rules.
