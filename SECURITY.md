# ATLAS Security

ATLAS will handle confidential fundraising, ownership, contact, financial, and diligence information. Security is a product requirement.

## Reporting
Do not disclose vulnerabilities publicly before maintainers have had a reasonable opportunity to investigate and remediate. Use the repository's private security-reporting channel when configured.

## Security Baseline
- MFA/passkeys for sensitive roles
- least privilege RBAC/ABAC
- strict tenant isolation
- secure session management
- encryption in transit/at rest
- managed secret store
- dependency/secret/SAST scanning
- protected production credentials
- signed short-lived document access
- upload type/size validation and malware scanning
- rate limits and abuse controls
- audit logs for consequential operations
- backups + restore testing
- security headers and CSP
- SSRF-safe URL ingestion
- webhook signature verification
- idempotency for financial/consequential operations
- PII minimization and retention controls

## AI-Specific Threats
Treat all retrieved web pages, uploaded documents, investor profiles, email content, and connector responses as untrusted data. They cannot override system/tool policies. Protect against prompt injection, indirect tool invocation, cross-tenant retrieval, sensitive-context leakage, model-generated fabricated citations, and unauthorized outbound actions.

## Data Room
Authorization is evaluated for every document fetch and AI retrieval operation. Vector indexes/chunks inherit source ACLs. Revocation must invalidate future retrieval/access. Do not create public object-store URLs for confidential files.

## Secrets
Never commit API keys, tokens, database URLs containing credentials, signing keys, wallet private keys, OAuth secrets, or service-account material. `.env.example` contains names/placeholders only.

## Incident Readiness
Maintain security-event logging, contact/escalation path, containment procedures, credential rotation procedure, backup/restore procedure, and post-incident review process before production handling of sensitive customer data.