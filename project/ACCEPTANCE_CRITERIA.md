# MTL-XF-036 — Acceptance and domain tests

Acceptance requires executed evidence, not headings. Segmentation Assurance Analyst records state, actual result, evidence/commit, date, author, reviewer and defect/retest reference. Templates start NOT RUN.

## AC1–AC12

| Criterion | Output | Measurable pass condition |
| --- | --- | --- |
| AC1 | D1 | All eight link source support, D/AC/DT and B2B Sales Director approval. |
| AC2 | D2 | Every required file/field is verified and approved; unsupported requirements explicitly block G1. |
| AC3 | D3 | Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist. |
| AC4 | D4 | Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion. |
| AC5 | D5 / SC1 | Totals equal sum of six categories; positive-total shares sum to 1 within 1e−9; monetary units are not relabelled GBP; zero totals yield unavailable shares. |
| AC6 | D6 / SC2 | Channel/Region/row IDs excluded from distance; label permutations aligned; select or reject segmentation with explicit stability/interpretability evidence, not silhouette alone. |
| AC7 | D7 / SC3 | Every case includes row ID, segment, category share, comparator, total spend, account-manager question and owner; no predicted growth, churn or confirmed cross-sell demand. |
| AC8 | D8 / SC4 | Reviewer explains one segment in ordinary sales terms, traces a candidate to its six spend values and identifies an unstable/deferred case. |
| AC9 | D9 | All ten tests and three tasks pass; zero unresolved critical/high defects. |
| AC10 | D10 | Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded. |
| AC11 | D11 / SC5 | Each card names evidence needed from account conversations and future transactions; no growth claim from a single annual snapshot. |
| AC12 | D12 | All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count. |

## SC1–SC5 — Business output success contracts

These requirements supplement AC1–AC12 and are mandatory. Record approval at G1, then execute against final outputs. All five require PASS with traceable evidence, or a formally approved scope revision; an unmet model-performance target must be reported as unmet and reflected in the recommendation.

### SC1 / D5 — Annual category-spend profile

**Accountable delivery role:** B2B Account Strategy Analyst. **Business reviewer:** B2B Sales Director. **Independent assurance:** Segmentation Assurance Analyst.

**Required artefact:** data/curated/annual-category-spend-profile.csv and docs/05-kpi-catalogue/annual-category-spend-profile.md.

**Content:** 440 row-keyed customer profiles with six category spends, total, shares, Channel/Region and zero/invalid flags.

**Pass condition:** Totals equal sum of six categories; positive-total shares sum to 1 within 1e−9; monetary units are not relabelled GBP; zero totals yield unavailable shares.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC2 / D6 — Segmentation comparison and stability report

**Accountable delivery role:** Data Scientist / Decision Modelling Analyst. **Business reviewer:** B2B Sales Director. **Independent assurance:** Segmentation Assurance Analyst.

**Required artefact:** docs/06-analysis/segmentation-comparison-and-stability-report.md plus machine-readable evaluation_results.csv.

**Content:** Channel baseline, k=2…6 log-scaled clustering, silhouette, 50-bootstrap adjusted Rand stability and raw-vs-log sensitivity; segment sizes and spend profiles.

**Pass condition:** Channel/Region/row IDs excluded from distance; label permutations aligned; select or reject segmentation with explicit stability/interpretability evidence, not silhouette alone.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC3 / D7 — Account opportunity register and propositions

**Accountable delivery role:** B2B Account Strategy Analyst. **Business reviewer:** B2B Sales Director. **Independent assurance:** Segmentation Assurance Analyst.

**Required artefact:** docs/07-decision-framework/account-opportunity-register-and-propositions.csv plus policy.md.

**Content:** Up to ten below-segment-median category-share/above-median-total cases plus exactly three service propositions, or documented deferrals.

