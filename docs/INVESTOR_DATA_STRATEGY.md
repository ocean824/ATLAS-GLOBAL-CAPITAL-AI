# Investor Intelligence & Data Ingestion Strategy

## Goal

Build a continuously refreshed, provenance-first global investor graph without making ATLAS dependent on one commercial database.

## Source Classes

### Tier A — Primary / authoritative
- investor/fund official sites and portfolio pages
- regulatory/public filings
- company press releases
- official fund announcements
- official partner/team biographies
- government/public investment registries where applicable

### Tier B — High-quality secondary
- reputable financial/business publications
- structured licensed data providers
- established startup/private-market datasets

### Tier C — Discovery/community
- conference pages
- podcasts/interviews
- professional/social profiles where terms permit
- founder-reported ATLAS outcomes

Tier C can discover facts but material ranking claims should be corroborated when practical.

## Ingestion Pipeline

`DISCOVER → FETCH → NORMALIZE → ENTITY_RESOLVE → EXTRACT → PROVENANCE → CONFIDENCE → REVIEW/ACCEPT → GRAPH → FRESHNESS MONITOR`

### Raw layer
Immutable capture metadata: URL/provider, retrieval time, content hash, license/usage class, parser version.

### Normalized layer
Canonical entities and claims.

### Claim layer
Each claim records subject, predicate, value, source, confidence, effective date, observed/stated status, and supersession state.

## Entity Resolution

Resolve:
- investment firm vs fund vehicle;
- parent vs CVC subsidiary;
- similarly named firms;
- partner/person identity;
- portfolio company identity;
- fund vintage.

Never merge uncertain entities without confidence thresholds or review.

## Freshness

Suggested refresh classes:
- active mandate/team pages: weekly/monthly depending source cost;
- portfolio/news activity: daily/weekly;
- static regulatory identity: slower cadence;
- ATLAS outcome signals: event-driven.

Freshness affects confidence. It does not automatically erase historically useful evidence.

## Connectors / Adapters

Every external source implements an adapter contract:
- discover()
- fetch()
- normalize()
- rateLimitPolicy()
- provenance()
- licensePolicy()
- health()

No source-specific object should leak into the canonical domain model.

## Data Quality

Track:
- completeness
- freshness
- source agreement
- entity-resolution confidence
- extraction confidence
- contradiction count
- manual correction history

## Corrections

Users/investors may submit corrections. Corrections become reviewable claims; they do not destroy prior provenance. Verified investor representatives can receive stronger correction authority for their own stated mandate while observed investment history remains independently represented.

## Privacy / Terms

Do not build the core product around prohibited scraping, bypassed access controls, or undisclosed resale of restricted data. Store licensing/usage metadata per source/provider. Personal contact data requires a lawful basis, minimization, permission controls, and deletion/retention handling.

## Initial V1 Strategy

Start with a curated global set of high-value funds/strategics across regions and sectors, then expand breadth. Optimize data quality and match usefulness before raw record count. Seed the graph with primary sources plus licensed/public datasets, and use ATLAS outcomes to create proprietary intelligence over time.
