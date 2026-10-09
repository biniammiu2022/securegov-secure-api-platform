# Deployment Readiness Checklist

This is a planning checklist, not a compliance certification. Tailor it with the system owner before any deployment.

## Application security
- [ ] Validate OIDC issuer, token signature, expiry, and configured audience.
- [ ] Enforce least privilege and deny-by-default authorization.
- [ ] Validate request bodies, query parameters, content types, and pagination.
- [ ] Return safe errors without stack traces, tokens, or secrets.
- [ ] Test unauthenticated, unauthorized, malformed, and boundary requests.
- [ ] Review CORS, CSRF applicability, security headers, request limits, and rate limits.

## Data and secrets
- [ ] Use an approved secret manager; never commit credentials.
- [ ] Define data classification, minimization, retention, deletion, and backup procedures.
- [ ] Redact tokens and sensitive fields from logs.
- [ ] Restrict and audit access to databases, logs, and backups.

## Operations
- [ ] Centralize security logs, metrics, and alerts.
- [ ] Define incident response, escalation, and reporting procedures.
- [ ] Patch runtime, container images, and dependencies.
- [ ] Scan dependencies/images and protect CI/CD credentials and artifacts.
- [ ] Test backups and recovery; define health checks and availability targets.

## Government / regulated environment
- [ ] Obtain required agency authorization and accreditation before production use.
- [ ] Use agency-approved identity, hosting, encryption, monitoring, and key-management services.
- [ ] Complete privacy, accessibility, records-management, and applicable compliance reviews.
- [ ] Map controls to the target agency's framework and retain evidence.
- [ ] Confirm data residency, retention, and incident-reporting obligations.

Do not use this portfolio project for real government data until the responsible authority approves the system and all environment-specific requirements are met.
