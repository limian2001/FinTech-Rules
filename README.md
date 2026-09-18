# FinTech-Rules

Personal AI-assisted software engineering operating system for FinTech, banking, data, APIs, testing, security, DevOps, and Git.

This repository is not just a coding style guide.

It is a **project operating system for AI-assisted development**: it tells an AI agent how to start a project, how to make decisions, when to ask the human, how to implement, how to verify, and how to preserve project memory so that the project does not become inconsistent over time.

## 1. The Core Idea

The system follows one principle:

> **Discover first. Agree second. Design third. Implement fourth. Verify continuously.**

A new project should not begin with:

> "AI, build this application."

Instead, start with:

> "Bootstrap this project using FinTech-Rules."

The AI should then guide the project through the 10-step bootstrap protocol before substantial implementation.

## 2. The 10-Step Lifecycle

```
1. Initialize
       ↓
2. Discover
       ↓
3. Project Constitution
       ↓
4. Architecture
       ↓
5. Decision Lock / ADR
       ↓
6. Task Planning
       ↓
   HUMAN APPROVAL
       ↓
7. Implementation
       ↓
8. Verification
       ↓
9. Review / Commit
       ↓
10. Memory / Learning
       ↓
   Next Task
```

The first six steps establish a shared project contract.

Steps 7–10 execute and continuously improve that contract.

## 3. How to Start a New Project

### Option A — Give the rules repository to your AI coding agent

Make this repository available to the agent together with the project you want to build.

Then give the agent a startup instruction such as:

```text
Bootstrap this project using FinTech-Rules.

Do not start substantial implementation yet.

Read the rules, inspect the repository, generate the bootstrap report and project discovery, identify unresolved questions, and guide me through the 10-step Project Bootstrap Protocol.

Stop at the human approval gate before substantial implementation.
```

The important point is **not** to tell the AI the entire process every time. The process is encoded in `rules/90-ai-project-bootstrap.md`.

### Option B — Start from an empty repository

For an empty repository, the AI should:

1. load FinTech-Rules;
2. inspect the empty repository;
3. create the initial project documentation;
4. ask discovery questions;
5. create the Project Constitution;
6. propose architecture;
7. identify material decisions;
8. create the initial task plan;
9. wait for human approval;
10. establish the development/testing/security baseline;
11. begin the first small implementation task.

## 4. What the AI Creates

A properly bootstrapped project should normally contain:

```
project/
├── AGENTS.md
├── README.md
├── PROJECT_DISCOVERY.md
├── PROJECT_CONSTITUTION.md
├── SPEC.md
├── ARCHITECTURE.md
├── TASKS.md
├── CHANGELOG.md
│
├── docs/
│
├── adr/
│   ├── ADR-001-*.md
│   └── ...
│
├── memory/
│   ├── PROJECT_MEMORY.md
│   └── DECISIONS.md
│
├── src/
├── tests/
│
└── .github/
    └── workflows/
```

Not every project needs every file. The AI should use the smallest structure that is appropriate.

## 5. The Project Constitution

`PROJECT_CONSTITUTION.md` is the most important project-specific document.

It records the rules that must remain stable during development:

- mission;
- scope;
- non-goals;
- technology stack;
- architecture principles;
- data principles;
- security principles;
- financial rules;
- testing requirements;
- deployment requirements;
- AI working rules;
- human approval requirements.

The Constitution specializes FinTech-Rules.

It must not silently weaken core safety, financial-integrity, security, auditability, or verification requirements.

## 6. Decision Authority

One of the most important features is explicit AI/human decision authority.

### AI can normally decide

Examples:

- naming;
- local function decomposition;
- formatting;
- test implementation details;
- small behavior-preserving refactors.

### AI should propose and obtain approval

Examples:

- new dependencies;
- API contract changes;
- caching strategy;
- module boundary changes;
- non-trivial performance architecture;
- retry strategy.

### Human approval is required

Examples:

- financial calculation semantics;
- money/asset state transitions;
- material database schema changes;
- authentication/authorization architecture;
- security boundary changes;
- production deployment policy;
- real-money transaction behavior;
- regulatory reporting logic;
- material architecture changes.

This prevents the AI from silently changing the project's fundamental assumptions.

## 7. Architecture Decisions Are Locked

Material decisions are recorded as ADRs.

If a later change is necessary, the AI should not silently rewrite the original decision.

Instead:

```
Existing Decision
      ↓
New Evidence
      ↓
New Proposal
      ↓
Human Approval
      ↓
New ADR
      ↓
Architecture Update
```

This is one of the main mechanisms that keeps a long-running AI project coherent.

## 8. Verification Is Not the Same as Testing

The system deliberately separates implementation, testing, and verification.

