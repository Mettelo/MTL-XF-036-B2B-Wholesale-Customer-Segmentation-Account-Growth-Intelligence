# MTL-XF-036 — Deliverables and metric contracts

**Decision:** Choose three account-service propositions and up to ten cross-sell investigation candidates.

Required team outputs follow; this master does not claim they are complete. Each item needs a named author, distinct reviewer, version, evidence link and status.

## D1 — Discovery and requirements

**Due:** Week 2 · **Owner:** Business Analyst / Delivery Lead · **Team location:** docs/01-discovery/

Eight user requirements, prioritised by decision value, each with owner and measurable test; stakeholder map and as-is/to-be workflow for quarterly account planning review.

**Pass evidence:** All eight link source support, D/AC/DT and B2B Sales Director approval.

## D2 — Governed source and freeze

**Due:** Week 2 · **Owner:** Data Governance Analyst · **Team location:** docs/02-data-governance/

S1 provenance, rights, dictionary, storage/restore path and immutable byte manifest. All 440 original records; no invented transaction dates, business names or recurring customer history. Keep Channel and Region for profiling, not clustering.

**Pass evidence:** Every required file/field is verified and approved; unsupported requirements explicitly block G1.

## D3 — Engineering pipeline and model

**Due:** Week 4 · **Owner:** Data Engineer · **Team location:** src/ and docs/03-data-model/

Versioned ingestion/transformation and curated model. Grain: One customer annual-spend record; source row number is a local surrogate, not an externally identifiable account. Preserve file/sheet/row lineage and all exclusion reasons.

**Pass evidence:** Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist.

## D4 — Quality and exceptions

**Due:** Week 4 · **Owner:** Data Engineer + independent reviewer · **Team location:** docs/04-data-quality/

Profile types, nulls, duplicates, sentinels, labels, units and source support. Address Treating mathematically separated clusters as stable business needs or claimed growth forecasts would overstate the evidence.

**Pass evidence:** Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion.

## D5 — Annual category-spend profile

**Due:** Week 4 · **Owner:** B2B Account Strategy Analyst · **Business reviewer:** B2B Sales Director · **Independent reviewer:** Segmentation Assurance Analyst

**Required artefact:** data/curated/annual-category-spend-profile.csv and docs/05-kpi-catalogue/annual-category-spend-profile.md.

440 row-keyed customer profiles with six category spends, total, shares, Channel/Region and zero/invalid flags.

**Mandatory pass condition (SC1):** Totals equal sum of six categories; positive-total shares sum to 1 within 1e−9; monetary units are not relabelled GBP; zero totals yield unavailable shares.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D6 — Segmentation comparison and stability report

**Due:** Week 6 · **Owner:** Data Scientist / Decision Modelling Analyst · **Business reviewer:** B2B Sales Director · **Independent reviewer:** Segmentation Assurance Analyst

**Required artefact:** docs/06-analysis/segmentation-comparison-and-stability-report.md plus machine-readable evaluation_results.csv.

Channel baseline, k=2…6 log-scaled clustering, silhouette, 50-bootstrap adjusted Rand stability and raw-vs-log sensitivity; segment sizes and spend profiles.

**Mandatory pass condition (SC2):** Channel/Region/row IDs excluded from distance; label permutations aligned; select or reject segmentation with explicit stability/interpretability evidence, not silhouette alone.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D7 — Account opportunity register and propositions

**Due:** Week 6 · **Owner:** B2B Account Strategy Analyst · **Business reviewer:** B2B Sales Director · **Independent reviewer:** Segmentation Assurance Analyst

**Required artefact:** docs/07-decision-framework/account-opportunity-register-and-propositions.csv plus policy.md.

Up to ten below-segment-median category-share/above-median-total cases plus exactly three service propositions, or documented deferrals.

**Mandatory pass condition (SC3):** Every case includes row ID, segment, category share, comparator, total spend, account-manager question and owner; no predicted growth, churn or confirmed cross-sell demand.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D8 — Account strategy dashboard

**Due:** Week 7 · **Owner:** BI / Decision Product Developer · **Business reviewer:** B2B Sales Director · **Independent reviewer:** Segmentation Assurance Analyst

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

