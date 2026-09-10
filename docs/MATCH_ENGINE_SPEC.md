# Match Engine & Capital Router Specification

## Purpose

ATLAS ranks capital opportunities using evidence-backed compatibility rather than static sector tags. The engine produces separate `eligibility`, `fit`, `confidence`, `priority`, and `strategic_value` outputs.

## V1 Scoring Model

Normalize each component to `[0,100]`.

`FIT = 0.15 sector + 0.10 stage + 0.10 check_size + 0.08 geography + 0.08 cross_border + 0.07 business_model + 0.06 traction + 0.08 lead_probability + 0.06 ownership_compatibility + 0.10 strategic_resource + 0.05 warm_path + 0.07 observed_behavior`

Weights are configuration, versioned, and testable—not buried in prompts.

### Modifiers

- `portfolio_conflict`: 0 to -30
- `stale_mandate`: confidence penalty, not automatic fit penalty
- `sanctions_or_hard_eligibility`: eligibility gate
- `jurisdiction_review`: review flag; does not silently zero fit
- `founder_priority_alignment`: -10 to +10 priority modifier
- `recent_investment_signal`: 0 to +8 priority modifier

`PRIORITY = clamp(FIT + modifiers, 0, 100) × CONFIDENCE_FACTOR`

`CONFIDENCE_FACTOR` is derived from evidence count, source quality, agreement, and freshness. Low confidence must be visible.

## Evidence Requirements

Every component score stores:
- score
- explanation
- evidence/source IDs
- observed/stated classification
- captured_at
- source_updated_at when known
- confidence
- scoring model version

Never generate unsupported precision. Missing evidence produces `UNKNOWN`, not an invented value.

## Observed vs Stated Behavior

ATLAS explicitly separates:
- `stated_mandate`: what the investor says it wants;
- `observed_behavior`: what investment history demonstrates;
- `atlas_outcomes`: response/meeting/diligence/close behavior generated inside ATLAS.

Outcome data may influence ranking only after minimum sample/quality thresholds and bias monitoring.

## Capital Router

The Router consumes:
- company profile
- raise objective
- founder constraints
- strategic priorities
- investor graph
- jurisdiction/rules flags
- relationship graph
- portfolio conflicts
- scenario model

It returns:
1. recommended capital archetypes;
2. recommended geographic regions;
3. ranked lead candidates;
4. ranked strategic candidates;
5. likely co-investors;
6. check-size coverage/gap analysis;
7. dilution/structure scenarios;
8. cross-border review flags;
9. outreach sequencing;
10. next-best actions.

## Optimization Objective

The Router is multi-objective. It does not maximize valuation alone.

Candidate utility can be represented as:

`UTILITY = w1*capital_fit + w2*speed + w3*strategic_value + w4*distribution + w5*follow_on + w6*control_compatibility + w7*relationship_access - risk_penalties`

Weights are founder-configurable within safe product bounds. The UI must show how changing priorities changes recommendations.

## Ranking Integrity

- Sponsorship/payment is stored separately from organic rank.
- Admin users cannot manually alter an organic score without an auditable correction/evidence event.
- Model/prompt output cannot directly mutate deterministic scoring configuration.
- Ranking experiments require versioning and offline evaluation.
- Country/nationality cannot receive a hidden preferred/disfavored weight.

## Evaluation

Offline metrics:
- precision@K for founder saves/contacts/meetings;
- NDCG for relevance judgments;
- calibration of confidence;
- coverage across geographies/fund types;
- stale-data rate;
- evidence completeness;
- conflict false-negative rate.

Online funnel metrics:
`impression → save → contact → response → meeting → diligence → term sheet → close`.

Never optimize only for response rate if doing so reduces founder objective alignment or ranking integrity.
