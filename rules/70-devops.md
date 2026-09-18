# DevOps Rules

## Reproducibility

Builds and deployments should be reproducible.

## Configuration

Separate configuration from application code.

## Environments

Clearly distinguish:

- local;
- development;
- staging;
- production.

Never accidentally point local/test code at production resources.

## CI/CD

CI should run appropriate:

- formatting/linting;
- type checking;
- unit tests;
- integration tests;
- security checks.

## Containers

Containers should:

- use minimal base images where practical;
- avoid running as root where practical;
- pin important versions;
- avoid embedding secrets.

## Deployment

Prefer small, reversible deployments.

For database changes, consider backward compatibility and migration sequencing.

## Observability

Production services should provide:

- structured logs;
- health checks;
- metrics where appropriate;
- useful error visibility.

## Rollback

Every production deployment should have a realistic rollback or recovery strategy.
