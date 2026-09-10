# ATLAS — Unified Master Build Plan (V1 → V2 → V3)

> **Directive:** Build ATLAS as one coherent platform in one engineering program. V1/V2/V3 are capability gates and release milestones, **not three unrelated rewrites**.
>
> **Process:** Ø → Manus → GitHub → Traycer → CodeSpring → Gauntlet → Release
>
> **Target end-state:** Global Fundraising OS → Intelligence Network → Capital Marketplace / transaction-ready private-market infrastructure.

---

## 0. ONE-SHOT BUILD PHILOSOPHY

The architecture, data model, permissions, events, APIs, audit system, billing/entitlements, AI gateway, evidence/provenance system, jurisdiction rules, and provider-adapter boundaries are designed from day one for the V3 end-state. Releases progressively activate capabilities through entitlements, feature flags, jurisdiction/provider configuration, and maturity gates.

**Do not:** build V1 as disposable CRUD; create incompatible V2 schemas; bolt marketplace identity onto founder-only accounts later; hard-code one model/provider; hard-code U.S.-only assumptions; or delete V3 architecture merely because a feature is not launch-enabled in V1.

**Do:** create durable primitives once, expose them progressively, migrate deliberately, and keep inactive future capabilities behind tested interfaces/flags.

---

# 1. PLATFORM FOUNDATIONS — SHARED BY V1/V2/V3

## 1.1 Monorepo / application topology

Recommended logical topology:

```text
apps/
  web/                 Founder + Investor + Admin web
  api/                 Public/internal API gateway
  workers/             ingestion, enrichment, notifications, jobs
  mobile/              later mobile client / PWA packaging
packages/
  auth/
  db/
  domain/
  schemas/
  api-contracts/
  ui/
  ai-gateway/
  evidence/
  investor-graph/
  matching/
  capital-router/
  raise-architect/
  relationships/
  crm/
  outreach/
  dataroom/
  diligence/
  offers/
  marketplace/
  compliance-rules/
  transactions/
  billing/
  audit/
  observability/
  feature-flags/
  integrations/
  testing/
```

## 1.2 Foundational services

Build before feature verticals:
- authentication, MFA/passkey-ready identity;
- organizations, memberships, roles, permissions;
- founder/company/investor identities;
- canonical Postgres schema + migrations;
- object storage abstraction;
- queue/event bus abstraction;
- cache abstraction;
- audit event pipeline;
- notifications;
- feature flags/entitlements;
- subscription/billing abstraction;
- AI model gateway with provider routing;
- embeddings/retrieval abstraction;
- evidence/provenance framework;
- source/provider adapter framework;
- observability, traces, metrics, structured logs;
- secrets/configuration framework;
- CI/CD and environment isolation;
- backup/recovery;
- privacy/retention/deletion primitives.

## 1.3 End-state identity model

Users may participate in multiple organizations and roles. Do not create mutually exclusive founder/investor account types. An organization can have company/fund/investor capabilities according to verified identity and entitlements.

## 1.4 End-state event model

Domain events include:
`CompanyUpdated, RaiseOpened, InvestorUpdated, MatchComputed, RouteComputed, RelationshipImported, OutreachApproved, OutreachSent, ResponseReceived, MeetingLogged, DataRoomGranted, DocumentViewed, DiligenceRequested, InterestSubmitted, OfferSubmitted, OfferUpdated, ComplianceAssessmentChanged, TransactionStateChanged, SubscriptionChanged`.

Events power notifications, analytics, outcome learning, audit, integrations, and future marketplace workflows.

---

# 2. V1 — GLOBAL FUNDRAISING OPERATING SYSTEM

## V1 objective

A founder can onboard a company and raise, receive evidence-backed global investor matches and a capital strategy, execute/manage outreach, track the raise, run dilution scenarios, prepare meetings, share diligence materials, and compare offers.

## V1-A. Authentication, organizations, trust
- email/OAuth authentication;
- MFA/passkey-ready architecture;
- organizations/memberships;
- founder/admin/member/viewer roles;
- invitation flow;
- session/device management;
- account recovery;
- audit history;
- privacy/export/delete controls;
- organization security settings.

