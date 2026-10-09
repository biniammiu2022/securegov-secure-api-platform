# SecureGov — Secure API Platform

> A portfolio project demonstrating secure API design for government-style services, with a focus on identity, authorization, auditability, validation, and automated security checks.

**Status:** Planning / initial implementation. Features listed as planned are not production controls until implemented and tested.

## Goals

- Authenticate API clients with OAuth 2.0 / OpenID Connect (OIDC) using Keycloak or an equivalent identity provider.
- Enforce role-based access control (RBAC) with Spring Security.
- Validate requests and return consistent, safe error responses.
- Record security-relevant audit events without leaking secrets or sensitive payloads.
- Document endpoints with OpenAPI and provide repeatable local development.
- Run automated tests and security checks in CI.

## Intended technology stack

- Java 21 and Spring Boot
- Spring Security with OAuth 2.0 Resource Server / JWT validation
- Keycloak (OIDC identity provider)
- PostgreSQL and Flyway migrations
- OpenAPI / Swagger UI
- Docker Compose and GitHub Actions

The stack is the current plan and may evolve as implementation proceeds.

## Planned capabilities

- Protected REST endpoints and JWT validation (issuer, signature, audience where configured, and expiry).
- Least-privilege roles and endpoint-level authorization.
- Input validation, pagination limits, and consistent error handling.
- Audit events for security-relevant actions.
- Unit and integration tests for authentication, authorization, validation, and error cases.
- CI checks, dependency/security scanning, and documented local setup.
- Threat model, architecture notes, API examples, and a deployment readiness checklist.

## Getting started

The application and deployment configuration are still being built. As implementation lands, this section will document the exact prerequisites and commands. Do not treat the repository as deployable or production-ready yet.

## Security and threat model

Primary risks to address include broken access control, forged or misconfigured tokens, injection and malformed input, sensitive-data exposure in logs, insecure defaults, vulnerable dependencies, and insufficient auditability.

Planned mitigations include OIDC/JWT validation, deny-by-default authorization, server-side validation, safe error responses, secret management through environment/configuration, dependency scanning, and security-focused tests. Each mitigation must be implemented and verified before it is described as active.

See [docs/threat-model.md](docs/threat-model.md) and [docs/deployment-checklist.md](docs/deployment-checklist.md) as they are added.

## Government deployment caveat

This is an educational portfolio project, not a certified government system. Real deployment would require agency-specific authorization and accreditation, an approved identity provider, documented data classification and retention, centralized monitoring, incident response, secure operations, accessibility and privacy review, and compliance assessments appropriate to the jurisdiction and system. This README does not claim compliance with FedRAMP, FISMA, NIST controls, or any other framework.

## Project tracking

Use the [SecureGov project board](https://github.com/users/biniammiu2022/projects/3) to track user stories through **Backlog → Ready → In Progress → In Review → Done**. The issues should represent planned work; issue creation alone does not mean a feature is implemented.

## Contributing

1. Pick a scoped issue and clarify acceptance criteria.
2. Create a feature branch.
3. Add tests with the implementation.
4. Run the documented checks before opening a pull request.
5. Never commit credentials, real personal data, access tokens, or production configuration.

## License

No license has been selected yet. Until one is added, assume standard copyright applies.
