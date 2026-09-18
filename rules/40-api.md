# API Rules

## Contracts

Define:

- request schema;
- response schema;
- authentication;
- authorization;
- errors;
- versioning;
- timeout expectations.

## Validation

Validate input at the boundary.

Never trust client-provided financial values, identifiers, status transitions, or permissions.

## Errors

Use structured, stable error responses.

Do not expose:

- secrets;
- stack traces;
- internal credentials;
- sensitive infrastructure details.

## Idempotency

Any API that can cause financial side effects must define idempotency behavior.

## External integrations

Every external integration must specify:

- timeout;
- retry policy;
- backoff;
- error classification;
- logging;
- correlation ID;
- circuit-breaking strategy where appropriate.

## Compatibility

Avoid breaking existing consumers without an explicit versioning/migration strategy.

## Rate limits

Respect provider rate limits and implement backoff where required.

## Observability

Record enough information to trace a request without logging sensitive secrets or unnecessary personal data.
