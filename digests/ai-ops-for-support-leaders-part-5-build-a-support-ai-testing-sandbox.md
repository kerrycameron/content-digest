# AI Ops For Support Leaders, Part 5: Build a Support AI Testing Sandbox

**Source:** https://1fernandoduarte.substack.com/p/ai-ops-for-support-leaders-part-5
**Date:** February 3, 2026
**Category:** 1. AI in Customer Support
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- "Most teams ship AI changes straight to production. Then customers run the first real test." — a sandbox is the cheapest insurance a support org buys, and it also speeds up shipping
- A sandbox has three components: a gold set of real tagged cases, scoring rules with clear pass/fail/partial criteria and severity levels, and launch gates with rollback procedures
- Build the gold set from real customer scenarios stratified by risk tier — teams consistently under-test Tier 2/3 scenarios where actual harm occurs
- Vague expected outputs ("good answer") aren't testable; specify outcomes and required actions for every gold set case
- Practice rollback procedures quarterly — rollback only works when rehearsed; an untested rollback plan is no plan at all

## Frameworks / Models

### Three-Component Sandbox

- **Test Cases**: Real customer scenarios labeled by intent, channel, and risk tier
- **Scoring Rules**: Clear pass/fail/partial criteria with severity levels attached to failures
- **Gates & Rollback**: Launch prerequisites and fast reversal mechanisms

### Gold Set Build Guidelines

**Target Size Progression:**
- Start: 50 cases
- Stable: 100–200 cases
- Mature: 300–500 cases per product area

**Minimum Cases by Risk Tier:**

| Risk Tier | Minimum Cases |
|-----------|---------------|
| Tier 0 | 10 |
| Tier 1 | 20 |
| Tier 2 | 15 |
| Tier 3 | 5 |

**Required Labels per Case:** Intent · Channel · Risk Tier

**Composition Rules:** Cover top intents by volume · Cover top intents by risk · Include edge cases from escalations · Address recent incidents and defects · Reflect new feature releases and policy updates

### Scoring & Severity System

**Three-Level Scoring:** Pass · Partial · Fail

**Severity Ratings on Failures:**
- Severity 1: Wrong tone, minor confusion, no harm
- Severity 2: Wrong answer, recontact likely
- Severity 3: Unsafe — privacy, money, or irreversibility risk

**Scoring Dimensions:** Correct outcome · Correct verification · Correct routing · Safe response boundaries · Correct operational actions

### Pass/Fail Launch Gates

| Tier | Gate |
|------|------|
| Tier 3 | Zero Severity 3 failures; zero outcome failures |
| Tier 2 | Zero Severity 3 failures; 95%+ pass rate |
| Tier 1 | 90%+ pass rate; <10% partial rate |
| Tier 0 | 85%+ pass rate; partials allowed |
| Global | No increase in known defect types; new defects require owner and fix path |

### Change-Level Gate Rules

| Change Type | Scope | Gate |
|------------|-------|------|
| Small (prompt edits, single article) | Impacted intents only | Run subset for affected intents |
| Medium (routing, intent split, model change) | Multiple intents | Run full gold set |
| Large (new channels, automations, product launch) | System-wide | Full gold set + 48-hour launch monitoring |

### Rollback Procedures (by Component)

| Component | Rollback Mechanism |
|-----------|--------------------|
| Prompt | Store versioned copies with timestamp and owner; one-click or one-PR revert |
| Knowledge | Restore previous article revision; disable from retrieval index; flag for freshness review |
| Routing | Revert triggers/workflow changes; restore previous queue logic; turn off new automation paths |
| Feature | Switch to handoff-only mode; disable auto-actions; disable outbound messaging |

Practice rollback procedures **quarterly**.

### Six-Step Release Process Workflow

1. Propose change (description, impacted intents, risk exposure, owner)
2. Update test plan (identify applicable gold set cases; define expected outcome updates)
3. Run tests (execute sandbox; score results; log defects)
4. Fix & retest (prioritize Severity 3; retest until gates pass)
5. Launch with monitoring (define 48-hour watch metrics; assign monitoring owner; set rollback thresholds)
6. Log release (one-line summary; change links; seven-day outcomes)

### Role & Ownership Model

| Role | Responsibility |
|------|---------------|
| **Sandbox Owner** | Maintains gold set; owns scoring rules; runs weekly test cycle |
| **Risk Owner** | Approves Tier 2/3 changes; owns verification rules; owns rollback decisions |
| **Knowledge Owner** | Owns sources of truth; owns freshness cadence; reviews retrieval failures |
| **Ops Owner** | Owns routing, fields, triggers, automations, deployment steps |

### 14-Day Build Plan

| Days | Task |
|------|------|
| 1–2 | Define 10–20 intents, risk tiers, pass criteria |
| 3–5 | Pull 50 real cases; tag and write expected outputs |
| 6–7 | Define scoring rules, severity levels, launch gates |
| 8–10 | Test current production; log failures; fix Severity 3 |
| 11–12 | Build rollback runbook (prompt, knowledge, routing, feature) |
| 13 | Rehearse one change end-to-end; measure friction points |
| 14 | Publish first release log with learnings |

## Guardrails & Anti-patterns
- **Anti-pattern:** Over-testing Tier 0/1 scenarios while under-representing Tier 2/3 in the gold set
- **Guardrail:** Enforce minimum case counts by risk tier from day one — harm hides in the cases you didn't test
- **Anti-pattern:** Documenting expected outputs as "good answer" or "correct response"
- **Guardrail:** Specify expected outcomes as observable actions — approve/deny/escalate/route — with required verification steps and response boundaries
- **Anti-pattern:** Treating severity errors equally regardless of risk (wrong reset logic = punctuation error)
- **Guardrail:** Apply severity tiers to all failures; Severity 3 (unsafe) failures are blockers regardless of pass rate on other dimensions
- **Anti-pattern:** Building rollback procedures that have never been practiced
- **Guardrail:** Rehearse rollback procedures quarterly; an untested rollback plan fails under the stress of a real incident
