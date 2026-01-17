# Analytics Project Brief

**Project Name:** SoundWave Strategy Recomendation **Date:** 13.01.2026

**Prepared by:** Alina Imanakhunova

---

## 1. Problem & Decision

**What business question or decision will this analysis inform?**

SoundWave is facing a strategic inflection point: its top podcasters has 15% of annual churn, free tier users are not converting to paid one, and middle podcasters have highest LTV but only 8% of podcasts. So the question is: Should comapny prioritize building product features for middle segment creators (1k–10k downloads per episode) or invest on scaling the ad marketplace driven primarily by top creators (10k+  downloads per episode)? The analysis will serve as the basis for making investment allocation decisions that will help eliminate troubling patterns that the company has encountered.

**Who is asking, and why now?**

The business question was raised by The Board of Directors, prompted by increasing market consolidation (Spotify/Apple exclusives) and other troubling patterns that company faced with.

**Who is the ultimate decision maker?**

The ultimate decision maker is The Board of Directors, advised by CEO Maya Rodriguez. 

**Hypothesis**

We believe that investing in the retention and growth of middle segment creators are highly profitable and will mitigate SoundWave’s current troubling patterns, because this segment has the highest LTV with lower churn rate. In contrast, churn among top creators is high and inevitable, as largely driven by external market forces.

---

## 2. Metrics

**Primary Metric**

| Metric name | Definition | Baseline | Target |
|-------------|------------|----------|--------|
|LTV:CAC Ratio by Creator Segment| 12-month projected creator LTV (subscription + ad revenue share) divided by estimated acquisition and enablement cost per creator, segmented by average downloads per episode (1k–10k vs 10k+) | Unknown | Validate whether mid creators achieve LTV:CAC ≥3.0x and at least 1.3× higher than top creators, under conservative CAC assumptions|

**Counter-Metrics** 

| Counter-metric | Type | Why it could break | How we'll measure |
|----------------|------|-------------------|-------------------|
| 1. Total ad marketplace revenue | Tradeoff |Shifting focus away from top creators could reduce near-term ad revenue concentration |Calculating ad revenue on monthly basis|
| 2. Platform growth rate (new creators) | Tradeoff |Focusing on retention may slow new creator acquisition| Monthly new creators count |
| 3. Top creator churn| Guardrail |Strategy should not accelerate top creator churn |Annual churn for 10,000+ segment|

---

## 3. Stakeholder Map

| | High Interest | Low Interest |
|---|---|---|
| **High Power** | Board of Directors, Maya Rodriguez (CEO), Kevin Liu (VP Product), | External Investors |
| **Low Power** | Diana Chen (Head of Sales), Creator Community Team| Platform developers |

**Champions:**
Maya Rodriguez (CEO)- needs validation of strategic thesis
Kevin Liu (VP Product) - implementation roadmap depends on findings

**Blockers:**
Diana Chen (Head of Sales) - believes top 500 podcasts drive ~80% of value. Ad Marketplace Specialist - if analysis shows that LTV:CAC ratio is driven by mid creators rather than top podcasts, the current ad-marketplace-led strategy loses priority.

**If >2 blockers, what's your strategy?**
In case of more then 2 blockers, we can use persuasion strategy. Align findings with blockers’ incentives by explicitly showing how the recommended strategy protects or expands their KPIs, rather than threatening them. Show for the blockers like Diana that 
mid creators = are future supply for ad marketplace, without them the advertising pipeline collapses.

---

## 4. Methodology

| Method | Hypothesis being tested | Data required |
|--------|------------------------|---------------|
| 1. Cohort-based LTV modeling by creator segment| Do mid-tier creators (1k–10k downloads/episode) generate higher LTV:CAC ratio over 12-month than top creators? |Creator subscription history (tier, tier_start_date), churn_date, podcast_id, average downloads per episode, ad campaign revenue|
| 2. Retention & churn driver analysis| Is churn among top creators primarily driven by scale-related external factors rather than low product engagement, while mid-tier retention is meaningfully influenced by feature usage? |churn_date, average downloads per episode, download growth over time, features_used, time_in_dashboard|
| 3. Expansion (monetization & upgrade) analysis| Do Mid creators have the highest likelihood of revenue expansion on the platform, including upgrading to Pro tier and adopting monetization tools, suggesting that investment in creator tools will yield higher incremental revenue than focusing solely on top-creator ad monetization? |Tier change history, ad campaign revenue, features_used, time_in_dashboard, average downloads per episode|


