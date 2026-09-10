# ATLAS V1–V3 Requirement Registry

Every CodeSpring/Traycer work package must reference one or more stable IDs. Detailed acceptance criteria live in the master plan, PRD, domain specs, and scoped work packages.

## Foundation
- `ATLAS-REQ-FND-001` Unified multi-tenant identity/org model supports founder and investor roles.
- `ATLAS-REQ-FND-002` RBAC/ABAC enforced at service/resource boundary.
- `ATLAS-REQ-FND-003` Consequential mutations emit append-only audit events.
- `ATLAS-REQ-FND-004` External vendors/models are adapter-based and replaceable.
- `ATLAS-REQ-FND-005` Feature flags/entitlements/jurisdiction config support progressive activation through V3.
- `ATLAS-REQ-FND-006` Evidence/provenance is a shared platform primitive.
- `ATLAS-REQ-FND-007` CI/CD, observability, backup/recovery, secret management and environment isolation are production-grade.

## V1
- `ATLAS-REQ-V1-001` Founder can create/version canonical Company Truth.
- `ATLAS-REQ-V1-002` Founder can configure a structured global raise objective.
- `ATLAS-REQ-V1-003` System maintains a provenance/freshness-aware Global Investor Graph.
- `ATLAS-REQ-V1-004` Match Engine produces explainable eligibility/fit/confidence/priority/strategic-value results.
- `ATLAS-REQ-V1-005` Capital Router produces multi-region, multi-archetype global capital strategy.
- `ATLAS-REQ-V1-006` Raise Architect models dilution/ownership/runway scenarios deterministically.
- `ATLAS-REQ-V1-007` Warm-Path Graph supports permissioned relationship analysis without making introductions mandatory.
- `ATLAS-REQ-V1-008` Pitch Intelligence preserves canonical facts and evidence.
- `ATLAS-REQ-V1-009` Outreach requires explicit authorization for consequential sends.
- `ATLAS-REQ-V1-010` CRM supports full raise state machine and interaction history.
- `ATLAS-REQ-V1-011` Meeting intelligence prepares and captures investor interactions.
- `ATLAS-REQ-V1-012` Data room provides permissioned/revocable/audited document access and authorized AI Q&A.
- `ATLAS-REQ-V1-013` Offer engine normalizes and compares economics/control/strategic terms without inventing missing terms.
- `ATLAS-REQ-V1-014` Cross-border rules engine surfaces versioned jurisdiction review states.
- `ATLAS-REQ-V1-015` Billing/entitlements cannot corrupt organic ranking.
- `ATLAS-REQ-V1-016` Founder and Trust/Admin UIs cover the complete V1 workflow.

## V2
- `ATLAS-REQ-V2-001` Verified investor organizations can configure funds/mandates/team roles.
- `ATLAS-REQ-V2-002` Investors receive permission-aware AI-ranked deal flow and internal pipeline/collaboration.
- `ATLAS-REQ-V2-003` Matching becomes bidirectional/mutual while preserving evidence/confidence.
- `ATLAS-REQ-V2-004` Outcome learning uses thresholded, versioned, bias-monitored signals.
- `ATLAS-REQ-V2-005` Relationship graph supports co-investment/syndication/introduction intelligence.
- `ATLAS-REQ-V2-006` Institutional diligence supports structured workstreams and exportable evidence-backed reports.
- `ATLAS-REQ-V2-007` Raise readiness identifies completeness/contradictions without presenting investment worthiness as fact.
- `ATLAS-REQ-V2-008` Advanced strategy models syndicates, concentration, follow-on and geographic mixes.
- `ATLAS-REQ-V2-009` Aggregate market intelligence enforces privacy/licensing thresholds.
- `ATLAS-REQ-V2-010` Enterprise supports SSO/custom roles/policies/connectors/audit requirements.
- `ATLAS-REQ-V2-011` Developer platform provides scoped APIs/webhooks/OAuth/service accounts/rate limits/usage controls.
- `ATLAS-REQ-V2-012` Integration marketplace uses permission-scoped revocable connectors.
- `ATLAS-REQ-V2-013` Messaging/collaboration includes anti-spam/abuse controls.
- `ATLAS-REQ-V2-014` Verification/reputation avoids opaque public social-credit scoring.
- `ATLAS-REQ-V2-015` Mobile supports monitoring/approval/communication workflows.

## V3
- `ATLAS-REQ-V3-001` Verified marketplace listings provide granular visibility/disclosure controls.
- `ATLAS-REQ-V3-002` Investors can submit structured interest without bypassing eligibility/permission gates.
- `ATLAS-REQ-V3-003` Competitive offer workflow separates organic discovery from paid promotion and resists gaming.
- `ATLAS-REQ-V3-004` Syndication supports lead/follow/allocation/commitment workflows.
- `ATLAS-REQ-V3-005` Closing room tracks conditions, approvals, documents, signatures and immutable audit evidence.
- `ATLAS-REQ-V3-006` Transaction policy engine evaluates identity/eligibility/KYC/KYB/sanctions/jurisdiction/provider state before actions.
- `ATLAS-REQ-V3-007` Transaction providers are replaceable adapters with explicit failure/reconciliation state machines.
- `ATLAS-REQ-V3-008` Optional stablecoin/fiat settlement preserves accounting/reconciliation and is activation-gated.
- `ATLAS-REQ-V3-009` Optional on-chain credentials/attestations/ownership proofs do not assume blockchain removes legal obligations.
- `ATLAS-REQ-V3-010` Secondary/liquidity architecture remains disabled until separately approved/configured, but core data/interfaces can support future extension.
- `ATLAS-REQ-V3-011` Marketplace monetization supports jurisdiction/provider configuration and never silently changes organic rank.
- `ATLAS-REQ-V3-012` V3 transaction/marketplace actions have human authorization, audit, idempotency and incident controls.

## Cross-version quality
- `ATLAS-REQ-QLT-001` WCAG/accessibility baseline for core workflows.
- `ATLAS-REQ-QLT-002` No critical/high unresolved security finding at production gate unless formally risk-accepted by authorized owner.
- `ATLAS-REQ-QLT-003` Core financial/scoring/policy logic has deterministic golden tests.
- `ATLAS-REQ-QLT-004` Prompt-injection cannot bypass authorization/data-room/tenant boundaries.
- `ATLAS-REQ-QLT-005` Ranking changes are versioned, evaluable and rollback-capable.
- `ATLAS-REQ-QLT-006` Data retention/export/delete controls operate across shared and versioned architecture.
