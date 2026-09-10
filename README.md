# ATLAS — Global Capital AI

> **Project:** ATLAS — AI-Native Global Capital Operating System
> **Founder / Product Direction:** Ø
> **Status:** Strategic Blueprint / Full System Architecture
> **Tagline:** Capital Without Borders.
> **Version:** 0.1 Blueprint
> **Last Updated:** September 2026

---

## Mission

ATLAS is an AI-native global capital operating system designed to reduce geographic, institutional, informational, and network-based barriers between founders and capital.

ATLAS does **not** assume Silicon Valley, the United States, or any single financial center is the default or optimal source of startup capital. It asks a more useful question:

> **Where in the world is this company most financeable, by whom, on what terms, through what path, and with what strategic value beyond cash?**

ATLAS converts a startup's goals, fundamentals, ownership constraints, sector, stage, geography, strategic needs, and risk profile into an executable global fundraising strategy. It then discovers investors, ranks fit, explains the match, finds paths to decision-makers, prepares fundraising materials, manages outreach and diligence, compares offers, and helps founders move from capital discovery to close.

The long-term product progression is:

**AI Fundraising OS → Global Investor Graph → Capital Marketplace → Transaction Infrastructure → Global Private-Market Network.**

ATLAS exists to make capital discovery more competitive, transparent, global, and founder-accessible without pretending that securities, sanctions, foreign-investment, tax, privacy, AML/KYC, or other legal requirements disappear on the internet or on-chain.

---

## Core Principles

1. **Global by default.** Geography is a variable, not a gatekeeper.
2. **Founder sovereignty.** Optimize access to capital without silently optimizing away founder control, mission, IP, or long-term objectives.
3. **Capital must compete.** A founder should be able to compare investors and offers rather than treating the first term sheet as the only path.
4. **Strategic value matters.** Distribution, infrastructure, hiring, market access, technical support, partnerships, regulatory experience, and customer access may matter as much as valuation.
5. **Explainable matching.** Every investor score must expose the evidence and reasoning behind the recommendation.
6. **Freshness over stale directories.** ATLAS should continuously update investor mandates, partners, portfolio activity, check sizes, geography, and demonstrated behavior.
7. **Compliance-ready, not compliance-paralyzed.** Preserve useful product and monetization architecture while implementing jurisdiction/provider configuration, eligibility controls, disclosures, auditability, and professional-review escalation where required.
8. **AI assists; humans authorize consequential actions.** Outreach, disclosure, document sharing, negotiations, commitments, and transactions require explicit permissions appropriate to their consequence.
9. **Privacy is structural.** Confidential founder information and investor information must be permissioned, minimized, encrypted, and auditable.
10. **No pay-to-rank corruption.** Paid placement must never silently alter organic investor-match scores.
11. **Evidence beats marketing claims.** Distinguish what investors say they fund from what they demonstrably fund.
12. **Model agnostic.** ATLAS orchestration must support multiple LLM/model providers and permit future local/private inference.

---

## Product Surfaces

### Founder Workspace
- Company and raise profile
- Capital strategy generator
- Investor matches and explanations
- Global capital map
- Raise scenario modeling
- Pitch/deck and narrative workspace
- Outreach sequencing
- Fundraising CRM
- Data room and diligence tracker
- Meetings, objections, follow-ups, and commitments
- Offer/term-sheet comparison
- Founder control and dilution simulator

### Investor Workspace
- Investment mandate profile
- Deal-flow inbox
- AI-ranked opportunities
- Saved searches/theses
- Company diligence workspace
- Permissioned data-room Q&A
- Team notes and pipeline
- Intro/request-meeting workflows
- Offer/interest workflows where enabled

### ATLAS Intelligence Layer
- Global Investor Graph
- Company Graph
- Capital Router
- Match Engine
- Investor Intelligence Agents
- Warm-Path Graph
- Raise Architect
- Pitch Intelligence
- Diligence Intelligence
- Deal Intelligence
- Cross-Border Rules Engine
- Learning/Outcome Engine

### Administrator / Trust Console
- Verification queues
- entity/investor corrections
- data provenance
- abuse/fraud review
- jurisdiction feature flags
- model/prompt versions
- audit logs
- ranking integrity monitoring
- subscription/billing controls

