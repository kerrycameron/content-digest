# AI in Support, Part 2: Choose the Right Use Cases Before You Train Anyone

**Source:** https://1fernandoduarte.substack.com/p/ai-in-support-part-2-choose-the-right
**Date:** November 24, 2025
**Category:** 1. AI in Customer Support
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- Start with the right problems, not the shiny tool — implementation success depends on selecting appropriate use cases before deploying AI
- Use a three-factor scorecard (impact, effort, risk) to select Wave 1 candidates: high impact, low-to-medium effort, low-to-medium risk
- "If your senior agents debate the right answer, do not send that to AI first" — judgment-dependent decisions belong in later waves
- Every use case needs a narrative story defining trigger phrases, data sources, operational rules, human escalation thresholds, and success metrics
- Establish baseline metrics (volume, handle time, escalation rate, recontact rate, CSAT) before launch — they make evaluation objective rather than intuitive

## Frameworks / Models

### AI Use Case Ladder (Five Levels)

| Level | Type | Complexity |
|-------|------|-----------|
| 1 | Simple factual answers (eligibility, deadlines, document requirements, password resets) | Lowest risk |
| 2 | Guided checklists (preparation steps, document requirements, pre-appointment reviews) | Low risk |
| 3 | Status inquiries (application tracking, document receipt, payout status) | Low risk |
| 4 | Triage and routing (question assessment, queue assignment, self-service vs. escalation) | Medium |
| 5 | Agent assist — behind the scenes (suggested replies, policy highlights, account summaries) | Medium |

### Impact / Effort / Risk Scorecard

**Impact indicators:** Contact volume, average handle time, escalation rates, customer/agent pain points

**Effort indicators:** Knowledge content quality, system integration requirements, policy clarity, product change needs

**Risk indicators:** Consequence of incorrect answers, regulatory/privacy exposure, emotional impact on customers

### Use Case Story Template

For each Wave 1 use case, document:
- **Trigger phrases** that activate the flow
- **Required data sources** (systems, knowledge base articles)
- **Operational rules** governing the AI's scope
- **Human escalation thresholds** (what triggers handoff)
- **Success metrics** (containment rate, handle time, recontact rate)

### Metrics Framework

| Metric | Purpose |
|--------|---------|
| Weekly contact volume | Baseline for containment measurement |
| Average handle time | Efficiency impact signal |
| Escalation rate | Quality and scope signal |
| 7-day recontact rate | Resolution completeness |
| CSAT / thumbs rating | Customer experience signal |

### Team Validation Checklist

Four pressure-test questions per use case:
1. Do we agree on correct answers in most scenarios?
2. Are policies documented in plain language?
3. Do we know which systems hold required data?
4. What triggers human takeover?

Red flag: Extended debate over edge cases = defer to a later wave.

## Guardrails & Anti-patterns
- **Anti-pattern:** Starting from "What does our vendor offer?" rather than customer pain points
- **Guardrail:** Extract contact drivers from actual ticket data, search terms, and voice transcripts before evaluating vendor capabilities
- **Anti-pattern:** Attempting complex judgment calls — money complaints, denials, refunds — in Wave 1
- **Guardrail:** Reserve high-emotion and judgment-dependent scenarios for later waves after team and system trust is established
- **Anti-pattern:** Launching without documented baseline metrics
- **Guardrail:** Write down baselines before launch; post-launch comparisons without baselines produce opinions, not evidence
- **Anti-pattern:** Skipping frontline validation of use case suitability
- **Guardrail:** Have senior agents pressure-test every Wave 1 use case before training begins
