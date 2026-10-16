# MTL-XF-036 — Data acquisition and engineering

## Approved S1

[Wholesale Customers](https://archive.ics.uci.edu/dataset/292); required files: **Wholesale customers data.csv**. Expected source population: 440 customer annual-spend records.

Exact official download:

https://archive.ics.uci.edu/static/public/292/wholesale+customers.zip

No paid API or temporary dashboard export is required. [Source register](SOURCE_REGISTER.md) records checked byte references and rights.

## Frozen cohort and schema

All 440 original records; no invented transaction dates, business names or recurring customer history. Keep Channel and Region for profiling, not clustering.

**Grain:** One customer annual-spend record; source row number is a local surrogate, not an externally identifiable account.

**Required fields:** Fresh, Milk, Grocery, Frozen, Detergents_Paper, Delicassen, Channel, Region.

## Acquisition and freeze procedure

1. Retrieve original bytes and required documentation into approved durable storage outside Git. Record retrieval UTC, requested/resolved URLs and HTTP result.
2. Verify archive/member integrity, actual sizes and SHA-256 against the checked reference. A mismatch stops processing for publisher-change/corruption review.
3. Inspect schema, encoding, separator, headers/sheets, count, label coding, dates and coverage. Preserve actual header spellings, field types and original row order; distinguish identifiers, predictors and outcomes.
4. Complete source→actual field→KPI→deliverable support matrix for K1–K7 and D1–D12. Missing mandatory fields block dependent work; do not invent substitutes.
5. Approve an immutable S1-v1 byte manifest and exact cohort with retention owner, reviewer access, analyst/reviewer identities and date. Master source verification does not replace team G1 approval.
6. Transform reproducibly into separate curated outputs. Account for every raw row once as retained, excluded or quarantined; preserve lineage and treatment reason.

## Evaluation

Core is descriptive segmentation. Fit log1p+scaling and compare k=2…6 clustering with seed 36; evaluate bootstrap stability over 50 resamples aligned to original assignments. Channel/Region are excluded from distance features; no supervised growth claims.

## Interpretation and quality

Spend is annual monetary units, not verified GBP, margin or growth. No time series, retention outcome, product-level baskets or sales-response labels exist. Proposed cross-sell actions require account-manager confirmation.

Profile every actual column. Dictionary includes spelling, type, unit, valid values, sentinel/null policy, meaning and feature/target/ID role plus availability time. Investigate duplicates/label conflicts; no silent deduplication or denominator invention. Validate key uniqueness and joins at the declared grain.

Keep [raw](raw/README.md), [references](reference/README.md) and [metadata](metadata/README.md) separate. Derived outputs belong in team data/curated/ or an approved location. Raw data are not uploaded by this update. Refresh creates a new snapshot while the accepted core stays reproducible.
