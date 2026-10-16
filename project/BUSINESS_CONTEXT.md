# MTL-XF-036 — Business context and practical use case

## Organisation and accountable decision

Confidential Wholesale Distributor is the simulated sponsor. The B2B Sales Director owns the quarterly account planning review and must decide: **Choose three account-service propositions and up to ten cross-sell investigation candidates.**

## The operational problem

The wholesale sales director must allocate account-manager attention across customers with different annual category mixes. A customer with high total spend but a low category share may warrant a conversation, but low share alone does not establish unmet demand. The team needs understandable groups, evidence that the grouping is stable, and a shortlist account managers can validate before offering a different service or cross-sell proposition.

## How the finished product will be used

At quarterly account planning, sales reviews spend profiles and cluster stability, compares them with existing channel groups, and assigns three service propositions and up to ten account-category investigation cases.

**Current approach:** Apply the same account treatment across heterogeneous category-spend profiles.

**Required future approach:** Use interpretable, tested segment profiles and evidence-labelled account conversations.

The review starts with a verified frozen population and measured baseline. The domain analyst demonstrates the specified business outputs, the operational owner challenges workload and feasibility, assurance challenges correctness, and the sponsor records accept/defer/override. Each action records a source/configuration reference, rationale, accountable role, next step and review date. Uncertain cases remain in a visible manual-review/defer route.

## Stakeholder responsibilities

| Stakeholder | Responsibility | Decision evidence |
| --- | --- | --- |
| B2B Sales Director | Approve scope, project assumptions, acceptance contract and final recommendation. | SC1–SC5 outputs; baseline/alternative trade-offs; pilot/investigation actions. |
| B2B Account Strategy Analyst | Name segments using observed spend profiles and draft three account propositions with eligibility, outreach owner and evidence to collect. | Domain scorecard, worked cases, supported interpretation and source lineage. |
| Operational service owner | Accept workload, assignment and escalation route. | Case register, capacity/threshold comparison, due dates and overrides. |
| Data Governance Analyst | Confirm source identity, rights, exact freeze and required fields. | S1 manifest and source→field→measure→deliverable matrix. |
| Segmentation Assurance Analyst | Approve evidence quality and independently challenge the release. | Executed SC/AC/DT checks, three UAT tasks and rerun. |

## Business questions tied to outputs

1. Can the sponsor use **Annual category-spend profile** to support the stated decision, with this evidence: 440 row-keyed customer profiles with six category spends, total, shares, Channel/Region and zero/invalid flags.
2. Can the sponsor use **Segmentation comparison and stability report** to support the stated decision, with this evidence: Channel baseline, k=2…6 log-scaled clustering, silhouette, 50-bootstrap adjusted Rand stability and raw-vs-log sensitivity; segment sizes and spend profiles.
3. Can the sponsor use **Account opportunity register and propositions** to support the stated decision, with this evidence: Up to ten below-segment-median category-share/above-median-total cases plus exactly three service propositions, or documented deferrals.
4. Can the sponsor use **Account strategy dashboard** to support the stated decision, with this evidence: Segment profile, channel/region context, stability and candidate register views.
5. Can the sponsor use **Sales adoption and validation plan** to support the stated decision, with this evidence: Three proposition cards with audience, service change, account-owner role, discovery questions, pilot comparator and success/guardrail measures.

## Concrete outputs and required success

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Annual category-spend profile | 440 row-keyed customer profiles with six category spends, total, shares, Channel/Region and zero/invalid flags. |
| D6 | Segmentation comparison and stability report | Channel baseline, k=2…6 log-scaled clustering, silhouette, 50-bootstrap adjusted Rand stability and raw-vs-log sensitivity; segment sizes and spend profiles. |
| D7 | Account opportunity register and propositions | Up to ten below-segment-median category-share/above-median-total cases plus exactly three service propositions, or documented deferrals. |
| D8 | Account strategy dashboard | Segment profile, channel/region context, stability and candidate register views. |
| D11 | Sales adoption and validation plan | Three proposition cards with audience, service change, account-owner role, discovery questions, pilot comparator and success/guardrail measures. |

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Annual category-spend profile | Totals equal sum of six categories; positive-total shares sum to 1 within 1e−9; monetary units are not relabelled GBP; zero totals yield unavailable shares. |
| SC2 | D6 — Segmentation comparison and stability report | Channel/Region/row IDs excluded from distance; label permutations aligned; select or reject segmentation with explicit stability/interpretability evidence, not silhouette alone. |
| SC3 | D7 — Account opportunity register and propositions | Every case includes row ID, segment, category share, comparator, total spend, account-manager question and owner; no predicted growth, churn or confirmed cross-sell demand. |
| SC4 | D8 — Account strategy dashboard | Reviewer explains one segment in ordinary sales terms, traces a candidate to its six spend values and identifies an unstable/deferred case. |
| SC5 | D11 — Sales adoption and validation plan | Each card names evidence needed from account conversations and future transactions; no growth claim from a single annual snapshot. |

## Benefit and adoption boundary

Assessment success means the required outputs are correct, reproducible and usable in the specified review. It does not mean a model must win, a customer must buy, a fault must disappear or a security incident must be prevented. The executive pack must name the measured baseline, alternative, operating trade-off, recommendation and evidence still required for a real pilot. Do not invent commercial savings or success percentages to make the business case appear complete.

At G1 record simulated sponsor approval of the requirements and criteria. At G3 record the policy recommendation and unresolved evidence gaps. At G4 record an actual team reviewer and simulated sponsor role separately; template text is not an approval.

## Source and scope limits

All 440 original records; no invented transaction dates, business names or recurring customer history. Keep Channel and Region for profiling, not clustering.

Spend is annual monetary units, not verified GBP, margin or growth. No time series, retention outcome, product-level baskets or sales-response labels exist. Proposed cross-sell actions require account-manager confirmation.

**Failure to prevent:** Treating mathematically separated clusters as stable business needs or claimed growth forecasts would overstate the evidence.

Missing mandatory support blocks dependent acceptance until an explicit source/scope decision updates the affected deliverables and tests.

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
