# FinTech Rules

These rules apply to financial data, balances, trades, payments, orders, settlements, accounting values, fees, positions, and other financial state.

## 1. Monetary precision

Never use floating point numbers for monetary calculations.

Use Decimal.

Currency, scale, precision, and rounding behavior must be explicit.

Do not rely on implicit binary floating-point conversion.

## 2. Transaction identity

Every financial transaction must have:

- unique transaction ID;
- timestamp;
- source;
- status;
- audit information.

Where appropriate, also include:

- currency;
- amount;
- account/entity;
- correlation ID;
- idempotency key;
- version;
- business date.

## 3. Idempotency

Financial operations must be idempotent.

Retries must not create duplicate financial effects.

Idempotency keys must be persisted or otherwise enforced at the correct consistency boundary.

## 4. Failure handling

Never silently discard failed transactions.

Every failure must be:

- recorded;
- observable;
- traceable;
- recoverable or explicitly terminal.

Partial failure must be represented explicitly.

## 5. External APIs

Every external API call must have:

- timeout;
- retry policy where retry is safe;
- error handling;
- structured logging.

Retries must respect operation semantics. Never blindly retry a non-idempotent financial operation.

## 6. Auditability

All financial state changes must be auditable.

The system should make it possible to determine:

- what changed;
- when it changed;
- why it changed;
- which operation caused it;
- which actor/system caused it;
- previous and resulting state where appropriate.

Audit records should not be silently overwritten.

## 7. State transitions

Financial state transitions must be explicit.

Invalid transitions must be rejected.

For example:

pending -> completed

is different from:

pending -> failed

and neither should be represented as an arbitrary boolean flag.

## 8. Rounding

Rounding rules must be explicit.

Tests must cover:

- exact values;
- boundary values;
- rounding boundaries;
- currency-specific precision;
- repeated calculations where cumulative rounding matters.

## 9. Reconciliation

Where internal state represents external financial state, provide a reconciliation mechanism.

Reconciliation should identify:

- missing records;
- duplicate records;
- amount differences;
- status differences;
- timing differences.

## 10. Ledger/state integrity

Prefer immutable financial events or append-only records where appropriate.

Do not mutate historical financial facts merely to make current balances look correct.

## 11. Database integrity

Financial records should use:

- appropriate unique constraints;
- foreign keys where appropriate;
- transaction boundaries;
- optimistic/pessimistic locking when required by the consistency model.

## 12. Testing

Financial calculations must test:

- normal values;
- zero;
- negative values where valid;
- maximum/minimum values;
- precision boundaries;
- rounding;
- duplicate requests;
- retries;
- timeout/failure;
- partial failure;
- reconciliation mismatches.

## 13. No silent correction

Never silently alter financial data to compensate for an upstream or calculation error.

Create an explicit correction/reversal/adjustment flow.

## 14. Traceability

Financial operations should be traceable end-to-end using correlation/request identifiers.

## 15. Business date vs system time

Do not assume system timestamp and business date are interchangeable.

Financial systems must explicitly model business dates where relevant.
