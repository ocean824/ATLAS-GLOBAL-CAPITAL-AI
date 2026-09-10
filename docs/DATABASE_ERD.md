# ATLAS Database ERD — Conceptual V1

```mermaid
erDiagram
  ORGANIZATION ||--o{ MEMBERSHIP : has
  USER ||--o{ MEMBERSHIP : joins
  ORGANIZATION ||--o{ COMPANY : owns
  COMPANY ||--o{ FOUNDER : has
  COMPANY ||--o{ RAISE : conducts
  RAISE ||--o{ MATCH : produces
  INVESTOR_ENTITY ||--o{ FUND : manages
  INVESTOR_ENTITY ||--o{ INVESTOR_PERSON : employs
  FUND ||--o{ INVESTMENT_MANDATE : has
  INVESTOR_ENTITY ||--o{ INVESTMENT_EVENT : makes
  COMPANY ||--o{ INVESTMENT_EVENT : receives
  MATCH }o--|| INVESTOR_ENTITY : targets
  MATCH ||--o{ MATCH_EVIDENCE : explains
  SOURCE ||--o{ EVIDENCE : supports
  EVIDENCE ||--o{ MATCH_EVIDENCE : referenced_by
  RAISE ||--o{ PIPELINE_RECORD : tracks
  INVESTOR_ENTITY ||--o{ PIPELINE_RECORD : subject
  PIPELINE_RECORD ||--o{ INTERACTION : contains
  PIPELINE_RECORD ||--o{ MEETING : contains
  RAISE ||--o{ OFFER : receives
  OFFER ||--o{ TERM : contains
  COMPANY ||--o{ DATA_ROOM : owns
  DATA_ROOM ||--o{ DOCUMENT : contains
  DATA_ROOM ||--o{ PERMISSION_GRANT : grants
  DATA_ROOM ||--o{ DILIGENCE_REQUEST : supports
  RAISE ||--o{ COMPLIANCE_ASSESSMENT : assessed
  JURISDICTION_RULE ||--o{ COMPLIANCE_ASSESSMENT : informs
  ORGANIZATION ||--o{ AUDIT_EVENT : generates
  USER ||--o{ AUDIT_EVENT : actor
  ORGANIZATION ||--o{ SUBSCRIPTION : billed
  SUBSCRIPTION ||--o{ ENTITLEMENT : enables
```

## Storage Rules

- `organization_id` tenant key appears on all tenant-owned records.
- Cross-tenant global intelligence entities are separate from private tenant records.
- Confidential founder data is never copied into global investor intelligence tables.
- Claims/evidence are append/supersede oriented; provenance is not destructively overwritten.
- Monetary values store currency + integer minor units/decimal-safe numeric values.
- Match results are immutable/versioned snapshots; recomputation creates a new version.
- Audit events are append-only at application level.
- Documents store metadata in Postgres and bytes in object storage.
- Embeddings reference source/document chunks and authorization scope; retrieval enforces permissions before generation.

## Index Priorities

- tenant + resource IDs
- raise pipeline state
- investor geography/stage/sector/check-range filters
- evidence/source freshness
- relationship graph endpoints
- vector semantic indexes for approved textual intelligence
- audit actor/resource/timestamp

Dedicated graph infrastructure is deferred until measured query complexity/latency justifies it.
