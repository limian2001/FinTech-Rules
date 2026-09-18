# Pull Request Checklist

## Scope

- [ ] Change is limited to the requested scope.
- [ ] No unrelated refactoring was introduced.

## Correctness

- [ ] Existing behavior is preserved unless intentionally changed.
- [ ] Edge cases were considered.

## Financial integrity

- [ ] Decimal is used for monetary calculations.
- [ ] Idempotency is implemented where required.
- [ ] Failures are not silently discarded.
- [ ] Financial state changes are auditable.

## Security

- [ ] No secrets are committed.
- [ ] Sensitive information is not unnecessarily logged.
- [ ] Authorization is checked for protected operations.

## Testing

- [ ] Unit tests added/updated.
- [ ] Integration tests added/updated where needed.
- [ ] Regression tests added where appropriate.
- [ ] Tests actually ran.

## Verification

- [ ] Lint/format checks passed.
- [ ] Type checks passed where applicable.
- [ ] Test results are known.
- [ ] Remaining risks are documented.