A successful test run does not automatically prove that the whole system is correct.

The AI should report:

- what changed;
- what was tested;
- what passed;
- what failed;
- what was not tested;
- environmental limitations;
- remaining risks.

Never claim a test, external API, deployment, or verification step that was not actually performed.

## 9. FinTech-Specific Principles

When financial or regulatory behavior is involved, the rules become stricter.

Examples:

- use `Decimal` for monetary calculations;
- make financial operations idempotent;
- preserve auditability;
- explicitly model state transitions;
- handle retries and duplicate requests;
- never silently discard financial failures;
- maintain data lineage where required;
- test rounding and boundary conditions;
- distinguish business date from system time;
- protect secrets and sensitive data;
- make production changes reversible where practical.

See `rules/20-fintech.md` and the related technical/security rules.

## 10. Repository Structure

```
FinTech-Rules/
│
├── README.md
├── AGENTS.md
├── VERSION
├── CHANGELOG.md
│
├── rules/
│   ├── 00-core.md
│   ├── 01-ai-behavior.md
│   ├── 02-development-workflow.md
│   ├── 10-python.md
│   ├── 20-fintech.md
│   ├── 30-data.md
│   ├── 40-api.md
│   ├── 50-testing.md
│   ├── 51-test-verification.md
│   ├── 60-security.md
│   ├── 61-security-workflow.md
│   ├── 70-devops.md
│   ├── 80-git.md
│   ├── 90-ai-project-bootstrap.md
│   └── 99-rule-governance.md
│
├── templates/
│   ├── PROJECT_DISCOVERY.md
│   ├── PROJECT_CONSTITUTION.md
│   ├── BOOTSTRAP_REPORT.md
│   ├── SPEC.md
│   ├── ARCHITECTURE.md
│   ├── TASK.md
│   ├── ADR.md
│   ├── TEST_PLAN.md
│   ├── SECURITY_REVIEW.md
│   ├── PR_CHECKLIST.md
│   ├── RELEASE_CHECKLIST.md
│   ├── DEFINITION_OF_DONE.md
│   └── INCIDENT_REVIEW.md
│
└── memory/
    ├── PROJECT_MEMORY.md
    └── DECISIONS.md
```

## 11. Rule Hierarchy

The system is layered:

```
Core Rules
    ↓
AI Behavior
    ↓
Technical Rules
    ↓
Domain Rules
    ↓
Project Constitution
    ↓
Task / Implementation Details
```

Project-specific rules can specialize the general system.

They should not silently weaken higher-priority safety or financial-integrity requirements.

## 12. How the System Evolves

This is a living engineering system.

When the AI repeatedly makes the same class of mistake:

```
Project
  ↓
Failure / Lesson
  ↓
Document
  ↓
Generalize
  ↓
Update FinTech-Rules
  ↓
Version + Changelog
  ↓
Future Projects Benefit
```

Do not promote every project-specific problem into a global rule.

A lesson should become a global rule when it is recurring, broadly applicable, sufficiently understood, and unlikely to create harmful constraints elsewhere.

## 13. Recommended First Conversation With AI

For a brand-new project, the shortest useful starting prompt is:

```text
I want to start a new project using my FinTech-Rules engineering operating system.

Bootstrap the project.

Do not write substantial application code yet.

First:
1. read the rules;
2. inspect the repository;
3. create the Bootstrap Report;
4. conduct Project Discovery;
5. identify unresolved questions;
6. create the Project Constitution;
7. propose the architecture;
8. identify material ADR decisions;
9. create the initial task plan;
10. stop for my approval.

Do not invent requirements or silently make material architectural decisions.
```

After approval, use:

```text
The project baseline is approved.

Proceed to the next implementation task according to FinTech-Rules.

Before coding, read the Constitution, Architecture, relevant ADRs, and Task.
Implement only the approved scope, then run the required verification and report the evidence.
```

## 14. Updating FinTech-Rules

When this repository itself changes:

1. identify the problem or improvement;
2. determine the correct rule/template;
3. make the smallest coherent change;
4. update `CHANGELOG.md`;
5. update `VERSION` when appropriate;
6. review the resulting diff;
7. commit the change.

See `rules/99-rule-governance.md`.

## 15. Philosophy

This system is designed around:

- **Correctness over speed**
- **Clarity over cleverness**
- **Small changes over uncontrolled generation**
- **Explicit decisions over hidden assumptions**
- **Evidence over claims**
- **Security and financial integrity by default**
- **Human approval for material decisions**
- **Continuous learning instead of static rules**

The goal is not to eliminate human judgment.

The goal is to make AI-assisted development **repeatable, auditable, maintainable, and increasingly reliable**.
