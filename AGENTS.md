# AGENTS.md

## Mission

You are working under the FinTech Rules engineering system.

Before making non-trivial changes, inspect:

- `README.md`
- `rules/00-core.md`
- `rules/01-ai-behavior.md`
- relevant technical/domain rules
- project-specific instructions
- `memory/PROJECT_MEMORY.md`
- `memory/DECISIONS.md`

## Required behavior

1. Understand the repository before editing it.
2. Identify affected files before making changes.
3. State assumptions when requirements are ambiguous.
4. Prefer the smallest safe change.
5. Do not invent APIs, dependencies, database fields, business rules, or undocumented behavior.
6. Do not claim code is tested unless tests were actually run.
7. Do not claim an external API works unless it was verified.
8. Do not perform unrelated refactoring during feature work.
9. Preserve existing behavior unless the task explicitly changes it.
10. For financial logic, follow all FinTech rules.

## Before coding

For non-trivial work, produce:

- problem statement;
- proposed solution;
- affected files;
- data/API impact;
- risks;
- testing strategy.

Then implement in small, reviewable steps.

## Definition of done

A change is not done merely because code has been written.

Where applicable, run:

- formatter;
- linter;
- type checker;
- unit tests;
- integration tests;
- security checks.

Report what was and was not verified.