**Acceptance:** no cross-tenant resource access; authorization tests cover every protected resource family.

## V1-B. Company Truth Model

Structured onboarding captures:
- legal/display identity;
- location/jurisdictions;
- founders/team;
- sector/subsector;
- business model;
- product/technology;
- stage;
- traction/KPIs;
- revenue/funding history;
- cap-table summary;
- IP/strategic assets;
- competitors;
- target markets;
- strategic needs;
- documents/evidence.

Create versioned `CompanyTruth` snapshots. Generated investor material must trace factual claims to this source.

## V1-C. Raise Workspace

Capture:
- target/min/max raise;
- security/instrument preferences;
- valuation assumptions;
- dilution ceiling/preferences;
- runway/milestones;
- lead/follow needs;
- geographic openness;
- strategic priorities;
- control/IP constraints;
- timing;
- existing commitments;
- target investor exclusions.

Support multiple raises historically but one configurable active raise per company initially.

## V1-D. Global Investor Graph

Implement canonical investor entities, funds, people, mandates, investment events, portfolio companies, geography, sector/stage/check behavior, strategic resources, relationships, sources, claims, confidence, and freshness.

### Ingestion
`DISCOVER → FETCH → NORMALIZE → ENTITY RESOLVE → EXTRACT → PROVENANCE → CONFIDENCE → REVIEW/ACCEPT → GRAPH → REFRESH`.

Admin surfaces:
- entity-resolution queue;
- contradiction queue;
- correction workflow;
- source health;
- freshness dashboard;
- ingestion run history.

## V1-E. Explainable Match Engine

Implement `docs/MATCH_ENGINE_SPEC.md` as deterministic/versioned scoring configuration.

Every result exposes:
- eligibility;
- fit;
- confidence;
- priority;
- strategic value;
- component scores;
- evidence;
- observed vs stated mandate;
- conflicts;
- freshness;
- scoring version.

Support save, dismiss, shortlist, notes, filters, compare, and feedback.

## V1-F. Capital Router

Produce a complete global capitalization strategy:
- investor archetypes;
- priority regions;
- leads;
- strategics;
- co-investors;
- check-size coverage;
- capital gaps;
- structure options;
- geographic rationale;
- sequencing;
- jurisdiction flags;
- likely objections;
- next-best actions.

Founder can re-weight speed, valuation, dilution, control, strategic resources, distribution, follow-on capacity, and relationship access and observe routing changes.

## V1-G. Raise Architect

Scenario engine for:
- priced equity;
- SAFE/convertible abstractions;
- strategic minority;
- multiple co-investors;
- project/subsidiary capital;
- debt/non-dilutive alternatives where configured.

Calculate pre/post money, ownership, dilution, option pool impact, runway, milestone coverage, follow-on scenarios. Use decimal-safe deterministic math.

## V1-H. Relationship / Warm-Path Graph

Permissioned import/connectors for relationship sources. Build person/org edges with source, strength, recency, and permission scope. Show best paths while preserving cold outreach as a first-class option.

## V1-I. Pitch Intelligence

From canonical company truth generate:
- executive summary;
- investor-specific narrative;
- deck outline/copy;
- outreach drafts;
- meeting brief;
- FAQ/objections;
- follow-up memo;
- diligence checklist.

Never mutate facts to fit investor preferences. Require citations/evidence for material claims.

## V1-J. Outreach Engine

- templates;
- personalized drafts;
- sequences;
- scheduling;
- explicit send approvals;
- provider adapters;
- delivery/bounce/reply events;
- unsubscribe/suppression handling where applicable;
- rate/abuse controls;
- campaign analytics.

AI draft != send authorization.

## V1-K. Fundraising CRM

Pipeline:
`DISCOVERED → QUALIFIED → INTRO_PATH → CONTACTED → RESPONDED → MEETING → DILIGENCE → PARTNER_IC → TERM_SHEET → COMMITTED → CLOSED` plus terminal/paused states.

Views: Kanban, table, investor detail, timeline, calendar/activity, funnel analytics.

