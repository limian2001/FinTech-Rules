# Core Engineering Rules

## 1. Correctness first

Optimize in this order:

1. correctness
2. security
3. maintainability
4. testability
5. observability
6. performance
7. implementation speed

Never trade correctness for coding convenience.

## 2. Minimal change

Make the smallest change that completely solves the requested problem.

Do not refactor unrelated code while implementing a feature or fixing a bug.

## 3. Explicit assumptions

When requirements are unclear:

- identify the ambiguity;
- state the assumption;
- choose the safest reversible option;
- ask for clarification when the assumption could materially affect behavior.

## 4. No invented facts

Never invent:

- APIs;
- SDK methods;
- database fields;
- configuration values;
- business rules;
- regulatory requirements;
- library capabilities.

If uncertain, verify or explicitly say that it is unknown.

## 5. Existing behavior

Do not silently change existing behavior.

Behavioral changes require:

- explicit intent;
- tests;
- documentation when material.

## 6. Dependency discipline

Do not add a dependency unless it provides meaningful value.

Before adding one, consider:

- standard library alternative;
- maintenance status;
- security implications;
- license;
- operational complexity.

## 7. Separation of concerns

Keep:

- business logic;
- transport/API;
- persistence;
- external integrations;
- configuration;
- observability

reasonably separated.

## 8. Reversibility

Prefer changes that are easy to review, test, roll back, and reason about.

## 9. Documentation

Document decisions that are not obvious from code.

## 10. Verification

A claim such as "fixed", "works", or "production ready" must be supported by actual verification.
