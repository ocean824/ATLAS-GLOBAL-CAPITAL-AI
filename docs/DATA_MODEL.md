# ATLAS Canonical Data Model

## Identity
`users`, `organizations`, `memberships`, `roles`, `sessions`, `api_keys`, `entitlements`.

## Companies
`companies`: identity, jurisdiction, website/domain, description, sector taxonomy, stage.
`founders`: person profile linked to company/user where applicable.
`company_metrics`: temporal KPI facts with period/source.
`funding_rounds`: historical financing.
`cap_table_snapshots`: summarized ownership snapshots; sensitive access.
`raises`: active/planned raise objective and constraints.
`raise_scenarios`: modeled financing scenarios.

## Investors
`investor_entities`: VC/CVC/family office/sovereign/accelerator/strategic/etc.
`funds`: fund-specific mandate and lifecycle.
`investor_people`: partners/analysts/decision makers.
`mandates`: stated/observed investment criteria with validity period.
`portfolio_companies` and `investment_events`.
`investor_resources`: distribution, technical, recruiting, market access, etc.

## Evidence
`sources`: canonical source records.
`claims`: atomic sourced claims.
`claim_reviews`: verification/correction workflow.
`entity_aliases`: names/domains/identifiers.
`entity_merge_events`: auditable entity resolution.

## Matching
`matches`: company/raise/investor/fund relationship.
`match_components`: dimension, score, weight, confidence.
`match_evidence`: evidence links and polarity.
`match_versions`: algorithm/config version.
`router_runs`: complete Capital Router execution.
`router_recommendations`: regions/archetypes/investors/actions.

## Relationships
`people`, `relationship_edges`, `contact_methods`, `connection_imports`, `intro_paths`.
Private edges include visibility/consent scope.

## CRM
`pipeline_records`, `interactions`, `meetings`, `tasks`, `campaigns`, `campaign_steps`, `messages`, `objections`, `commitments`.

## Diligence
`data_rooms`, `folders`, `documents`, `document_versions`, `permission_grants`, `document_access_events`, `diligence_requests`, `diligence_answers`.

## Deals
`offers`, `offer_versions`, `terms`, `term_extractions`, `deal_comparisons`, `strategic_commitments`.

## Rules
`jurisdictions`, `rules`, `rule_versions`, `transaction_contexts`, `assessments`, `assessment_findings`, `professional_review_requests`.

## AI & Audit
`model_runs`, `prompt_versions`, `evaluations`, `audit_events`, `notifications`.

## Billing
`plans`, `subscriptions`, `usage_records`, `invoices`, `partner_attributions`.

## Required Cross-Cutting Columns
Where relevant: `id`, `organization_id`, `created_at`, `updated_at`, `created_by`, `deleted_at`, `version`, `metadata`.

## Money
Never store money in floating-point. Store integer minor units plus ISO currency, or exact decimal with explicit precision. Scenario calculations must declare currency and FX timestamp/source when conversion occurs.

## Time
UTC canonical timestamps; preserve source timezone when material. Deadlines and meetings retain IANA timezone.

## Sensitive Data
Classify columns/documents: PUBLIC, INTERNAL, CONFIDENTIAL, HIGHLY_SENSITIVE. Access and logging policy depends on classification.