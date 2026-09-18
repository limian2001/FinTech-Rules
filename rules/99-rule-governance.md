# Rule Governance

## Purpose

This document defines how FinTech-Rules itself evolves without becoming inconsistent.

## Rule Precedence

Unless a more specific higher-priority safety requirement applies:

1. Core safety and financial-integrity rules
2. AI behavior rules
3. Technical rules
4. Domain rules
5. Project Constitution
6. Project-specific implementation details

A project may specialize a rule, but must not silently weaken a higher-priority requirement.

## Rule Changes

When changing a rule:

1. identify the problem;
2. provide evidence or a reproducible example;
3. determine whether the lesson is project-specific or general;
4. update the smallest appropriate rule;
5. update documentation/templates if needed;
6. update CHANGELOG;
7. increment VERSION when appropriate;
8. commit the change.

## Versioning

Use semantic-style versioning:

- MAJOR — incompatible changes to the operating model or rule interpretation
- MINOR — new rules, workflows, or capabilities that are backward compatible
- PATCH — clarification, typo fix, or non-behavioral documentation correction

## Rule Quality

A good rule should be:

- explicit;
- testable where possible;
- actionable;
- reusable;
- minimally ambiguous;
- consistent with other rules.

Avoid rules that merely express vague preferences.

## Conflict Resolution

When two rules appear to conflict:

1. identify both rules;
2. determine precedence;
3. explain the conflict;
4. do not silently choose a convenient interpretation;
5. update the rules if the conflict is structural.

## Learning Loop

Project lessons should not automatically become global rules.

Promote a lesson to global rules only when it is:

- recurring;
- broadly applicable;
- sufficiently understood;
- unlikely to create harmful constraints elsewhere.

## Templates vs Rules

Rules define required behavior.

Templates provide reusable structure.

Memory records what happened or was decided.

Do not put historical project decisions into global rules.
