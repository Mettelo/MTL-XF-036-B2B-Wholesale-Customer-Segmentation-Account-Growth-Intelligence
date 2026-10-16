# MTL-XF-036 — B2B Wholesale Customer Segmentation Account Growth Intelligence

**Track:** Cross-Functional · **Sector:** Private-sector commercial operations · **Team:** 6–8 · **Duration:** 8 weeks

## The business problem

The wholesale sales director must allocate account-manager attention across customers with different annual category mixes. A customer with high total spend but a low category share may warrant a conversation, but low share alone does not establish unmet demand. The team needs understandable groups, evidence that the grouping is stable, and a shortlist account managers can validate before offering a different service or cross-sell proposition.

**Simulated organisation:** Confidential Wholesale Distributor. **Accountable decision owner:** B2B Sales Director.

## Practical use case

At quarterly account planning, sales reviews spend profiles and cluster stability, compares them with existing channel groups, and assigns three service propositions and up to ten account-category investigation cases.

**Decision the project must enable:** Choose three account-service propositions and up to ten cross-sell investigation candidates.

**Current approach:** Apply the same account treatment across heterogeneous category-spend profiles.

**Required future approach:** Use interpretable, tested segment profiles and evidence-labelled account conversations.

## Specific deliverables

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Annual category-spend profile | 440 row-keyed customer profiles with six category spends, total, shares, Channel/Region and zero/invalid flags. |
| D6 | Segmentation comparison and stability report | Channel baseline, k=2…6 log-scaled clustering, silhouette, 50-bootstrap adjusted Rand stability and raw-vs-log sensitivity; segment sizes and spend profiles. |
| D7 | Account opportunity register and propositions | Up to ten below-segment-median category-share/above-median-total cases plus exactly three service propositions, or documented deferrals. |
| D8 | Account strategy dashboard | Segment profile, channel/region context, stability and candidate register views. |
| D11 | Sales adoption and validation plan | Three proposition cards with audience, service change, account-owner role, discovery questions, pilot comparator and success/guardrail measures. |

These five business outputs sit inside the full D1–D12 engagement. The team also delivers requirements/process mapping, source governance, engineering and quality evidence, independent UAT, handover and contribution records. [Detailed deliverable specifications](project/DELIVERABLES.md) define owners, artefact paths, fields, calculations and review evidence.

## Required success criteria

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Annual category-spend profile | Totals equal sum of six categories; positive-total shares sum to 1 within 1e−9; monetary units are not relabelled GBP; zero totals yield unavailable shares. |
| SC2 | D6 — Segmentation comparison and stability report | Channel/Region/row IDs excluded from distance; label permutations aligned; select or reject segmentation with explicit stability/interpretability evidence, not silhouette alone. |
| SC3 | D7 — Account opportunity register and propositions | Every case includes row ID, segment, category share, comparator, total spend, account-manager question and owner; no predicted growth, churn or confirmed cross-sell demand. |
| SC4 | D8 — Account strategy dashboard | Reviewer explains one segment in ordinary sales terms, traces a candidate to its six spend values and identifies an unstable/deferred case. |
| SC5 | D11 — Sales adoption and validation plan | Each card names evidence needed from account conversations and future transactions; no growth claim from a single annual snapshot. |

These are assessment requirements, not claims that results have already been achieved. At G1 the team records simulated stakeholder approval of scope, policy assumptions and criteria; later changes require a decision log. Financial benefit, causal uplift, production safety and operational adoption need separate pilot evidence. [Acceptance and worked tests](project/ACCEPTANCE_CRITERIA.md) control pass/fail.

## Data and fixed analytical boundary

**Official source:** [Wholesale Customers](https://archive.ics.uci.edu/dataset/292). **Required input:** Wholesale customers data.csv. **Expected source population:** 440 customer annual-spend records.

All 440 original records; no invented transaction dates, business names or recurring customer history. Keep Channel and Region for profiling, not clustering.

**Download:** https://archive.ics.uci.edu/static/public/292/wholesale+customers.zip

Spend is annual monetary units, not verified GBP, margin or growth. No time series, retention outcome, product-level baskets or sales-response labels exist. Proposed cross-sell actions require account-manager confirmation.

The [source register](data/SOURCE_REGISTER.md) records checked hashes, exact acquisition and snapshot rules. No raw data are uploaded; teams retain immutable originals outside Git with a manifest and reviewer access.

## Analysis and decision rules

Core is descriptive segmentation. Fit log1p+scaling and compare k=2…6 clustering with seed 36; evaluate bootstrap stability over 50 resamples aligned to original assignments. Channel/Region are excluded from distance features; no supervised growth claims.

Baseline uses Channel groups; alternative uses interpretable spend clusters. Compare raw-spend versus log-scaled clustering sensitivity. A candidate category is below its segment median share while total spend is above segment median; this is an investigation rule, not a predicted sale.

Report measured baselines and alternatives, sample sizes, uncertainty and failure cases. A weaker model does not justify disguising results: the final recommendation must say whether to retain the baseline, improve the prototype or run a controlled pilot, and cite the evidence.

## Who does what

- Business Analyst / Delivery Lead: eight testable user requirements, process map and decision-to-evidence traceability.
- Data Governance Analyst: source rights, frozen cohort, field support and seven-KPI lineage.
- Data Engineer: reproducible model/pipeline, exact row accounting and key/join checks.
- B2B Account Strategy Analyst: Name segments using observed spend profiles and draft three account propositions with eligibility, outreach owner and evidence to collect.
- Data Scientist / Decision Modelling Analyst: baseline/alternative, feature timing, validation and sensitivity.
- BI / Decision Product Developer: the specified decision views, filter reconciliation and static export.
- Segmentation Assurance Analyst: independent checks, three stakeholder walkthroughs and clean rerun.

Assign named authors and distinct reviewers; combining roles cannot remove independent review.

## Delivery and review

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | B2B Sales Director, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, B2B Account Strategy Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | B2B Sales Director reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Segmentation Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Full master pack

[Project brief](project/PROJECT_BRIEF.md) · [Business context](project/BUSINESS_CONTEXT.md) · [Deliverables](project/DELIVERABLES.md) · [Success criteria and tests](project/ACCEPTANCE_CRITERIA.md) · [Governance](project/GOVERNANCE.md) · [Data guidance](data/README.md) · [Submission](submission/README.md).

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