**Pass condition:** Every case includes row ID, segment, category share, comparator, total spend, account-manager question and owner; no predicted growth, churn or confirmed cross-sell demand.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC4 / D8 — Account strategy dashboard

**Accountable delivery role:** BI / Decision Product Developer. **Business reviewer:** B2B Sales Director. **Independent assurance:** Segmentation Assurance Analyst.

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

**Content:** Segment profile, channel/region context, stability and candidate register views.

**Pass condition:** Reviewer explains one segment in ordinary sales terms, traces a candidate to its six spend values and identifies an unstable/deferred case.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC5 / D11 — Sales adoption and validation plan

**Accountable delivery role:** Business Analyst / Delivery Lead with domain specialist. **Business reviewer:** B2B Sales Director. **Independent assurance:** Segmentation Assurance Analyst.

**Required artefact:** deliverables/sales-adoption-and-validation-plan.pdf plus editable slides and supporting cards/runbook.

**Content:** Three proposition cards with audience, service change, account-owner role, discovery questions, pilot comparator and success/guardrail measures.

**Pass condition:** Each card names evidence needed from account conversations and future transactions; no growth claim from a single annual snapshot.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.


## DT1–DT10

| Test | Case | Expected result |
| --- | --- | --- |
| DT1 | Units preserved | 100 monetary units cannot be relabelled £100. |
| DT2 | Zero total | All six spends zero gives missing shares and manual review, not six fabricated zero proportions. |
| DT3 | Feature isolation | Channel, Region and row ID in clustering features fail the feature audit. |
| DT4 | Outlier sensitivity | Raw and log-scaled cluster membership changes are quantified; outliers are not silently deleted. |
| DT5 | No temporal claim | A customer cannot be labelled declining or churned from one annual record. |
| DT6 | Cluster identity | Permuted cluster numbers are aligned before stability assessment; labels alone are not compared. |
| DT7 | Source row accounting | One malformed fixture row is quarantined with source ID/reason; retained+excluded+quarantined equals input with no overlap. |
| DT8 | Missing versus zero | A 0/0 rate is unavailable with reason. Missing source evidence never becomes a measured zero or a fabricated result. |
| DT9 | BI reconciliation | K1–K5 match independent calculations on full cohort and one filtered slice. Counts exact; arithmetic unrounded or tolerance at most 0.01 displayed unit. |
| DT10 | Independent rerun | Distinct member reproduces cohort IDs, K1–K7 and policy selections from frozen bytes/configuration. Any stochastic tolerance is declared before running and discrepancies resolved. |

Use small synthetic fixtures for edge cases and frozen-source checks where relevant. Clearly distinguish fixture results from measured source outputs. Retain expected/actual evidence in docs/08-assurance-uat/; automate deterministic calculations where practical and document UI/interpretation reviews.

## Three project-specific UAT tasks

1. **Business review:** At quarterly account planning, sales reviews spend profiles and cluster stability, compares them with existing channel groups, and assigns three service propositions and up to ten account-category investigation cases. The participant must explain the observed baseline, population and decision limitation without assistance from the author; record actual completion and any defect.
2. **Policy challenge:** use the D7 artefact to compare a baseline and alternative case, then record accept/defer/override with evidence and accountable owner. The domain reviewer must independently reproduce the case outcome.
3. **Operational walkthrough:** Reviewer explains one segment in ordinary sales terms, traces a candidate to its six spend values and identifies an unstable/deferred case. Retain the task recording/screenshots, expected/actual values and reviewer outcome.

All three must pass after defect retest. Static exports may support review if interactive access is unavailable. The independent reviewer also checks every SC output against its declared artefact and source/configuration lineage.

## Release

All twelve ACs, ten DTs, UAT and independent rerun require evidence with zero unresolved critical/high defects. Underperformance can justify a baseline/manual policy; wrong labels/units, leakage, unregistered data or unsupported operational claims block acceptance. A scope revision updates affected requirements/tests; it cannot mark an unexecuted check passed.
