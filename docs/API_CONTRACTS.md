# ATLAS V1 API Contracts

Base: `/v1`. JSON over HTTPS initially. Generate OpenAPI from executable schemas when implementation begins.

## Global Rules

- authenticated tenant context required except explicitly public endpoints;
- UUID/ULID identifiers;
- ISO-8601 timestamps;
- cursor pagination;
- idempotency keys for consequential POST mutations;
- optimistic concurrency/version fields for mutable strategic records;
- machine-readable error envelope;
- audit event for consequential mutations;
- request IDs/correlation IDs;
- explicit authorization checks at service boundary.

## Error Envelope

```json
{"error":{"code":"ATLAS_CODE","message":"Human-readable message","request_id":"...","details":{}}}
```

## Core Endpoints

### Companies / Raises
- `POST /companies`
- `GET /companies/{id}`
- `PATCH /companies/{id}`
- `POST /companies/{id}/raises`
- `GET /raises/{id}`
- `PATCH /raises/{id}`
- `POST /raises/{id}/scenarios`

### Investors / Intelligence
- `GET /investors`
- `GET /investors/{id}`
- `GET /funds/{id}`
- `GET /investors/{id}/evidence`
- `GET /investors/{id}/activity`

### Matching / Router
- `POST /raises/{id}/matches:compute`
- `GET /raises/{id}/matches`
- `GET /matches/{id}`
- `POST /raises/{id}/route:compute`
- `GET /raises/{id}/route`

Match response includes component scores, confidence, evidence refs, model/scoring version, flags, and explanation.

### Relationships
- `GET /investors/{id}/paths`
- `POST /relationships/import` (explicit user action)

### CRM / Outreach
- `POST /raises/{id}/pipeline`
- `PATCH /pipeline/{id}`
- `POST /pipeline/{id}/interactions`
- `POST /outreach/drafts`
- `POST /outreach/{id}/approve`
- `POST /outreach/{id}/send` only when a configured provider and user authorization permit it.

Generated draft != authorization to send.

### Data Rooms
- `POST /data-rooms`
- `POST /data-rooms/{id}/documents`
- `POST /data-rooms/{id}/grants`
- `DELETE /data-rooms/{id}/grants/{grantId}`
- `GET /data-rooms/{id}/audit`

### Offers
- `POST /raises/{id}/offers`
- `PATCH /offers/{id}`
- `POST /offers:compare`

### Rules / Compliance
- `POST /compliance/assessments`
- `GET /compliance/assessments/{id}`
- `GET /jurisdictions/{code}/rules`

### Audit
- `GET /audit-events` restricted to authorized organization roles.

## Consequential Action State Machine

Actions such as outbound email, document disclosure, investor invitation, offer acceptance, or transaction initiation use:

`DRAFT → REVIEW_REQUIRED → APPROVED → EXECUTING → SUCCEEDED | FAILED | REVOKED`

No model output can skip `REVIEW_REQUIRED/APPROVED` when policy marks the action consequential.

## Webhooks

Signed webhooks with replay protection for:
- CRM/outreach delivery events;
- data-room access events;
- provider ingestion completion;
- billing events;
- future transaction events.

## Versioning

Breaking API changes require a new version or explicit migration. Scoring/model versions are independent of API version and must be returned with computed intelligence.