---

## The Capital Router

The Capital Router is the central ATLAS primitive. Given a structured company and raise objective, it produces a ranked capital strategy rather than a generic list of funds.

Example input:

> U.S.-based AI-first gaming infrastructure company. Raising $20M. Founder is willing to sell up to 20%. Open to global strategic and financial investors. Founder prioritizes speed, distribution, technical resources, global market access, and retention of meaningful operating control.

Example output:

- recommended raise structure and scenarios
- target investor archetypes
- priority countries/regions
- lead-investor candidates
- strategic candidates
- likely check-size coverage
- fit/confidence score with evidence
- conflicts/competitive portfolio exposure
- warm introduction paths
- relevant recent investments
- likely objections and preparation
- cross-border review flags
- next-best actions

ATLAS should be capable of concluding that the optimal source of capital is in Shenzhen, Singapore, Seoul, Tokyo, Abu Dhabi, Riyadh, Lagos, London, São Paulo, New York, or a combination thereof. Country is never a hard-coded preference.

---

## Global Investor Graph

The graph models investors as evolving entities rather than static directory rows.

Investor attributes include:
- entity and fund identity
- offices and operating geographies
- fund vintage where known
- fund size / estimated capital base where supportable
- stage preferences
- sectors and subsectors
- stated check range
- observed initial check range
- follow-on behavior
- lead/follow tendencies
- ownership targets where evidenced
- geography preferences
- cross-border investment history
- strategic resources
- relevant partners and decision-makers
- portfolio companies
- co-investor relationships
- competitive conflicts
- recent investments and exits
- thesis statements/interviews
- response/outcome history generated inside ATLAS
- source provenance and freshness timestamps

Every material fact must carry provenance, confidence, and freshness metadata.

---

## Match Engine

A match is multi-dimensional, explainable, and versioned. Initial scoring dimensions should include:

- sector fit
- stage fit
- check-size fit
- geography fit
- cross-border appetite
- business-model fit
- traction fit
- round-lead probability
- ownership/dilution compatibility
- strategic-resource fit
- portfolio conflict
- thesis recency
- investment recency
- founder priorities
- warm-path strength
- historical ATLAS response/meeting/close signals when sufficient data exists

The system must distinguish **eligibility**, **fit**, **confidence**, and **priority**. An investor can be eligible but low fit; high fit but low-confidence due to stale data; or strategically excellent but lower priority due to a direct portfolio conflict.

No opaque single score may be treated as ground truth. Users receive component scores and evidence.

---

## Raise Architect

The Raise Architect models alternative capitalization plans such as:

- priced equity
- SAFE / convertible structures where applicable
- strategic minority investment
- multiple co-investors
- project/subsidiary financing
- venture debt or other non-dilutive/less-dilutive capital where appropriate
- grants and public programs
- revenue-based or asset-backed alternatives where relevant

It models pre/post-money valuation, dilution, option-pool effects, founder ownership, investor ownership, follow-on rounds, runway, milestone financing, and scenario sensitivity. It must not present legal/tax outputs as professional advice.

---

## Deal Comparison Engine

ATLAS compares the complete economic and strategic package rather than headline valuation alone.

A comparison may include:
- cash invested
- pre/post-money valuation
- dilution
- liquidation preference
- participation
- anti-dilution
- board rights
- voting/control rights
- pro-rata rights
- information rights
- exclusivity
- ROFR/ROFO provisions
- IP restrictions
- territorial rights
- publishing/distribution rights
- strategic commitments
- milestone obligations
- founder vesting changes
- expected follow-on support
- estimated strategic value with explicit assumptions

The engine must label uncertain assumptions and never fabricate term-sheet language.

---

## Warm-Path Graph

ATLAS should identify lawful, permissioned relationship paths from founder to target decision-maker using connected sources and imported contact data. It should rank paths by relationship strength and relevance while protecting private contact information.

Direct cold outreach remains a first-class path; the product must not reproduce the gatekeeping problem it exists to reduce.

---

## Pitch Intelligence

