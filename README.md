# MTL-XF-036 — B2B Wholesale Customer Segmentation Account Growth Intelligence

**Track:** Cross-Functional · **Use case:** Commercial / private sector · **Team:** 6–8 · **Duration:** 8 weeks

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Business commission

**Client:** Confidential Wholesale Distributor. **Decision owner:** B2B Sales Director. **Cadence:** quarterly account planning review.

Account managers apply one service model to customers with very different category spending. They need interpretable, stable customer groups to focus account conversations without mistaking low category spend for proven unmet demand.

**Decision:** Choose three account-service propositions and up to ten cross-sell investigation candidates.

## End-to-end delivery

Deliver business requirements, governed source acquisition, engineering and data quality, seven defined metrics, baseline/alternative policy comparison, decision dashboard, assurance/UAT, executive recommendation and operational handover. A model alone is insufficient.

Baseline uses Channel groups; alternative uses interpretable spend clusters. Compare raw-spend versus log-scaled clustering sensitivity. A candidate category is below its segment median share while total spend is above segment median; this is an investigation rule, not a predicted sale.

## Core dataset and frozen cohort

**S1:** [Wholesale Customers](https://archive.ics.uci.edu/dataset/292). **Input:** Wholesale customers data.csv. **Source population:** 440 customer annual-spend records.

All 440 original records; no invented transaction dates, business names or recurring customer history. Keep Channel and Region for profiling, not clustering.

Exact official download:

https://archive.ics.uci.edu/static/public/292/wholesale+customers.zip

Spend is annual monetary units, not verified GBP, margin or growth. No time series, retention outcome, product-level baskets or sales-response labels exist. Proposed cross-sell actions require account-manager confirmation.

No raw data are uploaded by this update. Teams preserve original bytes outside Git in an approved durable snapshot, with checksums, source metadata and reviewer access. The source register records verification evidence and acquisition rules.

## Pack navigation

- [Project brief](project/PROJECT_BRIEF.md) — scope, roles and milestones.
- [Business context](project/BUSINESS_CONTEXT.md) — stakeholders and decisions.
- [Deliverables](project/DELIVERABLES.md) — D1–D12 and K1–K7.
- [Acceptance criteria](project/ACCEPTANCE_CRITERIA.md) — AC1–AC12 and DT1–DT10.
- [Governance](project/GOVERNANCE.md) — gates, assumptions and changes.
- [Data guidance](data/README.md) and [source register](data/SOURCE_REGISTER.md).
- [Submission pack](submission/README.md) — team repository and final evidence.

## Evaluation and policy boundary

Core is descriptive segmentation. Fit log1p+scaling and compare k=2…6 clustering with seed 36; evaluate bootstrap stability over 50 resamples aligned to original assignments. Channel/Region are excluded from distance features; no supervised growth claims.

**Primary risk:** Treating mathematically separated clusters as stable business needs or claimed growth forecasts would overstate the evidence.

At G1 (week 2), approve requirements, source rights, actual schema and frozen bytes. At G2 (week 4), approve row accounting, all seven metrics and evaluation design. At G3 (week 6), review baseline/alternative and uncertainty. At G4 (week 8), require all twelve deliverables, ten executed domain tests, three UAT tasks, five reconciliations and a distinct-member clean rerun.

Assign named authors and review partners. Unsupported mandatory outputs remain blocked until an approved source/scope change resolves them. Record actual results in a separate Mettelo team repository; this master defines the work.
