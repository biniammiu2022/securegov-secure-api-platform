# SecureGov Threat Model

This document tracks design risks for the planned SecureGov REST API. It is not evidence that controls are implemented.

## Assets
- API records and personal data
- Identities, roles, tokens, signing keys
- Database credentials and application secrets
- Audit events and operational logs

## Threats and planned mitigations
| Threat | Planned mitigation and verification |
|---|---|
| Broken access control | Deny by default, ownership checks, negative authorization tests |
| Invalid or forged token | Validate signature, issuer, expiry, and configured audience; test invalid tokens |
| Privilege escalation | Explicit role mapping and role-based endpoint tests |
| Malformed input or injection | Server-side validation, parameterized persistence, boundary tests |
| Sensitive data in logs | Redaction, minimal audit data, safe error responses, log-content tests |
| Secret leakage | Secret manager, placeholder-only examples, secret scanning |
| Vulnerable dependencies | Automated dependency scanning and timely updates |
| Missing audit trail | Structured security events, access controls, retention policy |
| Resource exhaustion | Request limits, pagination caps, timeouts, rate limiting as deployment requirements |
| Misconfiguration | Secure defaults and environment-specific configuration review |

## Trust boundaries
1. External client to API.
2. API to OIDC identity provider.
3. API to PostgreSQL.
4. Runtime to logging and CI/CD systems.

## Assumptions and limits
Production requires TLS, approved identity, managed secrets, protected centralized logs, backup/recovery, incident response, and environment-specific operational controls. Formal government authorization/accreditation and compliance review are outside the scope of this portfolio project.

## Verification
Link each implemented mitigation to automated tests, configuration review, or operational evidence. Documentation alone does not make a control complete.