Track owners, stakeholders, notes, interactions, objections, probability, next action, documents, commitments, source attribution.

## V1-L. Meeting Intelligence

- pre-meeting brief;
- attendee profiles;
- portfolio/conflict context;
- likely questions;
- note/transcript import;
- action extraction;
- follow-up generation;
- objection taxonomy;
- CRM updates after approval.

## V1-M. Data Room + Diligence Lite

- rooms/folders/documents;
- upload/versioning;
- granular grants;
- expiring/revocable access;
- signed links;
- access audit;
- malware scanning;
- document classification;
- authorized RAG/Q&A;
- diligence request tracker.

## V1-N. Offer / Term Comparison

Structured offer and term ingestion. Compare economics, control, governance, strategic value, restrictions, territorial/IP rights, founder vesting, follow-on, assumptions, and review flags. Never fabricate absent terms.

## V1-O. Cross-Border Rules Framework

Rules are versioned by jurisdiction, source, effective date, product capability, and state:
`INFORMATION | REVIEW_REQUIRED | RESTRICTED_PENDING_CONFIGURATION | BLOCKED_BY_CONFIRMED_RULE`.

Initial domains: securities, eligibility, KYC/AML/beneficial ownership, sanctions, foreign-investment review, export controls, privacy/data, tax flags, solicitation, payments/digital assets.

## V1-P. Billing / entitlements

Support founder tiers, investor-ready future tiers, enterprise feature flags, API entitlements, usage metering, trials/coupons, invoices/provider webhooks. Organic ranking is isolated from commercial placement.

## V1-Q. Founder UI

Public site + onboarding + Command Center + Capital Map + Matches + Investor Detail + Router + Raise Architect + CRM + Outreach + Meetings + Data Room + Offers + Company Truth + Settings.

## V1-R. Admin / Trust UI

Data quality, corrections, source health, rules, ranking versions, model runs, abuse, audit, support access, billing support, feature flags.

## V1-S. V1 Gauntlet

Must pass:
- functional acceptance suite;
- tenant isolation;
- authorization matrix;
- scoring golden tests;
- financial math golden tests;
- ingestion/entity-resolution tests;
- prompt-injection/RAG boundary tests;
- audit completeness;
- backup restore exercise;
- accessibility baseline;
- browser/device coverage;
- performance/load baseline;
- dependency/SAST/secret scanning;
- threat-model review.

**V1 release gate:** real founders can run a complete raise workflow without spreadsheet/manual system dependence for core ATLAS functions.

---

# 3. V2 — GLOBAL CAPITAL INTELLIGENCE NETWORK

## V2 objective

Turn ATLAS from a founder-side fundraising tool into a two-sided intelligence network with investor workspaces, richer proprietary outcome intelligence, institutional collaboration, deeper diligence, APIs/integrations, and continuously improving matching.

## V2-A. Investor Organization Onboarding
- investor/CVC/family-office/fund profiles;
- verification workflow;
- fund vehicles;
- team roles;
- mandates;
- check/stage/geography/sector preferences;
- exclusion/conflict policies;
- thesis editor;
- strategic-resource profile;
- inbound deal preferences;
- notification controls.

## V2-B. Investor Deal Flow
- AI-ranked company feed;
- thesis-specific feeds;
- search/filter;
- saved companies;
- internal ratings;
- team notes;
- assignment;
- stage/pipeline;
- meeting/diligence workflows;
- pass reasons;
- watchlists;
- portfolio conflict alerts.

Founder confidential data appears only when permissions permit.

## V2-C. Bidirectional Matching

Compute:
- founder→investor fit;
- investor→company fit;
- mutual fit;
- confidence;
- strategic complementarity;
- conflict probability.

Allow verified investors to improve their stated mandate while preserving independent observed-behavior intelligence.

## V2-D. Outcome Learning Engine

Capture privacy-safe events across response, meeting, diligence, pass, term sheet, close, check size, time-to-response, and follow-on.

Requirements:
- minimum sample thresholds;
- cohort controls;
- leakage prevention;
- bias/fairness monitoring;
- offline evaluation before ranking changes;
- versioned models;
- rollback;
- explainability.

