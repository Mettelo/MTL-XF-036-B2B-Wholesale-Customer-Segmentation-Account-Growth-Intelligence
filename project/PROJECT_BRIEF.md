# MTL-XF-036 — Project brief

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

**Client:** Confidential Wholesale Distributor · **Sponsor:** B2B Sales Director · **Team:** 6–8 · **Duration:** 8 weeks · **Cycle:** quarterly account planning review

## Problem and commission

The wholesale sales director must allocate account-manager attention across customers with different annual category mixes. A customer with high total spend but a low category share may warrant a conversation, but low share alone does not establish unmet demand. The team needs understandable groups, evidence that the grouping is stable, and a shortlist account managers can validate before offering a different service or cross-sell proposition.

> Choose three account-service propositions and up to ten cross-sell investigation candidates.

## Practical use case and business outputs

At quarterly account planning, sales reviews spend profiles and cluster stability, compares them with existing channel groups, and assigns three service propositions and up to ten account-category investigation cases.

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Annual category-spend profile | 440 row-keyed customer profiles with six category spends, total, shares, Channel/Region and zero/invalid flags. |
| D6 | Segmentation comparison and stability report | Channel baseline, k=2…6 log-scaled clustering, silhouette, 50-bootstrap adjusted Rand stability and raw-vs-log sensitivity; segment sizes and spend profiles. |
| D7 | Account opportunity register and propositions | Up to ten below-segment-median category-share/above-median-total cases plus exactly three service propositions, or documented deferrals. |
| D8 | Account strategy dashboard | Segment profile, channel/region context, stability and candidate register views. |
| D11 | Sales adoption and validation plan | Three proposition cards with audience, service change, account-owner role, discovery questions, pilot comparator and success/guardrail measures. |

## Required success contract

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Annual category-spend profile | Totals equal sum of six categories; positive-total shares sum to 1 within 1e−9; monetary units are not relabelled GBP; zero totals yield unavailable shares. |
| SC2 | D6 — Segmentation comparison and stability report | Channel/Region/row IDs excluded from distance; label permutations aligned; select or reject segmentation with explicit stability/interpretability evidence, not silhouette alone. |
| SC3 | D7 — Account opportunity register and propositions | Every case includes row ID, segment, category share, comparator, total spend, account-manager question and owner; no predicted growth, churn or confirmed cross-sell demand. |
| SC4 | D8 — Account strategy dashboard | Reviewer explains one segment in ordinary sales terms, traces a candidate to its six spend values and identifies an unstable/deferred case. |
| SC5 | D11 — Sales adoption and validation plan | Each card names evidence needed from account conversations and future transactions; no growth claim from a single annual snapshot. |

[Detailed acceptance](ACCEPTANCE_CRITERIA.md) defines executed evidence; [deliverables](DELIVERABLES.md) defines exact artefacts and ownership. G1 records simulated sponsor approval, not invented real-client agreement.

## Core scope

All 440 original records; no invented transaction dates, business names or recurring customer history. Keep Channel and Region for profiling, not clustering.

Required source: Wholesale customers data.csv. Model grain: One customer annual-spend record; source row number is a local surrogate, not an externally identifiable account.

Spend is annual monetary units, not verified GBP, margin or growth. No time series, retention outcome, product-level baskets or sales-response labels exist. Proposed cross-sell actions require account-manager confirmation.

Additional datasets, live integrations, operational deployment and claims of achieved benefits are outside core. Scope/source changes need approval and updated tests.

## Cross-functional roles

| Role | Required evidence |
| --- | --- |
| Business Analyst / Delivery Lead | Eight numbered prioritised requirements for Choose three account-service propositions and up to ten cross-sell investigation candidates. As-is/to-be workflow, stakeholder map and requirement→D→AC→DT traceability. |
| Data Governance Analyst | S1 rights, byte manifest, field support, approved cohort and lineage for all seven KPIs; review Treating mathematically separated clusters as stable business needs or claimed growth forecasts would overstate the evidence. |
| Data Engineer | Reproducible ingestion, curated model, source-row ledger and key/join controls at grain: One customer annual-spend record; source row number is a local surrogate, not an externally identifiable account. |
| B2B Account Strategy Analyst | Name segments using observed spend profiles and draft three account propositions with eligibility, outreach owner and evidence to collect. |
| Data Scientist / Decision Modelling Analyst | Baseline/alternative implementation, evaluation manifest, uncertainty and sensitivity. Core is descriptive segmentation. Fit log1p+scaling and compare k=2…6 clustering with seed 36; evaluate bootstrap stability over 50 resamples aligned to original assignments. Channel/Region are excluded from distance features; no supervised growth claims. |
| BI / Decision Product Developer | Four views for the quarterly account planning review: overview, diagnostics, action/policy comparison, quality/limitations. Five independent KPI reconciliations and static export. |
| Segmentation Assurance Analyst | Execute DT1–DT10, three UAT tasks and a distinct-member clean rerun; record expected/actual evidence, defects and retests. |

Assign named owners and review partners at kickoff. Combine roles only when a distinct member reviews critical calculations and performs final clean rerun. Sponsor labels describe simulated roles, separate from actual team identities.

## Evaluation contract

Core is descriptive segmentation. Fit log1p+scaling and compare k=2…6 clustering with seed 36; evaluate bootstrap stability over 50 resamples aligned to original assignments. Channel/Region are excluded from distance features; no supervised growth claims.

Record predictor allowlist, target mapping, timing assumptions, partition/resample IDs and train-only transforms. Report partition/class counts and uncertainty. Negative model results can support a manual/baseline recommendation; invented performance cannot.

## Decision contract

Baseline uses Channel groups; alternative uses interpretable spend clusters. Compare raw-spend versus log-scaled clustering sensitivity. A candidate category is below its segment median share while total spend is above segment median; this is an investigation rule, not a predicted sale.

## Objectives and gates

Deliver D1–D12, K1–K7, AC1–AC12, ten executed domain tests, three UAT tasks, five reconciliations and an independent rerun. The sponsor must trace one action to source and explain why uncertain cases are deferred.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | B2B Sales Director, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, B2B Account Strategy Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | B2B Sales Director reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Segmentation Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

[Deliverables](DELIVERABLES.md), [acceptance](ACCEPTANCE_CRITERIA.md), [data register](../data/SOURCE_REGISTER.md).
