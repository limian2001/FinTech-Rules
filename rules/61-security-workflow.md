# Secure Development Workflow

Security is part of the development lifecycle, not a final checklist.

## 1. Threat awareness

For every material feature consider:

- who can invoke it;
- what they can control;
- what data they can access;
- what financial effect they can cause;
- what happens if the input is malicious;
- what happens if a dependency is compromised.

## 2. Trust boundaries

Identify boundaries between:

- user and application;
- application and database;
- application and external APIs;
- services;
- development/staging/production.

Validate data at every trust boundary.

## 3. Authentication

Verify identity before protected operations.

Do not treat possession of an identifier as authentication.

## 4. Authorization

Authentication does not imply authorization.

Check permissions for every protected financial or administrative operation.

## 5. Input validation

Validate:

- type;
- length;
- range;
- format;
- allowed values;
- ownership;
- business constraints.

Never trust client-side validation.

## 6. Secrets

Secrets must come from secure configuration or secret management.

Never:

- hard-code secrets;
- commit secrets;
- print secrets;
- place secrets in URLs;
- expose secrets in exceptions.

If a secret is accidentally committed, treat it as compromised and rotate it.

## 7. Sensitive data

Minimize sensitive data collection.

Use appropriate:

- encryption;
- access controls;
- retention;
- masking;
- deletion procedures.

## 8. Logging

Logs should support investigation without becoming a data-leak channel.

Do not log:

- passwords;
- API keys;
- tokens;
- private keys;
- unnecessary full payment/account information.

## 9. Dependency security

Before introducing dependencies consider:

- source;
- maintenance;
- known vulnerabilities;
- license;
- transitive dependencies.

Use automated dependency/security scanning where practical.

## 10. Database security

Use parameterized queries.

Do not construct SQL using untrusted string interpolation.

Apply least-privilege database credentials.

## 11. Financial safety

For operations with financial consequences:

- require explicit authorization;
- enforce idempotency;
- record audit information;
- validate amounts and currency;
- protect against replay;
- make state transitions explicit.

## 12. Deployment safety

Before production deployment verify:

- correct environment;
- correct credentials;
- correct database;
- secure configuration;
- migration safety;
- rollback/recovery plan.

## 13. Security incident response

When a security issue is discovered:

1. contain;
2. preserve evidence;
3. assess impact;
4. rotate compromised credentials;
5. patch;
6. verify remediation;
7. document the incident;
8. add preventive controls where appropriate.
