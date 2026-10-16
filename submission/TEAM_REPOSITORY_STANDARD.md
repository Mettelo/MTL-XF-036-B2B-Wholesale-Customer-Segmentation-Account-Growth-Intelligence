# MTL-XF-036 — Team repository standard

Create **MTL-XF-036-<team-name>** under **Mettelo** and add individual member accounts. Record [master URL](https://github.com/Mettelo/MTL-XF-036-B2B-Wholesale-Customer-Segmentation-Account-Growth-Intelligence), reviewed master specification commit and final team commit/tag.

## Required areas

- README.md and CONTRIBUTIONS.md
- data/SOURCE_REGISTER.md; data/raw/README.md; data/reference/; data/metadata/; data/curated/
- docs/01-discovery/; docs/02-data-governance/; docs/03-data-model/; docs/04-data-quality/
- docs/05-kpi-catalogue/; docs/06-analysis/; docs/07-decision-framework/
- docs/08-assurance-uat/; docs/09-technical-handover/
- src/; tests/; dashboard/; deliverables/; submission/FINAL_SUBMISSION.md

Use sql/notebooks/analysis folders where useful; explain unused areas and avoid duplicate implementations. Pin free toolchain/dependencies and one documented run entry point. Keep raw payloads in approved storage outside Git, with verified manifest and reviewer access; never embed credentials.

## README and contribution evidence

State Choose three account-service propositions and up to ten cross-sell investigation candidates. Name B2B Sales Director as simulated sponsor. Include cohort, acquisition/restore, environment/run instructions, five findings, baseline/alternative, assumptions, UAT/rerun and evidence links. Preserve the simulated-client declaration and this limit: Spend is annual monetary units, not verified GBP, margin or growth. No time series, retention outcome, product-level baskets or sales-response labels exist. Proposed cross-sell actions require account-manager confirmation.

Assign named people to all seven [brief roles](../project/PROJECT_BRIEF.md). Every member links authored artefacts, at least one substantive review, and demo/handover contribution. Issues, commits, PRs and review records support evidence; commit count or one person's bulk upload is insufficient.

## Project-specific handover

Name segments using observed spend profiles and draft three account propositions with eligibility, outreach owner and evidence to collect.

Maintain D1–D12/AC1–AC12/DT1–DT10 evidence index with owner, distinct reviewer, state and final-commit path. Connect numeric claims to frozen source and code/configuration. Record all manual adjustments, excluded cases and limitations; preserve an insufficient-evidence case.

## Required business-output artefacts

- **D5 Annual category-spend profile:** data/curated/annual-category-spend-profile.csv and docs/05-kpi-catalogue/annual-category-spend-profile.md.
- **D6 Segmentation comparison and stability report:** docs/06-analysis/segmentation-comparison-and-stability-report.md plus machine-readable evaluation_results.csv.
- **D7 Account opportunity register and propositions:** docs/07-decision-framework/account-opportunity-register-and-propositions.csv plus policy.md.
- **D8 Account strategy dashboard:** dashboard/README.md, runnable dashboard/prototype and static review export.
- **D11 Sales adoption and validation plan:** deliverables/sales-adoption-and-validation-plan.pdf plus editable slides and supporting cards/runbook.

Index these under SC1–SC5 with author, distinct reviewer, executed result and final commit. Treat these paths as the default delivery contract; an equivalent tool-specific format requires an explicit documented mapping.

## Team organisation

The recommended team size is **3–5 people**. Delivery roles describe responsibilities, not separate positions: members can combine complementary business analysis, governance, engineering, analysis/modelling, BI and domain responsibilities. Assign a named owner to each deliverable and use a different team member to review critical calculations and perform the final clean rerun.
