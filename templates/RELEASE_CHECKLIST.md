# Release Checklist

## Code

- [ ] Scope reviewed.
- [ ] Diff reviewed.
- [ ] No accidental files changed.
- [ ] Documentation updated where required.

## Tests

- [ ] Unit tests passed.
- [ ] Integration tests passed where applicable.
- [ ] E2E tests passed where applicable.
- [ ] Regression tests passed.

## Security

- [ ] No secrets committed.
- [ ] Security review completed where required.
- [ ] Dependency/security checks passed.
- [ ] Production credentials/configuration verified.

## Database

- [ ] Migration reviewed.
- [ ] Backward compatibility considered.
- [ ] Backup/recovery considered.

## FinTech

- [ ] Decimal used for monetary calculations.
- [ ] Idempotency verified.
- [ ] Financial state transitions verified.
- [ ] Audit trail verified.
- [ ] Reconciliation considered.

## Deployment

- [ ] Environment verified.
- [ ] Monitoring/alerts verified.
- [ ] Rollback/recovery plan verified.

## Post-deployment

- [ ] Health checks passed.
- [ ] Critical business flow verified.
- [ ] Logs inspected.
- [ ] Metrics/alerts inspected.
- [ ] Data integrity verified.