Do not let engagement optimization override founder objectives.

## V2-E. Advanced Relationship Graph

- organization/person networks;
- co-investment graph;
- syndication patterns;
- board/advisor relationships;
- founder/investor introductions;
- relationship recency/strength;
- introduction request workflow;
- permission-aware connector enrichment.

## V2-F. Institutional Diligence Workspace

Expand V1 data room into:
- standardized diligence templates;
- request lists;
- ownership of requests;
- document Q&A;
- source citations;
- red-flag extraction;
- financial/model imports;
- legal/security/commercial workstreams;
- version comparison;
- completion dashboards;
- exportable diligence reports;
- investor team collaboration.

## V2-G. Company Readiness / Raise Readiness

AI evaluates completeness—not investment worthiness as fact—across data room, metrics, narrative consistency, governance, security, legal documentation, financial model, cap table, and investor FAQs. Surface missing evidence and contradictions.

## V2-H. Advanced Capital Strategy

- round construction optimizer;
- lead/follow syndicate simulation;
- ownership concentration;
- reserve/follow-on analysis;
- strategic vs financial investor mix;
- geography diversification;
- milestone tranching scenarios;
- downside/control scenarios;
- probability/time-to-close ranges with uncertainty.

## V2-I. Global Market Intelligence

Dashboards for:
- investment activity by sector/stage/region;
- check-size movement;
- active funds;
- thesis changes;
- cross-border flows;
- co-investment networks;
- fundraising velocity;
- portfolio concentrations;
- emerging capital hubs.

All aggregate products require privacy thresholds and source licensing compliance.

## V2-J. Enterprise / CVC

- SSO/SAML-ready auth;
- custom roles;
- team workspaces;
- custom mandates/scoring overlays;
- internal CRM integrations;
- portfolio/import connectors;
- API keys/service accounts;
- audit exports;
- retention policies;
- custom data connectors;
- procurement/security documentation.

## V2-K. Developer Platform

Public/partner API + webhooks for companies, investor intelligence (licensed/entitled), matching, CRM, diligence, and events. Add OAuth/app authorization model, scopes, rate limits, usage billing, developer console, API docs, sandbox.

## V2-L. Integration Marketplace

Adapters for CRM, email/calendar, cloud drives, data warehouses, cap-table providers, e-sign, identity/KYC, analytics, communications, and approved data providers. Connectors are permission-scoped and revocable.

## V2-M. Collaboration / Messaging

Controlled founder-investor messaging, document requests, meeting scheduling, notifications, and shared diligence threads. Anti-spam/abuse controls are mandatory.

## V2-N. Reputation / Verification

Verified identities, organization ownership, representative badges, data freshness, response reliability, and transaction-history attestations where lawful. Avoid simplistic public social-credit scoring.

## V2-O. Mobile

Founder/investor mobile experience for alerts, approvals, messages, meetings, pipeline, data-room notifications, saved matches, and next actions.

## V2-P. V2 Gauntlet

Add:
- two-sided permission tests;
- investor verification abuse tests;
- ranking bias/regression evaluation;
- enterprise isolation/SSO tests;
- API authorization/rate-limit tests;
- connector permission/revocation tests;
- aggregation privacy tests;
- messaging spam/abuse tests;
- higher-scale ingestion/load tests.

**V2 release gate:** founders and investors both receive independent value and the proprietary outcome graph measurably improves discovery/intelligence without compromising ranking integrity.

---

# 4. V3 — GLOBAL CAPITAL MARKETPLACE + TRANSACTION INFRASTRUCTURE

## V3 objective

Enable verified founders and investors to express structured interest, compete/collaborate around financing opportunities, coordinate syndicates, execute permissioned closing workflows, and support configurable transaction infrastructure where jurisdictions/providers allow.

V3 architecture is built early but transaction capabilities remain feature/jurisdiction/provider gated until launch requirements are satisfied.

## V3-A. Verified Marketplace Listings

Founders choose controlled visibility:
- private/invite-only;
- matched-investor only;
- verified-network discoverable;
- broader marketplace where configured.

Listing contains canonical truth snapshot, raise parameters, allowed disclosures,