Segment profile, channel/region context, stability and candidate register views.

**Mandatory pass condition (SC4):** Reviewer explains one segment in ordinary sales terms, traces a candidate to its six spend values and identifies an unstable/deferred case.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D9 — Independent assurance and UAT

**Due:** Week 7 · **Owner:** Segmentation Assurance Analyst · **Team location:** docs/08-assurance-uat/

Execute DT1–DT10 and three stakeholder tasks; record actual results and defects/retests.

**Pass evidence:** All ten tests and three tasks pass; zero unresolved critical/high defects.

## D10 — Technical/operational handover

**Due:** Week 8 · **Owner:** Engineer + Delivery Lead · **Team location:** docs/09-technical-handover/

One documented run entry point, dependency versions, manifest, output checksums/tolerances, refresh, rollback and operational owner.

**Pass evidence:** Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded.

## D11 — Sales adoption and validation plan

**Due:** Week 8 · **Owner:** Business Analyst / Delivery Lead with domain specialist · **Business reviewer:** B2B Sales Director · **Independent reviewer:** Segmentation Assurance Analyst

**Required artefact:** deliverables/sales-adoption-and-validation-plan.pdf plus editable slides and supporting cards/runbook.

Three proposition cards with audience, service change, account-owner role, discovery questions, pilot comparator and success/guardrail measures.

**Mandatory pass condition (SC5):** Each card names evidence needed from account conversations and future transactions; no growth claim from a single annual snapshot.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D12 — Contribution and final submission

**Due:** Weekly; final week 8 · **Owner:** Delivery Lead · **Team location:** CONTRIBUTIONS.md and submission/FINAL_SUBMISSION.md

Named D owners/reviewers, authored work, issues/PRs/commits, substantive reviews and demo/handover contribution for each member.

**Pass evidence:** All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count.

## K1–K7 — Authoritative contracts

| ID | Metric | Definition and population | Grain |
| --- | --- | --- | --- |
| K1 | Total annual spend | sum of six category spends, monetary units. | customer/segment |
| K2 | Category share | category spend / customer total; zero total yields unavailable. | customer |
| K3 | Segment size | customers assigned to segment and share of all eligible customers. | segment |
| K4 | Median account spend | median customer annual total; also show IQR. | segment |
| K5 | Silhouette | mean silhouette using declared transformed feature space; not a business-value score. | candidate k |
| K6 | Cluster stability | median adjusted Rand index over 50 bootstrap fits on common record IDs; label small/unstable segments. | candidate k |
| K7 | Candidate count | number meeting documented below-median category-share and above-median total-spend rule. | segment/category |

Extend each contract with actual S1 raw fields and curated columns, code lineage, population/exclusions, numerator/denominator, units/grain, aggregation, missing/zero/undefined policy, owner/reviewer, freeze ID and tests. B2B Account Strategy Analyst owns interpretation; Engineer implements; Segmentation Assurance Analyst reviews.

Zero denominators produce unavailable values with reasons. Do not average subgroup rates when compatible summed numerators/denominators are required. Show class/segment counts beside rates and uncertainty. Counts reconcile exactly; arithmetic reconciles unrounded or to a documented tolerance no wider than 0.01 displayed unit. No source field can silently be replaced by an assumption.

## Evaluation and decision policy

Core is descriptive segmentation. Fit log1p+scaling and compare k=2…6 clustering with seed 36; evaluate bootstrap stability over 50 resamples aligned to original assignments. Channel/Region are excluded from distance features; no supervised growth claims.

Baseline uses Channel groups; alternative uses interpretable spend clusters. Compare raw-spend versus log-scaled clustering sensitivity. A candidate category is below its segment median share while total spend is above segment median; this is an investigation rule, not a predicted sale.

**Interpretation boundary:** Spend is annual monetary units, not verified GBP, margin or growth. No time series, retention outcome, product-level baskets or sales-response labels exist. Proposed cross-sell actions require account-manager confirmation.

See [acceptance](ACCEPTANCE_CRITERIA.md) for tests and [governance](GOVERNANCE.md) for release decisions.
