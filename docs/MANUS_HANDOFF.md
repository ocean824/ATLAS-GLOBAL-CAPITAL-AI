# Manus / Coding-Agent Handoff

## Assignment
Implement ATLAS from this repository's canonical specification. Do not reduce it to a generic investor directory or chatbot.

Read in order:
1. `README.md`
2. `docs/PRD.md`
3. `docs/BUILD_CONTRACT.md`
4. `docs/ARCHITECTURE.md`
5. `docs/DATA_MODEL.md`
6. `SECURITY.md`
7. `docs/THREAT_MODEL.md`
8. `docs/MONETIZATION_AND_GOVERNANCE.md`
9. `docs/ROADMAP.md`

## Immediate Goal
Produce a production-oriented implementation plan and then implement Phase 0 through the V1 proof checkpoint without silently changing product intent.

## Required Planning Artifacts Before Major Build
- repository/codebase assessment
- dependency/stack proposal with reasons
- implementation plan mapped to PRD requirements
- initial schema/migrations
- API contracts
- authorization matrix
- threat-model mapping
- test plan
- environment/secrets matrix
- ADRs for material architecture choices

## Non-Negotiables
Global by default; evidence-backed investor intelligence; explainable scores; no pay-to-rank; strict tenant isolation; deterministic financial math; human approval for consequential outbound actions; model/provider abstraction; adapter boundaries; compliance-ready feature flags rather than deleting intended monetization; no hard-coded secrets.

## Recommended V1 Stack
Use current stable versions after compatibility verification. Prefer Next.js + TypeScript, PostgreSQL, pgvector, typed validation, background jobs/queues, object storage, and provider abstractions. Do not introduce a dedicated graph DB or microservice sprawl without measured need.

## UI Direction
ATLAS should feel like an institutional global-capital command center rather than a generic SaaS dashboard: dark executive visual language, dense-but-readable intelligence, global map/graph motifs, premium typography, strong hierarchy, fast command/search interactions, and explainable evidence drawers. Accessibility and responsive behavior remain required.

## Seed/Demo
Use synthetic demo companies/investors unless importing legitimately licensed/public data. Never seed private Lossless company information merely because it exists in other repositories.

## Agent Behavior
When requirements conflict or implementation reveals a material issue, open/document a decision instead of silently simplifying. Preserve the founder's intended monetization and global-capital architecture unless technically impossible or prohibited, and separate buildability from launch/compliance requirements.

## Completion Standard
A demo is insufficient. The implementation must have real persistence, authorization, migrations, tests, error states, observability, security controls, and documented deployment. Mock providers may be used behind production-shaped adapters until credentials/data contracts are supplied.