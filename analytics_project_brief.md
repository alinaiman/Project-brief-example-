# Analytics Project Brief

**Project Name:** SoundWave Strategy Recomendation **Date:** 13.01.2026

**Prepared by:** Alina Imanakhunova

---

## 1. Problem & Decision

**What business question or decision will this analysis inform?**

The core business question that SoundWave company faced with: Should comapny prioritize building product features for mid-tier podcast creators (1,000–10,000 downloads per episode) or invest on scaling the ad marketplace driven primarily by top creators (more then 10,000  downloads per episode)? The analysis will serve as the basis for making investment allocation decisions that will help eliminate troubling patterns that the company has encountered.

**Who is asking, and why now?**

The business question was raised by The Board of Directors, prompted by increasing market consolidation (Spotify/Apple exclusives) and rising churn among large podcasts.

**Who is the ultimate decision maker?**

The ultimate decision maker is The Board of Directors, advised by CEO Maya Rodriguez. The Board of Directors expect presentation in 8 weeks, where data-driven decision and strategy must be defined.  

**Hypothesis**

We believe that investing in the retention and growth of “middle class” creators will mitigate SoundWave’s current troubling patterns, because this segment combines the highest lifetime value with lower churn while accounting for only 8% of active podcasts today. And churn among top creators is largely driven by external market forces rather than internal product deficiencies.

---

## 2. Metrics

**Primary Metric**

| Metric name | Definition | Baseline | Target |
|-------------|------------|----------|--------|
|Creator LTV by Segment| Net revenue per creator over 12 months (subscriptions + ad revenue share – estimated support cost), segmented by downloads (1,000-10,000 and 10,000+ ), excluding creators with <1,000 downloads | The "middle class"  has highest LTV, but we don't know the exact number  | Validate “middle class” segment ≥30% higher LTV than large creators|

**Counter-Metrics** _(2-3 max — what breaks if we optimize the primary metric?)_

| Counter-metric | Type | Why it could break | How we'll measure |
|----------------|------|-------------------|-------------------|
| 1. Total ad marketplace revenue | Tradeoff |As the company will focus more on "middle class" it will reduce revenue from top podcasts, which by now drive 80% of value (by beliefs of Head of sales) |Calculating ad revenue on monthly basis|
| 2. Platform growth rate (new creators) | Tradeoff |As the company will focus on "middle class" segment it may slow acquisition of new creators| Monthly new creators count |
| 3. Top creator churn| Guardrail |Strategy should not accelerate large-creator churn |Annual churn for 10,000+ segment|

---

## 3. Stakeholder Map

| | High Interest | Low Interest |
|---|---|---|
| **High Power** | Board of Directors, Maya Rodriguez (CEO), Kevin Liu (VP Product), | External Investors |
| **Low Power** | Diana Chen (Head of Sales), Creator Community Team| Platform developers |

**Champions:**
Maya Rodriguez (CEO)
Kevin Liu (VP Product)

**Blockers:**
Diana Chen (Head of Sales)

**If >2 blockers, what's your strategy?**
In case of more then 2 blockers, we can use persuasion strategy. Align findings with blockers’ incentives by explicitly showing how the recommended strategy protects or expands their KPIs, rather than threatening them. Show for the blockers like Diana that 
"middle class" creators = are future supply for ad marketplace, without them the advertising pipeline collapses.

---

## 4. Methodology

| Method | Hypothesis being tested | Data required |
|--------|------------------------|---------------|
| 1. Cohort-based LTV modeling|Middle class” creators generate the highest 12-month LTV per creator, once churn, subscription revenue, and ad marketplace revenue are jointly accounted for. This would indicate that mid creators—not top creators—represent SoundWave’s highest long-term value segment. |creator_id , tier, churn_date, podcast_id , average downloads per episode, ad revenue , creator support cost|
| 2. Retention and retention driver analysis| Higher churn among top creators is primarily driven by external scale-related factors rather than low product engagement, indicating that a significant portion of top creator churn is structurally inevitable , while mid creator's retention is meaningfully influenced by product usage and feature adoption. |creator_id, churn_date , average downloads per episode ,download growth rate , features_used  ,time_in_dashboard ,episodes_published |
| 3. Expansion analysis| Mid creators have the highest likelihood of revenue expansion on the platform, including upgrading to Pro tier and adopting monetization tools, suggesting that investment in creator tools will yield higher incremental revenue than focusing solely on top-creator ad monetization.|creator_id tier, tier_start_date , average downloads per episode ,features_used ,ad revenue ,time_in_dashboard |


**Data Availability**

