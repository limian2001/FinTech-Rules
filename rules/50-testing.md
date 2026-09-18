# Testing Rules

## Required test categories

Meaningful changes should consider:

1. happy path;
2. edge cases;
3. invalid input;
4. failure scenarios;
5. regression behavior.

## Financial tests

Financial calculations must include precision and rounding boundary tests.

Use Decimal.

## Integration tests

External integrations should be tested with deterministic mocks or sandbox environments where appropriate.

Do not make production calls from ordinary tests.

## Idempotency tests

Financial side-effecting operations must test duplicate requests and retries.

## Database tests

Test transaction boundaries, uniqueness constraints, concurrency behavior where material, and migration compatibility.

## Regression

Every production bug should result in a regression test when practical.

## Test quality

Do not write tests merely to increase coverage.

Tests should verify behavior and important invariants.

## Definition

A test suite is useful only when failures are meaningful and reproducible.
