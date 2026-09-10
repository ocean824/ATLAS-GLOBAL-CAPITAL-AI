# ATLAS One-Shot Delivery Waves

This is the execution decomposition for `MASTER_BUILD_PLAN_V1_V3.md`. The objective is one continuous program with release gates, not stop/restart rewrites.

## Wave 0 — Program bootstrap
Repository conventions, package manager/monorepo, CI/CD, local dev, environment config, schema tooling, test harness, observability, secrets, feature flags, architecture decision workflow, requirement IDs, CodeSpring corpus/index integration.

## Wave 1 — Identity / tenancy / trust primitives
Auth, organizations, memberships, RBAC/ABAC, audit, notifications, privacy controls, billing/entitlement skeleton, admin support-access controls.

## Wave 2 — Canonical capital domain
Company Truth, founders, raises, investor/fund/person/mandate, sources/evidence/claims, investment events, relationships, offers/terms, compliance assessments, event model.

## Wave 3 — Intelligence ingestion
Source adapters, raw/normalized/claim layers, entity resolution, confidence/freshness, queues, admin review, correction system, source monitoring.

## Wave 4 — Core intelligence engines
Match Engine, Capital Router, Raise Architect, evidence explanations, scoring versions, golden datasets/tests, model gateway/RAG.

## Wave 5 — Founder operating system
Founder onboarding, Command Center, Capital Map, matches, investor detail, router, scenario builder, Company Truth editor.

## Wave 6 — Raise execution
CRM, outreach drafts/approvals/provider adapters, relationship paths, meetings, next-best actions, notifications, analytics.

## Wave 7 — Diligence / offers / rules
Data room, grants, authorized RAG, diligence requests, offer normalization/comparison, cross-border rules framework, jurisdiction flags.

## Gate A — V1 Gauntlet / Founder Release
Full V1 acceptance/security/performance/accessibility/recovery validation. V2/V3 primitives may exist behind flags but do not block V1 release unless they compromise shared foundations.

## Wave 8 — Investor operating system
Investor verification, organizations/funds/mandates, deal flow, bidirectional matching, investor CRM/team collaboration, founder permission controls.

## Wave 9 — Intelligence network
Outcome learning, advanced graph, market intelligence, raise readiness, advanced syndicate/round optimization, ranking evaluation framework.

## Wave 10 — Enterprise + developer platform
SSO/custom roles, enterprise policies, API/service accounts/OAuth, webhooks, developer portal, integration marketplace, licensed-data entitlements.

## Wave 11 — Network collaboration + mobile
Messaging, scheduling, shared diligence, introduction requests, reputation/verification, mobile/PWA capabilities.

## Gate B — V2 Gauntlet / Network Release
Two-sided security/privacy, ranking bias/regression, API/connector, enterprise, abuse, and scale validation.

## Wave 12 — Marketplace primitives
Verified listings, visibility/disclosure controls, structured interest, competitive offers, investor rooms, marketplace search/discovery, anti-spam/anti-gaming.

## Wave 13 — Syndication / allocation / closing room
Lead/follow workflow, allocation scenarios, commitments, conditions, signatures/docs checklist, closing status, immutable audit package.

## Wave 14 — Transaction policy + provider adapters
KYC/KYB/accreditation/sanctions/FDI review adapters, policy engine, payment/escrow/custody/e-sign/cap-table adapters, provider state machines, reconciliation.

## Wave 15 — On-chain optional infrastructure
Credential/attestation interfaces, consent/document hashes, settlement adapter, governance/transfer-control abstractions. Activate only where product value and configured legal/provider support justify it.

## Wave 16 — Marketplace economics + analytics
Jurisdiction-aware fee/success economics, enterprise transaction products, network analytics, transaction reporting, ranking-commercial separation tests.

## Gate C — V3 Gauntlet / Marketplace Release
Transaction authorization, eligibility, sanctions/KYC provider failures, reconciliation, double-submit/idempotency, financial ledger correctness, auditability, marketplace abuse, ranking integrity, incident/recovery exercises, jurisdiction configuration validation.

## Dependency Rule

Traycer may parallelize waves internally and overlap downstream foundation work, but no work package may depend on an undefined upstream contract. Interfaces may be stubbed behind approved contracts to enable parallel CodeSpring execution.

## Definition of Program Complete

Program completion means all three gates are satisfied, V1/V2/V3 capabilities are represented in the same production architecture, shared primitives are not duplicated per version, and inactive jurisdiction/provider-dependent features can be enabled through configuration rather than a rewrite.
