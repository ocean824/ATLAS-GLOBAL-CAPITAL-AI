# ATLAS Threat Model

## Crown Jewels
Confidential decks/data rooms; cap tables/financials; founder and investor identities/contact graph; private communications; offers/terms; credentials/tokens; proprietary investor graph/outcome data; ranking algorithms; audit logs.

## Trust Boundaries
Browser/mobile ↔ API; API ↔ DB/object store; API ↔ AI providers; ingestion ↔ public/paid sources; connectors ↔ email/calendar/CRM; workers ↔ queues; admin ↔ production; future blockchain/payment providers ↔ transaction services.

## Priority Threats
### Cross-Tenant Data Access
Mitigation: explicit tenant scope, server-side authorization, DB policies where practical, negative authorization tests, opaque IDs alone never treated as authorization.
### IDOR
Test all company, raise, match, document, offer, interaction, and admin endpoints.
### Data-Room Leakage
Short-lived signed URLs, ACL inheritance into retrieval indexes, revocation, download policy, access logs.
### Prompt Injection
Untrusted content cannot alter tool permissions/system rules. Separate instructions from retrieved data, structured tool policies, confirmation gates, output validation.
### AI Hallucinated Investor Intelligence
Evidence-constrained generation, citations/provenance, confidence, deterministic feature inputs, freshness indicators.
### Ranking Manipulation
Separate sponsored inventory from organic scoring; signed/versioned scoring configs; anomaly detection; audit administrative changes.
### Investor/Founder Impersonation
Verification tiers, domain/email proof where appropriate, account security, suspicious login controls.
### Scraping/Enumeration
Rate limits, abuse detection, response minimization, access-tier controls, monitoring.
### Malicious Upload
Type/size limits, quarantine, malware scanning, sandboxed parsing, no direct execution.
### SSRF
Allowlist/deny private networks, resolve/revalidate redirects/DNS, egress controls.
### OAuth/Connector Token Theft
Encrypted token vault, least scopes, rotation/revocation, never expose tokens to client/model context unnecessarily.
### Outreach Abuse
Send limits, consent/opt-out handling, manual approvals, suppression lists, anti-spam controls.
### Insider/Admin Abuse
Least privilege, privileged audit trail, separation of duties as scale requires, break-glass logging.
### Supply Chain
Lockfiles, dependency scanning, provenance, minimal CI permissions, protected release pipeline.

## Future Transaction Layer Threats
If ATLAS handles settlement/tokenized assets: wallet/key compromise, transaction replay, smart-contract bugs, chain reorgs, oracle failure, sanctions/eligibility bypass, irreversible wrong-address transfer. These require a separate transaction threat model and independent security review before activation.