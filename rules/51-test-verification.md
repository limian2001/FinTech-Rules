# Test and Verification Rules

Testing and verification are separate concepts.

- Tests determine whether defined behavior passes.
- Verification determines whether the implementation actually satisfies the intended requirement.

Both are required.

## Test pyramid

Prefer:

1. unit tests;
2. integration tests;
3. end-to-end tests where justified.

Use the smallest test level that provides meaningful confidence.

## Before testing

Define what must be proven.

For each meaningful change identify:

- expected behavior;
- important invariants;
- failure behavior;
- security properties;
- financial properties where applicable.

## Unit tests

Test:

- normal behavior;
- boundary values;
- invalid inputs;
- exceptions;
- state transitions.

Avoid tests that only reproduce implementation details.

## Integration tests

Verify important boundaries:

- database;
- message queues;
- external APIs;
- authentication;
- serialization;
- migrations.

Use deterministic test environments.

## End-to-end tests

Use E2E tests for critical user/business journeys.

Do not rely exclusively on E2E tests because failures are harder to diagnose.

## Financial verification

For financial operations verify:

- amount;
- currency;
- precision;
- rounding;
- balance effects;
- transaction state;
- idempotency;
- duplicate handling;
- retry behavior;
- audit records;
- reconciliation.

## Failure testing

Explicitly test:

- timeout;
- network failure;
- dependency failure;
- database failure;
- invalid upstream data;
- partial success;
- duplicate delivery.

## Regression

Every important production bug should result in a regression test where practical.

## Verification evidence

When reporting completion, state:

- checks executed;
- commands used;
- result;
- checks not executed;
- remaining risks.

Never report unexecuted checks as passed.

## Manual verification

For UI, workflow, configuration, deployment, and other areas not fully covered by automated tests, perform targeted manual verification and document the result.
