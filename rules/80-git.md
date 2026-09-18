# Git Rules

## Commits

Keep commits logical and focused.

Preferred prefixes:

- feat
- fix
- refactor
- test
- docs
- chore
- build
- ci

Example:

feat: add idempotent payment processing

## Commit scope

Avoid mixing:

- feature work;
- unrelated formatting;
- large refactoring;
- documentation cleanup

in one commit.

## Branches

Use short-lived branches for meaningful changes.

## Pull requests

A PR should explain:

- what changed;
- why;
- important design decisions;
- testing performed;
- known limitations.

## History

Do not rewrite shared history unless explicitly intended.

## Secrets

Never commit secrets, even temporarily.

## Diff review

Before committing:

- inspect changed files;
- inspect the diff;
- remove accidental changes;
- verify generated files.