| Data needed | Available? | If no, fallback |
|-------------|-----------|-----------------|
| creator_id| Yes |-|
| tier| Yes| - |
| churn_date| Yes |-|
| podcast_id| Yes  |-|
| average downloads per episode| Partial  |can be calculated by averaging the number of downloads|
| ad revenue| Yes |-|
| creator support cost| No | ask to provide with this info Client Support Manager, if we don't receive an answer drop this variable|
| download growth rate| Partial |can be calculated using the number of downloads and period |
| features_used| Yes |-|
| time_in_dashboard| Yes | -|
| episodes_published| Yes | -|
| tier_start_date| Yes|-|

**Data Validity Checks (Stop/Go)**

_What must be true before analysis proceeds? List checks to validate before drawing conclusions._

| Check | How to validate | Stop if... |
|-------|-----------------|------------|
|Segment definition stability |Recompute download bands monthly | >15% creators switch segments due to noise|
|Churn date accuracy | Compare churn_date with last activity | >10% mismatch |
|Ad revenue consistency |Reconcile campaign revenue totals |>15% unexplained variance |

---

## 5. Scope & Deliverables

**In Scope**
- Paid creators (Creator and Pro tiers)
- Download-based creator segments (<1k, 1k–10k, 10k+)
- Retention, churn, and expansion behavior over 12 months

**Out of Scope** _(what won't you do, but someone might assume you will?)_
- Free-tier–only creators
- External platform (Spotify / Apple) data

**Final Deliverables**

- [+] Board-ready slide deck (strategy + evidence)
- [+] Written report
- [+] Dashboard (PowerBI)
- [+] Reproducible analysis notebook

---

## 6. Success & Decision Criteria

**Analytical Success** 
- Clear, comparable 12-months LTV estimates by creator segment
- Identified primary drivers of churn for large creators
- Quantified expansion potential of middle class creators

**Business Success** 
- Board consensus on strategic focus (mid creators vs top creators)
- Clear investment direction for next 6 months

**Decision Forum:** Board Strategy Review meeting  **Action Owner:** СEO (Maya Rodriguez)

**Decision Criteria**

| If we find... | We will... |
|---------------|------------|
|Mid creators have ≥25–30% higher 12-months LTV per creator than both small and top creators, and show ≥10 pp lower annual churn than top creators|Prioritize investment in creator tools and retention, approve Kevin’s 6-month roadmap focused on growth, monetization, and collaboration features |
|Annual churn among top creators is ≥15% and shows weak or no correlation (<0.2) with product feature usage, but strong correlation with scale indicators (download growth, size)|Reduce investment in preventing top-creator churn, treat it as largely structural “graduation”, and hedge revenue risk by strengthening the mid-tier pipeline|
| Mid creators show the highest expansion probability (≥2× higher Creator→Pro upgrade rate than other segments and/or ≥20% higher likelihood of adopting monetization tools) |Allocate incremental resources to creator tools, positioning mid-tier creators as the primary source of future revenue growth|

**Action Thresholds** 

- We will only recommend action if: LTV differences between segments are ≥25%, or Retention or expansion effects are directionally consistent across cohorts
- We will not act if: Segment-level LTV differences are <15%, or Observed effects disappear under conservative churn assumptions

---

## 7. Timeline

| Milestone | Date |
|-----------|------|
| Data access secured | Week 1 |
| LTV modeling | Week 2–3 |
| Retention & churn driver analysis | Week 4 |
| Expansion analysis | Week 5 |
| Initial findings review |Week 6|
| Board presentation |Week 7 |

---

## 8. Risks & Assumptions

**Key Assumptions**
1. Historical retention predicts future behavior
2. Download count is a reasonable proxy for creator maturity

**Data Quality Assumptions**
- Completion rate noise does not bias relative comparisons

**Risks**

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
|LTV overestimation |  M  | H |Sensitivity analysis|
|Misclassification of creators | M| M | Sensitivity analysis |
|Sales pushback | H| M | Sensitivity analysis |


---

## 9. Ethics & Privacy

| | Yes | No | Notes |
|---|---|---|---|
| Requires PII? | [+] | [ ] | Creator-level internal data|
| Risk of bias against protected groups? | [ ] | [+] |No protected attributes used |
| GDPR / Privacy compliance reviewed? | [+] | [ ] |Internal-only analysis |

Mitigation: All outputs should be aggregated; No individual creator should be identified in board materials.

---

## 10. Pre-Mortem

Three months after the board approved increased investment in mid-tier creators, overall revenue declined. The analysis underestimated how concentrated advertiser demand was among top podcasts, and mid-tier monetization ramped more slowly than expected. A phased rollout with explicit revenue guardrails could have reduced downside risk. 
Perhaps, it would be worth considering and investigating Diana's investment plan.

---

"Your job is never to optimize a metric; it's to improve the experience that the metric measures."
