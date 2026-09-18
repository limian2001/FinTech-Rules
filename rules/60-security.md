# Security Rules

## Secrets

Never commit:

- passwords;
- API keys;
- private keys;
- access tokens;
- production credentials.

Use environment variables or a proper secret-management system.

## Sensitive data

Minimize collection and retention of:

- PII;
- credentials;
- financial account information;
- authentication data.

## Logging

Never log secrets.

Avoid unnecessary logging of sensitive financial or personal data.

## Authentication

Authentication and authorization are separate concerns.

Always verify authorization for protected financial operations.

## Input security

Treat all external input as untrusted.

Validate types, sizes, formats, and allowed values.

## Dependencies

Keep dependencies updated and review security advisories.

## Least privilege

Services and users should have only the permissions required for their tasks.

## Production safety

Do not use development credentials or unsafe debug settings in production.

## Destructive operations

Require explicit safeguards for irreversible or destructive operations.
