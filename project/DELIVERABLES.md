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

## D5 — KPI catalogue and lineage

**Due:** Week 4 · **Owner:** B2B Account Strategy Analyst · **Team location:** docs/05-kpi-catalogue/

Implement K1–K7 below with actual source fields, code, valid population, denominator, units, grain, exclusions, owner and worked examples.

**Pass evidence:** All seven reviewed; K1–K5 reconcile independently and in BI on full cohort and one filtered slice.

## D6 — Analysis and evaluation

**Due:** Week 6 · **Owner:** Data Scientist / Decision Modelling Analyst · **Team location:** docs/06-analysis/

Core is descriptive segmentation. Fit log1p+scaling and compare k=2…6 clustering with seed 36; evaluate bootstrap stability over 50 resamples aligned to original assignments. Channel/Region are excluded from distance features; no supervised growth claims.

**Pass evidence:** Baseline and alternative results, population/class counts, uncertainty, negative findings and feature/timing audit retained; no test-driven tuning.

## D7 — Decision policy and action register

**Due:** Week 6 · **Owner:** B2B Account Strategy Analyst · **Team location:** docs/07-decision-framework/

Baseline uses Channel groups; alternative uses interpretable spend clusters. Compare raw-spend versus log-scaled clustering sensitivity. A candidate category is below its segment median share while total spend is above segment median; this is an investigation rule, not a predicted sale.

**Pass evidence:** Both policies and sensitivity outputs supplied; every action has evidence, eligibility, owner, next review and uncertainty. Include a defer case.

## D8 — Dashboard / decision prototype

**Due:** Week 7 · **Owner:** BI / Decision Product Developer · **Team location:** dashboard/

Four linked views: K1–K7 executive overview, source-supported diagnostics, policy/action comparison and quality/limitations for B2B Sales Director.

**Pass evidence:** Five metric/filter checks pass; frozen scope and limitations survive export; static copy/user guide require no paid access.

## D9 — Independent assurance and UAT

**Due:** Week 7 · **Owner:** Segmentation Assurance Analyst · **Team location:** docs/08-assurance-uat/

Execute DT1–DT10 and three stakeholder tasks; record actual results and defects/retests.

**Pass evidence:** All ten tests and three tasks pass; zero unresolved critical/high defects.

## D10 — Technical/operational handover

**Due:** Week 8 · **Owner:** Engineer + Delivery Lead · **Team location:** docs/09-technical-handover/

One documented run entry point, dependency versions, manifest, output checksums/tolerances, refresh, rollback and operational owner.

**Pass evidence:** Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded.

## D11 — Executive recommendation

**Due:** Week 8 · **Owner:** Delivery Lead + domain specialist · **Team location:** deliverables/

8–12 slides and a 5–10-minute demo answering Choose three account-service propositions and up to ten cross-sell investigation candidates. Include five evidence-linked findings, three next actions, comparison and a defer case.

**Pass evidence:** Every numeric claim links tested evidence; costs/benefits and operational targets are labelled assumptions unless measured.

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
