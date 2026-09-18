# FinTech Rules

Personal AI-assisted software engineering rules for FinTech, banking, data, APIs, testing, security, DevOps, and Git.

## Purpose

This repository is the reusable engineering rulebook for my Vibecoding workflow.

The hierarchy is:

1. Core rules
2. AI behavior rules
3. Technical rules
4. Domain rules
5. Project-specific rules

Project-specific rules may add constraints, but should not silently weaken core safety or financial-integrity rules.

## Repository structure

- `rules/` — engineering rules
- `templates/` — reusable project documents
- `memory/` — project decisions and accumulated lessons
- `AGENTS.md` — instructions for AI coding agents

## Versioning

Rules are versioned with Git.

When a recurring AI failure is discovered:

1. reproduce/document the problem;
2. decide whether a rule is needed;
3. update the relevant rule;
4. record the change in Git;
5. apply the new rule to future projects.

## Rule philosophy

Prefer:

- correctness over speed;
- simple architecture over unnecessary abstraction;
- explicit behavior over hidden magic;
- small reversible changes over broad refactors;
- verified facts over assumptions;
- tests and evidence over claims.

This is a living engineering system, not a static style guide.
