# Development Workflow

This workflow is mandatory for non-trivial changes.

## 1. IDEA

Start by defining:

- problem;
- user/business value;
- scope;
- non-goals;
- constraints.

Do not start coding merely because an idea has been described.

## 2. SPEC

Create or update `SPEC.md`.

The specification should define:

- functional requirements;
- business rules;
- inputs and outputs;
- failure scenarios;
- security considerations;
- financial considerations;
- acceptance criteria.

Ambiguities must be identified before implementation.

## 3. ARCHITECTURE

For changes larger than a small localized fix, create or update `ARCHITECTURE.md`.

Cover:

- components;
- data flow;
- API flow;
- database changes;
- external integrations;
- failure handling;
- security;
- observability;
- testing;
- migration/compatibility;
- risks.

Do not implement a substantial feature before its architecture is understood.

## 4. TASK BREAKDOWN

Create `TASK.md`.

Break the work into small, independently verifiable tasks.

Each task should have:

- objective;
- affected files;
- implementation steps;
- tests;
- verification;
- risks.

## 5. IMPLEMENTATION

Implement one logical task at a time.

Rules:

- make minimal changes;
- follow existing architecture;
- do not mix unrelated refactoring;
- preserve existing behavior;
- update tests with behavior changes;
- update documentation when needed.

## 6. TEST

Testing must happen continuously, not only at the end.

At minimum, consider:

- unit tests;
- integration tests;
- API tests;
- database tests;
- edge cases;
- failure paths;
- regression tests.

Financial code must additionally test:

- Decimal precision;
- rounding;
- idempotency;
- duplicate requests;
- retries;
- partial failures;
- reconciliation.

## 7. SECURITY VERIFICATION

Before declaring a change complete, review:

- secrets;
- authentication;
- authorization;
- input validation;
- sensitive data exposure;
- dependency vulnerabilities;
- logging;
- configuration;
- destructive operations.

Never use production credentials for development or testing.

## 8. CODE REVIEW

Review the actual diff.

Check:

- correctness;
- scope;
- architecture;
- security;
- error handling;
- test coverage;
- observability;
- financial integrity.

The reviewer should challenge assumptions, not merely inspect formatting.

## 9. CI VERIFICATION

Run applicable automated checks:

- formatter;
- linter;
- type checker;
- unit tests;
- integration tests;
- security scanning;
- build.

A failed check must be investigated. Do not bypass checks merely to obtain a green build.

## 10. COMMIT

Create a focused Git commit after verification.

Commit messages should describe the logical change.

## 11. DEPLOYMENT

Before deployment:

- verify configuration;
- verify migrations;
- verify dependencies;
- verify secrets;
- verify rollback/recovery strategy;
- verify monitoring.

Prefer staged or incremental deployment for material changes.

## 12. POST-DEPLOYMENT VERIFICATION

After deployment:

- verify health;
- verify key business flows;
- inspect logs;
- inspect metrics/alerts;
- verify data integrity.

For financial systems, perform reconciliation where applicable.

## 13. FEEDBACK

Record:

- bugs;
- operational incidents;
- recurring AI mistakes;
- architecture lessons;
- new rules.

If the same failure can recur, convert the lesson into a rule or automated check.

## 14. DONE

A task is complete only when implementation, tests, security, verification, documentation, and operational considerations have been addressed.

Never equate "code generated" with "task complete".
