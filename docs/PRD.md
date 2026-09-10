# ATLAS Product Requirements Document

## 1. Product Objective
Build the global AI fundraising operating system for founders and investors. ATLAS must transform an ambiguous goal such as “raise $15M globally without losing control” into a sourced, ranked, trackable capital campaign.

## 2. Primary Personas
### Founder / CEO
Needs capital strategy, investor discovery, outreach, CRM, dilution modeling, diligence, and deal comparison.
### Founder Team / CFO
Needs permissions, financial scenarios, document management, reporting, and pipeline collaboration.
### Investor / Partner
Needs high-quality global deal flow aligned with a mandate.
### Investor Analyst
Needs filtering, research, diligence, notes, and IC preparation.
### ATLAS Admin / Trust Analyst
Needs verification, corrections, provenance, abuse controls, jurisdiction configuration, and auditability.

## 3. Jobs To Be Done
- Determine how much to raise and possible structures.
- Discover investors beyond existing social/geographic networks.
- Understand why each investor is relevant.
- Find the correct decision-maker and best available path.
- Generate truthful investor-specific materials quickly.
- Coordinate outreach without losing context.
- Prepare for meetings and diligence.
- Compare capital offers beyond headline valuation.
- Surface cross-border issues before they become expensive surprises.
- Learn which investors actually behave according to their stated mandates.

## 4. Founder Onboarding
Required structured fields should include company identity, jurisdiction, sector/subsector, business model, stage, traction, revenue state, funding history, cap table summary, current raise target/range, maximum desired dilution, runway, use of funds, target milestones, geographic preferences/exclusions, strategic needs, founder control priorities, target close date, and optional investor exclusions.

The onboarding AI may extract this information from uploaded decks/memos but must show extracted facts for confirmation before treating them as canonical.

## 5. Investor Onboarding
Investors may claim/verify an entity and define fund, check range, stages, sectors, geography, ownership targets, lead/follow preferences, strategic resources, exclusions, desired traction, and contact preferences. Claimed data does not erase observed evidence; ATLAS stores stated and observed profiles separately.

## 6. Capital Router Requirements
Given Company + Raise + Founder Priorities, return:
- financing scenarios
- priority investor archetypes
- region/country opportunities
- ranked investors
- likely leads and followers
- coverage analysis for round size
- strategic-value analysis
- relationship paths
- preparation gaps
- cross-border flags
- next-best actions

Every recommendation stores `router_version`, inputs, evidence set, generated_at, and confidence.

## 7. Match Requirements
Each match contains component scores, overall priority, eligibility state, confidence, positive evidence, negative evidence, missing evidence, conflicts, freshness, and explanation. Re-scoring must be reproducible from versioned inputs.

## 8. Search & Discovery
Filters: region, country, stage, sector, check range, fund type, strategic/financial, lead likelihood, cross-border history, portfolio conflict, freshness, relationship strength, and match score. Semantic natural-language search must map into transparent structured filters rather than silently hiding constraints.

## 9. Outreach
Support templates, AI-personalized drafts, sequences, manual approval, contact/channel preferences, send-state tracking via adapters, opt-out/suppression, bounce handling, follow-up reminders, and per-investor history. No autonomous mass-spam mode.

## 10. CRM
Provide Kanban/table/list views, custom stages, owners, notes, interactions, meetings, next action, probability, objections, commitments, requested documents, and analytics. A complete audit history is required for material stage/commitment changes.

## 11. Meetings
Before meeting: participant research, portfolio/thesis summary, likely questions, conflicts, talking points, and preparation checklist.
After meeting: user-approved summary, objections, requested follow-up, next steps, updated probability, and CRM state recommendation.

## 12. Data Room
Folders, document versions, viewer permissions, expiration, revocation, logs, request lists, Q&A, and watermark option. AI retrieval must enforce the same authorization boundary as direct file access.

## 13. Deal Room
Store offers and normalized terms. Compare dilution/control/economics/strategic value. Original documents remain authoritative. AI-extracted terms require human confirmation.

## 14. Cross-Border Review
A transaction context can be evaluated against jurisdiction rules. Results are informational flags with evidence/version/date and professional-review escalation. Product configuration must support jurisdiction feature flags without deleting global product architecture.

## 15. Notifications
Examples: investor mandate changed; target fund made relevant investment; contact replied; meeting tomorrow; diligence request overdue; data-room access; term-sheet deadline; material match score changed. Users control notification channels and frequency.

## 16. Success Metrics
North star: qualified investor conversations originated or materially accelerated by ATLAS.
Supporting: match→save, save→contact, contact→response, response→meeting, meeting→diligence, diligence→term sheet, term sheet→close, time-to-first-qualified-meeting, global diversity of qualified matches, stale-data rate, evidence coverage, and founder-reported match quality.

## 17. Anti-Metrics
Do not optimize raw email volume, vanity investor counts, pay-to-rank revenue, or engagement that does not improve financing outcomes.

## 18. Acceptance Criteria for V1
A founder can onboard, define a raise, receive sourced global investor matches, understand each score, save targets, draft approved outreach, manage investors through a CRM, model dilution, share selected diligence documents, record an offer, and compare it against another offer. Admins can correct investor data and inspect provenance/audit history.