One canonical company truth model powers audience-specific narratives. ATLAS may emphasize different legitimate aspects of the company for a gaming strategic, sovereign-backed fund, U.S. VC, family office, or corporate investor, but it may **never alter underlying facts** to suit an audience.

Outputs may include:
- investor-specific executive summary
- deck narrative
- outreach email
- meeting brief
- FAQ preparation
- likely objections
- data-room request checklist
- follow-up memo

All generated factual claims should be traceable to company-provided data or cited external evidence.

---

## Fundraising CRM

Pipeline states should support:

`DISCOVERED → QUALIFIED → INTRO_PATH → CONTACTED → RESPONDED → MEETING → DILIGENCE → PARTNER/IC → TERM_SHEET → COMMITTED → CLOSED`

with configurable terminal states such as `PASSED`, `DECLINED`, `PAUSED`, and `NOT_A_FIT`.

The CRM records interactions, next actions, objections, documents requested/shared, stakeholder mapping, meeting notes, probability estimates, commitments, and source attribution.

---

## Data Room & Diligence

ATLAS supports permissioned folders/documents, granular access, expiration/revocation, watermarking where desired, access logs, version history, document classification, diligence checklists, and AI Q&A restricted to authorized content.

High-sensitivity documents must never become general model-training data by default.

---

## Cross-Border Rules Engine

ATLAS is global without pretending borders do not exist. A policy/rules layer should surface potential requirements related to:

- securities offering rules
- investor eligibility/accreditation
- KYC/AML and beneficial ownership
- sanctions
- foreign direct investment review
- CFIUS and analogous regimes
- export controls
- data residency/privacy
- tax considerations
- industry-specific restrictions
- marketing/solicitation limitations
- payments/stablecoins/digital assets

The engine outputs `INFORMATION`, `REVIEW_REQUIRED`, `RESTRICTED_PENDING_CONFIGURATION`, or `BLOCKED_BY_CONFIRMED_RULE` states with source/version/jurisdiction metadata. Uncertainty escalates rather than silently deleting functionality.

---

## Blockchain / On-Chain Layer

Blockchain is infrastructure, not the product's identity. Candidate capabilities include:

- verifiable identity/eligibility credentials
- ownership/cap-table attestations
- document and consent proofs
- shareholder voting records
- programmable transaction workflows
- stablecoin settlement where lawful and provider-supported
- compliant transfer controls
- future tokenized private-market instruments where legally structured

ATLAS must never assume that tokenization removes securities, tax, AML/KYC, sanctions, or licensing obligations.

---

## AI Agent Architecture

Recommended logical agents/services:

1. **Navigator** — user-facing orchestrator and next-best-action engine.
2. **Cartographer** — builds and maintains the global investor/company graph.
3. **Scout** — discovers investors, funds, people, mandates, and changes.
4. **Analyst** — calculates explainable match scores and comparisons.
5. **Architect** — capitalization/raise scenario modeling.
6. **Diplomat** — investor-specific communications and meeting preparation.
7. **Pathfinder** — relationship/warm-path analysis.
8. **Librarian** — company knowledge/data-room retrieval and provenance.
9. **Sentinel** — permissions, privacy, policy, jurisdiction, and risk gates.
10. **Closer** — pipeline intelligence, diligence progress, term comparison, and closing checklists.
11. **Observer** — outcome learning, drift detection, ranking evaluation, and data-quality monitoring.

Agents are logical roles, not mandatory one-model-per-agent processes. Runtime orchestration should select the cheapest/reliable model or deterministic service appropriate to each task.

---

## High-Level Technical Architecture

```text
Web / Mobile / API
       |
API Gateway + Auth
       |
ATLAS Orchestrator
       |
+------+---------+-----------+-----------+
|                |           |           |
Capital Graph   Match      Raise       CRM
Service         Engine     Architect    Service
|                |           |           |
Intel/Ingestion  AI Gateway  Rules       Data Room
|                |           Engine      Service
+----------------+-----------+-----------+
                 |
        Postgres + Vector + Object Storage
                 |
      Queue / Events / Audit / Analytics
```

