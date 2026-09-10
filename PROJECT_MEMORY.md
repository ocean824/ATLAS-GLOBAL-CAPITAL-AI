# ATLAS Project Memory

## Current Canonical State

- Product: ATLAS — Global Capital AI.
- Thesis: AI-native global capital operating system; capital without borders.
- Progression: Fundraising OS → Intelligence Network → Capital Marketplace → Transaction Infrastructure → Global Private-Market Network.
- **V1, V2, and V3 are one unified engineering program.** They are capability/release gates, not separate rewrites. Shared architecture must be designed for the V3 end-state from day one and activated progressively through feature flags, entitlements, jurisdiction/provider configuration, and Gauntlet gates.
- Master execution specification: `docs/MASTER_BUILD_PLAN_V1_V3.md`.
- Delivery decomposition: `docs/DELIVERY_WAVES.md`.
- Stable requirements: `docs/REQUIREMENT_REGISTRY_V1_V3.md`.
- Development process: XYRA pipeline `Ø → Manus → GitHub → Traycer → CodeSpring → Gauntlet → Release`.
- GitHub is durable source of truth.
- V1 proves global investor discovery, explainable matching, capital routing, outreach/CRM, raise modeling, and diligence/data room.
- V2 activates the two-sided investor intelligence network, proprietary outcome intelligence, enterprise/developer platform, and deeper collaboration/diligence.
- V3 activates verified marketplace, competitive structured interest/offers, syndication/closing workflows, and configurable transaction infrastructure where jurisdiction/provider requirements permit.
- Blockchain is optional infrastructure where useful; architecture may support it before activation, but ATLAS does not assume blockchain removes securities, tax, AML/KYC, sanctions, licensing, or other obligations.
- Founder sovereignty, global neutrality, ranking integrity, provenance, human authorization, tenant isolation, and compliance-ready architecture are non-negotiable.

## Durable Technical Decisions

- TypeScript-first; Python for justified ML/data workloads.
- PostgreSQL canonical transactional store.
- Relational graph representation first; dedicated graph DB only when measured need justifies it.
- External providers behind adapters.
- Deterministic scoring/rules outside opaque LLM prompts.
- Versioned match snapshots and scoring models.
- Unified identity model supports founder and investor participation rather than mutually exclusive account types.
- Audit, evidence, entitlements, feature flags, events, rules, provider adapters, and authorization are shared primitives across V1–V3.
- Large CodeSpring/XYRA Markdown corpus is selectively retrieved through context manifests/indexes rather than bulk-loaded.

Update this file when an approved decision materially changes the durable current state. Do not use it as a substitute for full governing specifications.
