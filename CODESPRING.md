# CodeSpring Role — ATLAS / XYRA

CodeSpring is the scoped implementation and validation execution layer.

## Start

Read:
1. `AGENTS.md`;
2. assigned GitHub issue/work package;
3. its `context_manifest`;
4. relevant governing specs/ADRs;
5. acceptance criteria.

Do **not** ingest every Markdown file by default.

## Execution

Use an isolated branch/worktree. Follow:

`REQUIREMENT → PLAN → IMPLEMENT → VALIDATE → REVIEW → FIX → EVIDENCE → MERGE`

Before coding, restate the implementation plan, interfaces affected, migration impact, and tests required. During coding, stay inside scope unless a discovered dependency is necessary and documented.

## Gauntlet Evidence

A completion packet should contain:
- requirement IDs satisfied;
- files/modules changed;
- migrations/config changes;
- tests added/updated;
- commands executed and results;
- security/privacy checks relevant to the change;
- screenshots/artifacts for UI behavior when applicable;
- known limitations;
- unresolved findings;
- PR/commit references.

## Defect Handling

- Requirement defect: escalate; do not silently rewrite.
- Architecture defect: propose ADR/contract change; re-Gauntlet affected scope.
- Test defect: correct only when governing evidence proves expectation wrong.
- Environment defect: repair environment and rerun; drift is itself a finding.
- Third-party defect: implement appropriate retry/fallback/degradation/error behavior; provider blame alone does not close the finding.
- Known provider limitation: document explicitly.

No critical known defect is considered release-ready.
