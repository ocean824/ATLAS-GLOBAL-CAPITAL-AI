# ATLAS Context Index — XYRA / CodeSpring

## Purpose

ATLAS may accumulate hundreds of Markdown planning, architecture, research, review, and implementation files. This index prevents context collapse by telling agents what is authoritative and what to load for a scoped task.

## Governing Set — Always Resolve First

| ID | Document | Authority | Purpose |
|---|---|---|---|
| GOV-001 | `BUILD_CONTRACT.md` | LOCKED after Ø approval | non-negotiable build rules |
| GOV-002 | `docs/PRD.md` | governing | product requirements |
| GOV-003 | `docs/ARCHITECTURE.md` | governing | system architecture |
| GOV-004 | `docs/DATA_MODEL.md` | governing | canonical domain model |
| GOV-005 | `docs/API_CONTRACTS.md` | governing | service/API semantics |
| GOV-006 | `docs/MATCH_ENGINE_SPEC.md` | governing | matching/router logic |
| GOV-007 | `SECURITY.md` | governing | security policy |
| GOV-008 | `docs/THREAT_MODEL.md` | governing | threat assumptions/controls |
| GOV-009 | `AGENTS.md` | governing process | cross-agent XYRA operating contract |

## Persistent Agent Files

- `MANUS.md` — product/specification orchestration role.
- `TRAYCER.md` — planning/decomposition/orchestration role.
- `CODESPRING.md` — implementation and Gauntlet execution role.
- `PROJECT_MEMORY.md` — durable decisions/current state.
- `OPEN_DECISIONS.md` — unresolved material decisions.

## Corpus Layout

Recommended when CodeSpring files are added:

```text
codespring/
  00-governance/
  10-product/
  20-architecture/
  30-data/
  40-api/
  50-security/
  60-frontend/
  70-backend/
  80-ai-intelligence/
  90-infrastructure/
  100-testing-gauntlet/
  work-packages/
  evidence/
  archive/
```

The exact names can follow the CodeSpring generator, but the semantic separation must remain.

## Document Metadata

Recommended frontmatter:

```yaml
id: CS-ATLAS-0001
title: Example
status: PROPOSED
authority: supporting
domain: matching
depends_on: [GOV-002, GOV-006]
supersedes: []
applies_to: [apps/api, packages/matching]
last_updated: 2026-09-10
```

## Context Manifest

Every Traycer/CodeSpring work package should declare:

```yaml
context_manifest:
  governing:
    - BUILD_CONTRACT.md
    - docs/PRD.md
  task_specific:
    - docs/MATCH_ENGINE_SPEC.md
    - codespring/80-ai-intelligence/CS-ATLAS-0042.md
  decisions:
    - docs/adr/ADR-0007.md
  acceptance:
    - issue:#123
```

Agents should not recursively load the entire `codespring/` tree unless explicitly performing corpus-wide audit/index work.

## Status Semantics

- `LOCKED` — cannot be changed without explicit authorized decision.
- `OPEN` — unresolved; implementation must not invent the answer when material.
- `PROPOSED` — candidate direction, not authoritative.
- `APPROVED` — active authoritative decision at its declared level.
- `SUPERSEDED` — historical; retained for traceability but not active truth.

## Traceability

Requirements should receive stable IDs (`ATLAS-REQ-*`). Work packages reference requirement IDs; tests/evidence reference both work package and requirement IDs. This enables:

`Requirement → Plan → Code/PR → Test → Evidence → Release`.

## Context Budget Principle

Hundreds of Markdown files are acceptable. Hundreds of Markdown files loaded into every agent turn are not. Index aggressively, retrieve selectively, summarize only for navigation, and always preserve links to canonical source documents.