**Data Availability**

| Data needed | Available? | If no, fallback |
|-------------|-----------|-----------------|
| creator_id| Yes |-|
| tier, tier_start_date| Yes| - |
| churn_date| Yes |-|
| podcast_id| Yes  |-|
| average downloads per episode| Partial  |Derived from episode downloads|
| ad revenue| Yes |-|
| creator support cost| No |Exclude from LTV; treat as limitation|
| download growth rate| Partial |Derived over time|
| features_used| Yes |-|
| time_in_dashboard| Yes | -|
| episodes_published| Yes | -|

**Data Validity Checks (Stop/Go)**

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
- Clear, comparable 12-months LTV:CAC ratio estimates by creator segment, with <20% confidence interval
- Identified primary drivers of churn for large creators
- Quantified expansion potential of middle class creators

**Business Success** 
- Board consensus on strategic focus (mid creators vs top creators)
- Clear investment direction for next 6 months

**Decision Forum:** Board Strategy Review meeting (will be in a 8 weeks) **Action Owner:** СEO (Maya Rodriguez)

**Decision Criteria**

| If we find... | We will... |
|---------------|------------|
|Mid creators have LTV:CAC ≥3.0x and at least 1.3× higher than top creators, and show ≥10 pp lower annual churn than top creators|Prioritize investment in creator tools and retention, approve Kevin’s 6-month roadmap focused on growth, monetization, and collaboration features |
|Annual churn among top creators is ≥15% and shows weak or no correlation (<0.2) with product feature usage, but strong correlation with scale indicators (download growth, size)|Reduce investment in preventing top-creator churn, treat it as largely structural “graduation”, and hedge revenue risk by strengthening the mid creator pipeline|
| Mid creators show the highest expansion probability (≥2× higher Creator→Pro upgrade rate than top segment and/or ≥20% higher likelihood of adopting monetization tools) |Allocate incremental resources to creator tools, positioning mid creators as the primary source of future revenue growth|

**Action Thresholds** 

- We will only recommend action if: Mid creators have LTV:CAC ≥3.0x and at least 1.3× higher than top creators
- We will not act if:cohorts are <12 months old (insufficient LTV data)

---

## 7. Timeline

| Milestone | Date |
|-----------|------|
| Data access secured | Week 1 |
| LTV modeling | Week 2–3 |
| Retention & churn driver analysis | Week 4 |
| Expansion analysis | Week 5 |
| Initial findings review |Week 6|
| Preparation of delivarabels |Week 7|
| Board presentation |Week 8 |

---

## 8. Risks & Assumptions

**Key Assumptions**
- Historical retention predicts future behavior
- Churn events reflect true creator exit, rather than temporary inactivity or publishing pauses.

**Data Quality Assumptions**
- Episode download counts are consistently recorded across time
- Tier change events (Creator → Pro) are fully captured and timestamped correctly
- Ad campaign revenue attribution is directionally accurate at the podcast level
- Analytics usage logs capture the majority of meaningful creator interactions with the platform

**Risks**

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
|LTV overestimation |  M  | H |Sensitivity analysis|
|Misclassification of creators | M| M | Acknowledge uncertainty, show ranges |
|Mid creators fail to scale monetization| M| H | Failure analysis |

---

## 9. Ethics & Privacy

| | Yes | No | Notes |
|---|---|---|---|
| Requires PII? | [+] | [ ] | Creator-level internal data, for analysis will anonymized|
| Risk of bias against protected groups? | [ ] | [+] |No protected groups used |
| GDPR / Privacy compliance reviewed? | [+] | [ ] |Using existing consented data |

Mitigation: All outputs should be aggregated to segment level; No individual creator should be identified in board materials.

---

## 10. Pre-Mortem

Three months after approval, revenue declined due to slower-than-expected monetization among mid creators and higher ad revenue concentration among top podcasts. The analysis underestimated advertiser preference concentration. A phased rollout with explicit revenue guardrails and pilot testing would have reduced downside risk.
Perhaps, it would be worth considering and investigating Diana's investment plan.

---

"Your job is never to optimize a metric; it's to improve the experience that the metric measures."
