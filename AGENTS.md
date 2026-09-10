# ATLAS Agent Operating Contract — XYRA Process

ATLAS is built under the XYRA delivery process. This file is the standing cross-agent entrypoint for Manus, Traycer, CodeSpring, Codex, Claude, and other coding/review agents.

## Canonical Pipeline

`Ø → Manus → GitHub → Traycer → CodeSpring → Gauntlet → Release`

GitHub is the durable source of truth for approved product intent, code, schemas, ADRs, issues, PRs, milestones, changelogs, tags, and validation evidence.

## Authority Order

When instructions conflict, use this order unless Ø explicitly overrides it:

1. Direct current instruction from Ø.
2. `BUILD_CONTRACT.md`.
3. `docs/PRD.md` and approved architecture/data/API specifications.
4. Accepted ADRs/RFCs.
5. Scoped GitHub issue + acceptance criteria.
6. `PROJECT_MEMORY.md` / approved decision registries.
7. Tool-specific files: `MANUS.md`, `TRAYCER.md`, `CODESPRING.md`.
8. Supporting CodeSpring/XYRA Markdown corpus relevant to the task.
9. Existing implementation behavior where not contradicted above.

Never silently resolve a material conflict. Record it in `OPEN_DECISIONS.md` and escalate.

## Required Work Loop — XYRA Gauntlet

`REQUIREMENT → PLAN → IMPLEMENT → VALIDATE → REVIEW → FIX → EVIDENCE → MERGE`

A task is not complete because code exists. It is complete only when requirements are traceable to implementation and passing evidence.

### Before implementation
- Read the issue/task.
- Resolve the applicable governing documents using `docs/CONTEXT_INDEX.md`.
- Read only the relevant CodeSpring/XYRA documents rather than loading the entire corpus.
- Identify applicable ADRs, schemas, API contracts, security rules, and acceptance criteria.
- Produce an implementation plan and test plan.
- Surface requirement conflicts before coding.

### During implementation
- Work on a scoped short-lived branch/worktree.
- Do not silently expand scope.
- Preserve deterministic boundaries for money, permissions, compliance gates, ranking, and audit logic.
- Keep external vendors behind adapters.
- Update tests and documentation with behavioral changes.

### Before merge
- Run required lint/type/unit/integration/e2e/security checks applicable to the change.
- Map acceptance criteria to evidence.
- Resolve material review findings or explicitly escalate them.
- Update `PROJECT_MEMORY.md` for durable architectural/product decisions.
- Update `OPEN_DECISIONS.md` for unresolved material decisions.
- Do not merge known critical defects.

## Branch / Environment Model

- `main` — production/release truth.
- `staging` — release-candidate integration.
- `develop` — active integration.
- scoped branches — `feature/*`, `fix/*`, `chore/*`, `docs/*`, `security/*`, `hotfix/*`.

Promote through PRs. Do not treat branches as interchangeable environments. Configuration and secrets remain environment-specific.

## Large Markdown Corpus Rule

ATLAS is expected to coexist with hundreds of CodeSpring/XYRA Markdown files. They are a dependency-aware knowledge system, **not one giant prompt**.

Rules:
- Store/organize corpus files by domain, phase, decision type, or work package.
- Register governing and high-value documents in `docs/CONTEXT_INDEX.md`.
- Every scoped task declares a `context_manifest` containing only documents required for that task.
- Use frontmatter/metadata where practical: `id`, `title`, `status`, `authority`, `domain`, `depends_on`, `supersedes`, `applies_to`, `last_updated`.
- Preserve status semantics: `LOCKED`, `OPEN`, `PROPOSED`, `SUPERSEDED`.
- Never let a lower-authority planning note silently override a locked specification.
- Archive/supersede obsolete documents rather than leaving contradictory active truth.
- Do not bulk-load hundreds of files into every model call.

## Escalation Classes

Escalate rather than improvise when encountering:
- requirement defect or contradiction;
- architecture failure requiring contract/ADR change;
- test expectation inconsistent with approved behavior;
- environment drift;
- unavoidable provider limitation;
- material security/privacy/compliance architecture change;
- monetization/business-model change;
- founder-control/ownership/ranking-integrity change.

## ATLAS Non-Negotiables

- Global by default; no country is privileged by hard-coded ranking bias.
- Founder sovereignty and mission are optimization constraints.
- Paid placement cannot silently affect organic match ranking.
- Explainability/provenance are first-class requirements.
- Compliance concerns produce configurable gates/review states rather than silent deletion of intended product architecture unless functionality is confirmed illegal/impossible.
- Human authorization gates consequential outreach, disclosure, document sharing, commitments, and transactions.
- Tenant isolation and auditability are mandatory.