Recommended baseline:
- TypeScript end-to-end where practical
- Next.js web application
- React/React Native or PWA-first mobile strategy
- Node.js service layer; Python services for research/ML/data workloads where justified
- PostgreSQL as canonical transactional store
- pgvector/vector service for semantic retrieval
- graph representation using relational edge tables initially; dedicated graph DB only when query economics justify it
- Redis-compatible cache/queues where required
- object storage for data-room assets
- event-driven ingestion workers
- model-provider abstraction supporting OpenAI, Anthropic, Google, open/local models, and future providers
- OpenTelemetry-compatible observability
- infrastructure-as-code

Vendor selections must remain replaceable behind adapters.

---

## Core Data Model

Primary entities:

`User, Organization, Company, Founder, Raise, InvestorEntity, Fund, InvestorPerson, InvestmentMandate, PortfolioCompany, InvestmentEvent, RelationshipEdge, Match, MatchEvidence, OutreachCampaign, Interaction, Meeting, PipelineRecord, Document, DataRoom, PermissionGrant, DiligenceRequest, Offer, Term, ComplianceAssessment, JurisdictionRule, Source, Evidence, ModelRun, AuditEvent, Subscription, Entitlement.`

Every intelligence object should support source/evidence linkage and timestamps.

---

## API Domains

Planned versioned domains:

- `/v1/auth`
- `/v1/organizations`
- `/v1/companies`
- `/v1/raises`
- `/v1/investors`
- `/v1/funds`
- `/v1/matches`
- `/v1/router`
- `/v1/relationships`
- `/v1/outreach`
- `/v1/crm`
- `/v1/data-rooms`
- `/v1/diligence`
- `/v1/offers`
- `/v1/compliance`
- `/v1/intelligence`
- `/v1/agents`
- `/v1/audit`
- `/v1/billing`

All consequential mutation endpoints require authorization, idempotency where applicable, audit events, and explicit tenant scoping.

---

## Security & Trust Baseline

- strict multi-tenant isolation
- RBAC/ABAC authorization
- MFA/passkeys support
- encryption in transit and at rest
- managed secret storage; no secrets in source
- signed/expiring document links
- malware scanning for uploads
- audit logging
- rate limiting and abuse detection
- CSRF/XSS/SQLi/SSRF defenses
- dependency/SAST/secret scanning in CI
- backups and tested recovery
- retention/deletion controls
- model prompt-injection defenses for retrieved documents/web content
- PII minimization
- human approval gates for consequential outbound actions
- red-team testing for data exfiltration and cross-tenant retrieval

See `SECURITY.md` and `docs/THREAT_MODEL.md`.

---

## Monetization Architecture

ATLAS should support multiple configurable revenue models without corrupting ranking integrity:

- founder SaaS tiers
- investor/team SaaS tiers
- enterprise/CVC subscriptions
- premium intelligence/data products
- data-room/diligence tooling
- API access
- verified marketplace services
- optional transaction/success economics only where legally and operationally permissible
- partner/referral revenue with disclosure
- future compliant transaction infrastructure

**Hard rule:** payment never secretly purchases a higher organic investor-match score.

---

## V1 Definition

V1 proves one thing exceptionally well:

> **ATLAS can identify, explain, prioritize, and help founders reach high-fit global investors they otherwise would have missed.**

V1 scope:
- authentication/organizations
- founder/company/raise onboarding
- investor/fund database with provenance
- ingestion/update pipeline
- Capital Router
- explainable Match Engine
- global investor discovery/search
- saved targets
- basic relationship paths
- pitch/outreach generation
- fundraising CRM
- meeting/follow-up intelligence
- lightweight permissioned data room
- raise/dilution scenario modeling
- jurisdiction flagging framework
- subscriptions/entitlements
- admin/data-quality console
- analytics and outcome capture

V1 explicitly does **not require** securities settlement, secondary trading, tokenized securities, automated investment execution, or a dedicated graph database.

---

## Evolution

### V1 — Global Fundraising OS
Prove matching, routing, outreach, and raise management.

### V2 — Intelligence Network
Deepen proprietary outcome data, relationship graph, diligence, investor workflows, APIs, and institutional data quality.

### V3 — Capital Marketplace
Verified companies and investors; structured inbound interest; controlled competitive offer workflows; deeper diligence collaboration.
