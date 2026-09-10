# ATLAS System Architecture

## Architectural Goals
Global, multi-tenant, evidence-first, explainable, secure, model-agnostic, adapter-driven, observable, and incrementally scalable.

## Monorepo Target
```text
/apps
  /web
  /admin
  /api
/packages
  /ui
  /domain
  /auth
  /db
  /ai
  /matching
  /capital-router
  /compliance
  /connectors
  /observability
/workers
  /ingestion
  /enrichment
  /notifications
  /document-processing
/docs
/infrastructure
```

## Services
### Identity/Tenant Service
Users, organizations, memberships, roles, sessions, entitlements.
### Company Service
Canonical founder/company/raise truth.
### Investor Intelligence Service
Investor/fund/person/mandate data plus provenance and temporal history.
### Ingestion Pipeline
Fetch → parse → normalize → deduplicate/entity-resolution → extract claims → validate → source → publish.
### Match Engine
Deterministic features plus bounded AI reasoning. Produces versioned component scores and explanations.
### Capital Router
Portfolio-style reasoning across the entire raise: investor archetypes, regions, coverage, sequencing, and next actions.
### Relationship Service
Permissioned people/entity edges and warm paths.
### CRM Service
Pipeline, interactions, meetings, next actions, campaigns.
### Document/Data Room Service
Object storage, metadata, ACL, secure delivery, document processing, retrieval authorization.
### Rules/Policy Service
Jurisdiction/provider/feature policy and review flags.
### Offer Service
Normalized offers/terms/scenario comparison.
### AI Gateway
Provider abstraction, model registry, prompt registry, structured outputs, budgets, caching, evaluation, safety boundaries, and telemetry.
### Audit Service
Append-oriented consequential-action audit stream.

## Storage
PostgreSQL is canonical. Use normalized tables for core entities, JSONB for evolving evidence/policy payloads, pgvector for embeddings, relational edge tables for graph V1, object storage for documents, Redis-compatible caching/queueing where necessary.

## Tenant Isolation
Every tenant-owned table includes organization scope. Authorization occurs in service/domain boundaries and should be reinforced by database policies where practical. Background jobs carry explicit tenant context. Never rely on client-supplied organization IDs without membership validation.

## Evidence Model
Claims about investors are not naked fields. Important intelligence should resolve to:
`Claim(value, subject, predicate, valid_from, valid_to, confidence, source_id, observed_at, extraction_method, reviewer_state)`.
Derived investor profiles are materialized from claims while retaining provenance.

## Matching Pipeline
1. Hard eligibility filters.
2. Feature calculation.
3. Component scoring.
4. Conflict/risk modifiers.
5. Evidence-confidence calculation.
6. Priority score.
7. LLM explanation constrained to structured feature/evidence payload.
8. Persist score version and evidence IDs.

The LLM must not invent score inputs.

## AI Gateway Contract
Every AI run records provider, model, prompt/template version, tool policy, structured schema, latency, token/cost telemetry where available, input/output hashes where safe, and evaluation metadata. Sensitive payload retention is configurable.

## Event Model
Representative events:
`company.updated`, `raise.updated`, `investor.claim.updated`, `match.recomputed`, `interaction.created`, `meeting.completed`, `document.shared`, `offer.created`, `rule.updated`, `subscription.changed`.
Consumers must be idempotent.

## Connector Pattern
Email, calendar, CRM, data providers, identity verification, payments, storage, blockchain, and future sources live behind typed adapters. Business logic must not import provider SDKs directly.

## Deployment
Start as modular monolith + independent workers to minimize premature distributed-systems complexity. Split services only where scaling, security isolation, deployment cadence, or reliability warrants it.

## Environments
`local → development → staging → production`. Separate credentials/data stores. No production secrets or real investor/founder confidential data in test fixtures.

## Reliability
Health/readiness endpoints, structured logs, traces, metrics, dead-letter handling, retries with backoff, idempotency, database backups, object-store versioning where supported, restore tests, and graceful degradation when AI/data providers fail.

## Data Freshness
Investor intelligence has freshness policies by field/source. Stale data reduces confidence rather than disappearing silently. High-value targets can trigger prioritized refresh jobs.

## Search
Hybrid structured + lexical + semantic retrieval. Natural-language queries compile into visible filters and semantic clauses. User can inspect/remove inferred constraints.

## Internationalization
Unicode-first, locale-aware dates/numbers/currencies, translatable UI, original-language source preservation, translated summaries separated from originals, timezone-aware meetings and deadlines.