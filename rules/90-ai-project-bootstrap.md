# AI Project Bootstrap Protocol

## Purpose

This protocol defines how a new project is started under FinTech-Rules.

The goal is to establish project rules, scope, architecture, decision authority, testing, security, and delivery expectations **before substantial implementation begins**.

The AI must not treat a new project as an open-ended coding request. It must first establish a shared project contract with the human.

## Core principle

> Discover first. Agree second. Design third. Implement fourth. Verify continuously.

For a new project, the default sequence is:

1. Initialize
2. Discover
3. Establish Project Constitution
4. Design Architecture
5. Lock Decisions
6. Plan Tasks
7. Implement
8. Verify
9. Review and Commit
10. Record Memory and Learn

Steps 1–6 are primarily about alignment. Substantial implementation begins only after the human has approved the project baseline.

---

## Step 1 — Initialize

### AI must

Read, in order:

1. project `AGENTS.md` if present;
2. project `README.md` if present;
3. applicable FinTech-Rules;
4. project templates;
5. project memory and decisions if present.

Then inspect the repository:

- directory structure;
- existing source code;
- Git status/history;
- language/runtime versions;
- dependencies;
- database;
- external services;
- configuration;
- tests;
- CI/CD;
- deployment artifacts;
- documentation.

### AI output

Create or propose:

`BOOTSTRAP_REPORT.md`

It must contain:

- detected project type;
- detected technology stack;
- current implementation status;
- existing capabilities;
- unknowns;
- risks;
- missing information;
- recommended next questions.

### Restriction

Do not redesign or refactor the project during initialization.

---

## Step 2 — Discover

Create or complete:

`PROJECT_DISCOVERY.md`

The AI must ask questions rather than invent answers.

### Business

- What problem does the project solve?
- Who are the users?
- What are the primary user journeys?
- What is the success criterion?

### Scope

- What is in V1?
- What is explicitly out of scope?
- What may be considered later?

### Data

- What data enters the system?
- Where does it originate?
- What data is sensitive?
- What must be retained?
- What must be auditable?

### Financial / regulatory

Where applicable:

- Does the system handle money?
- Does it calculate financial values?
- Does it execute transactions?
- Does it hold assets?
- Does it process regulatory data?
- Does it contain personally identifiable or otherwise sensitive information?

### Technical

- Required runtime?
- Required database?
- Required APIs?
- Required third-party services?
- Deployment target?
- Availability/reliability expectations?

### Human decisions

Unresolved questions must be listed explicitly.

The AI must not silently convert unanswered questions into requirements.

---

## Step 3 — Establish Project Constitution

Create:

`PROJECT_CONSTITUTION.md`

This is the project's governing contract.

It should define:

- Mission
- Scope
- Non-goals
- Users
- Technology stack
- Architecture principles
- Data principles
- Security principles
- Financial rules
- Testing requirements
- Deployment requirements
- AI working rules
- Human approval requirements

### Constitution hierarchy

Project Constitution may specialize general FinTech-Rules, but it must not silently weaken:

- financial integrity;
- security requirements;
- auditability;
- verification honesty;
- data protection;
- production safety.

If a project needs an exception, document it explicitly and obtain human approval.

---

## Step 4 — Design Architecture

Create or update:

`ARCHITECTURE.md`

Before substantial coding, define at minimum:

- system context;
- major components;
- responsibilities;
- data flow;
- API boundaries;
- database model at an appropriate level;
- external integrations;
- trust boundaries;
- failure boundaries;
- observability;
- deployment model;
- scalability assumptions where relevant.

For changes involving more than a small local implementation, explain:

- why this architecture was chosen;
- important alternatives;
- major trade-offs;
- known risks.

Do not introduce architecture merely because it is fashionable or theoretically extensible.

---

## Step 5 — Lock Decisions

Create ADRs for material architectural or business-technical decisions.

Examples:

- database choice;
- external data source;
- authentication model;
- authorization model;
- event vs CRUD architecture;
- transaction/idempotency strategy;
- deployment model;
- regulatory data lineage strategy.

Use:

`templates/ADR.md`

A decision should contain:

