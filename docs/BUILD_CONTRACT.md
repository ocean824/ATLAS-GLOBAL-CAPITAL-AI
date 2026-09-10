# ATLAS Build Contract

This document is authoritative for implementation agents unless superseded by an explicit founder-approved ADR/requirement change.

## Product Invariants
1. Global capital discovery is first-class; no U.S.-default ranking bias.
2. Founder priorities and ownership/control constraints are explicit inputs.
3. Organic ranking cannot be purchased.
4. Material investor intelligence is source/provenance aware.
5. Stated investor mandate and observed investor behavior remain distinguishable.
6. Match explanations cannot invent evidence.
7. Confidential data is tenant-scoped and permissioned.
8. AI cannot autonomously disclose confidential documents or commit a founder/investor to a transaction.
9. Cross-border uncertainty surfaces review requirements; it does not silently delete monetization/product architecture.
10. All consequential mutations are auditable.
11. Provider dependencies use adapters.
12. No secrets are committed.
13. V1 remains buildable; future blockchain/marketplace functionality must not force premature complexity into core V1.

## Engineering Rules
- Type-safe interfaces and validated boundary schemas.
- Database migrations are forward/reversible where practical and reviewed.
- Every tenant query is tested for isolation.
- Every external integration has timeout/retry/error behavior.
- AI outputs affecting persisted structured data must validate against schemas.
- Financial calculations use deterministic code, not LLM arithmetic.
- Compliance/rules decisions use versioned deterministic policy inputs; AI may explain but not invent rules.
- Authorization is server-side.
- Logs must not casually contain tokens, raw credentials, full sensitive documents, or unnecessary PII.
- Feature flags control unfinished/jurisdiction-limited capabilities.

## Definition of Done
A feature is not done because UI renders. It requires requirements satisfied, authorization, validation, error/empty/loading states, auditability where consequential, telemetry, automated tests at appropriate level, accessibility review, security review proportional to risk, docs, and successful CI.

## AI Development Attribution
AI-assisted implementation is permitted and expected. Product direction, acceptance, architecture ownership, and final responsibility remain with Ø / project ownership. Never fabricate authorship claims or remove third-party license/attribution obligations.

## Change Control
If implementation reveals a requirement defect, architecture defect, provider limitation, test defect, security conflict, or regulatory constraint: document it; classify it; propose options; preserve intended business capability where lawful/buildable; and escalate material product changes rather than silently rewriting scope.

## Branch Strategy
Recommended: `main` production-ready, `develop` integration, short-lived feature branches. If the existing workflow uses environment branches, preserve clear promotion gates and prohibit direct unreviewed production changes.

## Testing Minimum
Unit: scoring, financial math, policy evaluation, parsers.
Integration: DB, storage, provider adapters, queues.
E2E: onboarding→matching→save→outreach draft→CRM; data-room authorization; offer comparison.
Security: tenant isolation, IDOR, privilege escalation, signed URLs, injection, SSRF, prompt injection/exfiltration.
AI evals: groundedness, ranking explanation fidelity, extraction precision/recall, hallucination rate, multilingual behavior.

## Release Gate
No production release with known critical auth/tenant-isolation vulnerability, exposed secret, destructive migration without recovery, or materially ungrounded investor ranking behavior.