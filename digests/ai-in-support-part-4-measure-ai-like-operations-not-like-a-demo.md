# AI in Support, Part 4: Measure AI Like Operations, Not Like a Demo

**Source:** https://1fernandoduarte.substack.com/p/ai-in-support-part-4-measure-ai-like
**Date:** December 8, 2025
**Category:** 1. AI in Customer Support
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- Treat AI as operational infrastructure requiring rigorous measurement — avoid vague "big improvements" claims by tracking use-case-level metrics tied to real decisions
- Set baselines before launch for every use case; post-launch comparisons without baselines produce opinions, not evidence
- The four-pillar framework (Volume & Containment, Quality & Satisfaction, Efficiency, Risk & Incidents) gives a complete operational picture per flow
- Every metric review must produce an action: expand, improve, or retire — analysis divorced from decisions has no value
- Aggregate AI metrics hide problem flows; disaggregated, per-use-case tracking enables targeted intervention

## Frameworks / Models

### Four-Pillar Metric Framework

**Pillar 1: Volume and Containment**
- Contacts in scope (conversations triggering the AI flow)
- Containment rate (% completed in AI without handoff)
- Handoff rate (% routed to humans)
- Abandon rate (% where customer exits without resolution)

*Example: "1,200 conversations handled; 54% containment, 36% handoff, 10% drop"*

**Pillar 2: Quality and Satisfaction**
- CSAT by channel/flow (compare AI vs. human-handled same-topic conversations)
- Thumb ratings (bot reply satisfaction signals)
- Recontact rate (customers returning within 7 days for same issue)
- Reopen rate (issues resurging after AI-assisted replies)

*Example: "CSAT 4.5/5 (human-parity); recontact down from 12% to 8%"*

**Pillar 3: Efficiency**
- Handle time (AI-assisted vs. non-assisted)
- Time to first response (for AI-drafted initial touches awaiting agent review)
- Queue backlog and SLA behavior post-rollout

*Example: "Password reset handle time: 6 min → 3.5 min; queue backlog -22%"*

**Pillar 4: Risk and Incidents**
- AI incident count (wrong, harmful, or policy-violating answers)
- Severity classification: Low (minor confusion resolved same contact) / Medium (customer inconvenience) / High (financial, privacy, or brand risk)
- Time to mitigation (detection-to-fix cycle)
- Failure source tags (outdated policy, missing articles, wrong routing, hallucinations)

*Example: "9 incidents/month: 7 low (policy), 2 medium (wording), 0 high"*

### Review Cadence

| Cadence | Audience | Focus |
|---------|----------|-------|
| Weekly (30 min) | Support leadership, operations, AI owner | Top metrics per use case, incident spikes, agent/QA feedback, next-week decisions |
| Monthly/Quarterly (60 min) | Leadership, product, operations, executives | Trends, expand/hold/retire decisions, investment priorities, brand/risk patterns |

### Metric-to-Action Decision Rules

| Metric Signal | Action |
|---------------|--------|
| Low containment + high handoff | Review entry questions, intent mapping, routing rules |
| High recontact rate | Sample conversations; fix confusing answers, missing steps |
| No handle-time improvement on AI-assisted tickets | Watch screen recordings — agents may be editing errors instead of saving time |
| Incidents cluster in one policy area | Freeze automation; update content/prompts; retest before relaunch |

## Guardrails & Anti-patterns
- **Anti-pattern:** Aggregating all AI performance into a single KPI — hides underperforming flows
- **Guardrail:** Track metrics at the individual use-case level; isolate which flows work and which need intervention
- **Anti-pattern:** Launching without documented baseline metrics and then claiming credit for improvement
- **Guardrail:** Write baselines down before launch; memory is not a valid measurement tool
- **Anti-pattern:** Building dashboards with no scheduled review audience
- **Guardrail:** Set metrics and fix the review schedule simultaneously; measurement without a decision cadence is theater
- **Anti-pattern:** Accepting vendor performance claims without cross-referencing internal data
- **Guardrail:** Run your own use-case-level tracking; vendor benchmarks don't reflect your customers, policies, or workflows
