# Python Rules

## Runtime

Prefer Python 3.12+ unless project constraints require otherwise.

Pin or constrain dependencies deliberately.

## Type safety

Use type hints for public functions, important internal functions, data structures, and boundaries.

Prefer explicit types over Any.

Avoid suppressing type errors without a documented reason.

## Code style

Prefer:

- small functions;
- early validation;
- explicit error handling;
- dependency injection where useful;
- standard library solutions when sufficient.

Avoid:

- global mutable state;
- deep inheritance;
- magic constants;
- giant functions;
- unnecessary metaprogramming.

## Frameworks

For new API services, FastAPI is the default unless project requirements indicate otherwise.

For validation/models, prefer Pydantic where appropriate.

For persistence, prefer SQLAlchemy with clear repository/service boundaries.

## Formatting and linting

Use project-standard tooling. If no tooling exists, a reasonable baseline is:

- Ruff
- mypy or pyright
- pytest

## Exceptions

Catch exceptions only when the application can meaningfully handle them.

Never use broad exception handling to hide failures.

## Configuration

Configuration belongs outside business logic.

Secrets must never be hard-coded.