- context;
- decision;
- alternatives considered;
- consequences;
- status.

### Decision rule

Once a material decision is accepted, AI must treat it as a project constraint.

If later evidence suggests changing it:

1. identify the existing decision;
2. explain the new evidence;
3. propose the replacement;
4. describe migration/risk;
5. obtain human approval;
6. create a new ADR;
7. update Architecture and Constitution if necessary.

Do not silently reverse an accepted decision.

---

## Step 6 — Plan Tasks

Create or update:

`TASKS.md`

Break work into:

`Epic → Feature → Task → Subtask`

Every meaningful task should define:

- goal;
- inputs;
- outputs;
- affected files/components;
- dependencies;
- acceptance criteria;
- tests;
- security considerations;
- data/financial considerations where applicable.

### Human approval gate

Before substantial implementation, the human should approve:

- scope;
- Constitution;
- Architecture;
- material ADRs;
- initial task plan;
- decision authority boundaries.

The AI may continue only with explicitly approved assumptions where appropriate.

---

# Implementation Lifecycle

## Step 7 — Implement

For each task:

1. read the relevant rules;
2. read Constitution;
3. read Architecture;
4. read relevant ADRs;
5. read the task;
6. inspect affected files;
7. propose a small implementation plan;
8. implement;
9. test locally where possible.

Prefer vertical, reviewable increments over large generated code dumps.

---

## Step 8 — Verify

Verification is separate from implementation.

Run applicable:

- unit tests;
- integration tests;
- API tests;
- end-to-end tests;
- financial correctness tests;
- idempotency tests;
- failure/retry tests;
- security checks;
- formatter;
- linter;
- type checker;
- regression tests.

Report:

- what changed;
- what was tested;
- what passed;
- what failed;
- what was not tested;
- environmental limitations;
- remaining risks.

Never claim verification that did not occur.

---

## Step 9 — Review and Commit

Before committing:

- inspect the diff;
- check for unrelated changes;
- check for secrets;
- check for debug code;
- check architecture consistency;
- check tests;
- check security;
- check financial integrity;
- check documentation.

Use logical Git commits following `80-git.md`.

A commit is not proof that the implementation is correct.

---

## Step 10 — Memory and Learning

After meaningful work, update the appropriate project memory:

- `memory/PROJECT_MEMORY.md`
- `memory/DECISIONS.md`
- ADRs
- incident reviews
- project documentation

### Rule evolution

If the same class of mistake appears repeatedly:

1. document the incident;
2. identify the general lesson;
3. determine whether it belongs in project documentation or global rules;
4. if general, update FinTech-Rules;
5. version the rule change;
6. apply the improved rule to future projects.

This creates a learning loop:

`Project → Failure/Lesson → Rule Improvement → Future Projects`

---

# Decision Authority

## AI may decide autonomously

Examples:

- variable/function naming;
- local function decomposition;
- formatting;
- test implementation details;
- small local refactors that preserve behavior.

## AI may propose, but should obtain approval

Examples:

- new dependency;
- API contract change;
- database index strategy;
- caching strategy;
- module boundary changes;
- retry strategy;
- non-trivial performance architecture.

## Human approval required

Examples:

- financial calculation semantics;
- money/asset state transitions;
- database schema migrations with material impact;
- authentication/authorization architecture;
- security boundary changes;
- production deployment policy;
- real-money transaction behavior;
- regulatory reporting logic;
- material architecture changes;
- changes that weaken a FinTech-Rules requirement.

---

# Bootstrap Completion Criteria

A project is considered bootstrapped only when:

- [ ] Discovery is documented
- [ ] Scope and non-goals are explicit
- [ ] Project Constitution exists
- [ ] Architecture is documented
- [ ] Material decisions have ADRs
- [ ] Initial tasks are defined
- [ ] Testing strategy exists
- [ ] Security baseline exists
- [ ] Decision authority is understood
- [ ] Human approval gate has been completed
- [ ] Initial implementation can proceed without guessing core requirements

The objective is not to create documents for their own sake.

The objective is to prevent the project from accumulating hidden assumptions and inconsistent decisions.
