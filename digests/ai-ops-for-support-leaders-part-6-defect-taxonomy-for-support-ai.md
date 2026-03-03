# AI Ops For Support Leaders, Part 6: Defect Taxonomy for Support AI

**Source:** https://1fernandoduarte.substack.com/p/ai-ops-for-support-leaders-part-6
**Date:** February 9, 2026
**Category:** 1. AI in Customer Support
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- "A defect taxonomy stops the arguing. Every failure becomes: A label. An owner. A standard fix path. A test to prove the fix worked."
- One failure, one primary label — every defect maps to one of six stable types; composite failures get the highest-risk primary label
- Route defects by owner group based on the fix path, not by who complained loudest — the taxonomy makes ownership automatic
- Add one new gold set test case for every S0 and S1 defect; treat same-subtype repeats within 14 days as regressions requiring escalated priority
- Track repeat rate by subtype as your leading indicator of systemic failure — volume alone misses structural problems hiding in distribution

## Frameworks / Models

### Six Defect Types + Subtypes

| Type | Definition | Subtypes |
|------|------------|---------|
| **WRONG ANSWER** | AI gave an answer conflicting with source of truth | Policy conflict · Stale content · Hallucinated rule · Math/eligibility error · Unsupported promise |
| **KNOWLEDGE GAP** | Right answer exists; retrieval or article failed | Missing article · Outdated article · Bad metadata · Retrieval miss · Answer in product but not in docs |
| **BAD SUMMARY** | Summary/internal note missed facts, swapped them, or leaked sensitive data | Missed next step · Wrong intent · Wrong names or IDs · Missing verification note fields · Sensitive data included |
| **BAD ESCALATION** | Flow escalated late, early, or to the wrong place | Escalation threshold wrong · No context in handoff · Wrong queue · Looping without progress |
| **BROKEN WORKFLOW STEP** | Automation, tool calls, forms, or routing rules failed | Tool failure · Routing rule failure · Form missing required field · Automation fired wrong macro · Channel handoff broke |
| **MISSING INTENT** | Conversation didn't map to taxonomy or mapped incorrectly | New topic · Multi-intent · Ambiguous request · Taxonomy too granular · Taxonomy too broad |

### Six Fix Paths & Owners

| Fix Path | Owner | Work |
|----------|-------|------|
| **A. Knowledge Fix** | Knowledge owner | Add/update articles, examples, edge cases, titles, metadata |
| **B. Prompt/Instruction Fix** | Support Ops | Update system prompt, agent patterns, constraints, formatting rules |
| **C. Policy & Guardrail Fix** | Support leadership + policy partner | Add exclusions, tighten thresholds, add verification steps, block unsafe actions |
| **D. Routing/Workflow Fix** | Support Ops + Engineering | Update routing logic, triggers, forms, tags, queue rules |
| **E. Tooling/Integration Fix** | Engineering or vendor | Fix tool calls, auth, missing fields, API limits |
| **F. Coaching Fix** | Team lead or QA | Train on capture, escalation, verification notes, defect reporting |

### Severity Guide

| Severity | Trigger |
|----------|---------|
| **S0** | Tier 3 risk OR legal/security/money movement issue |
| **S1** | Tier 2 risk OR large customer impact |
| **S2** | Tier 0–1 risk with repeat volume |
| **S3** | Cosmetic, rare, or low impact |

### Seven Rules for a Working Taxonomy

1. One failure, one primary label
2. Labels describe outcomes, not opinions
3. Every label maps to an owner group
4. Every label maps to a fix path
5. Every label has a severity tier
6. Every taxonomy change gets logged (or trend lines rot)
7. Every label maps to a test case in the gold set

### Weekly Triage Loop

**Agenda (once per week, same time, same people):**
1. Review new defects by severity
2. Merge duplicates
3. Assign owner group and due date
4. Choose fix type
5. Add test cases to gold set
6. Close loop with reporter

**Minimum Staffing:** Support Ops · QA · Knowledge owner · Engineering rep · Policy partner (for Tier 2 and 3)

### Regression Rule

If the same subtype returns within 14 days after a fix, reopen and escalate priority. This is a systemic failure, not a one-off.

### Core Operational Metrics

| Metric | Purpose |
|--------|---------|
| Defects per 1,000 AI conversations | Overall quality signal |
| Repeat rate by subtype | Leading indicator of systemic failure |
| Time to triage | Operational responsiveness |
| Time to fix | Fix velocity |
| Recontact rate after "resolved" | Resolution completeness |
| Escalation acceptance rate | Routing accuracy |
| Defect mix by risk tier | Risk distribution signal |

### Three Real-World Examples

**Example 1: WRONG ANSWER :: Policy conflict**
- Scenario: Bot says refunds post in 24 hours; policy says 5 business days
- Risk Tier: 2 · Fix Path: Policy/guardrail + knowledge · Test: Ask refund question three ways; expect 5-day answer + escalation criteria

**Example 2: BAD ESCALATION :: Looping without progress**
- Scenario: Bot asks for screenshots three times; user requests agent; bot repeats troubleshooting
- Risk Tier: 1 · Fix Path: Routing/workflow · Test: Detect "talk to agent" + "already tried"; escalate with context

**Example 3: KNOWLEDGE GAP :: Missing article**
- Scenario: New feature launches with no documentation; bot guesses
- Risk Tier: 0 · Fix Path: Knowledge · Test: Retrieval returns new article; answer includes link and next steps

### 30-Day Implementation Roadmap

| Week | Task |
|------|------|
| 1 | Pick six defect types; create intake form; define owner groups and SLAs |
| 2 | Train team on reporting; start weekly triage; ship one small fix |
| 3 | Build gold test set from real failures; add regression tracking |
| 4 | Publish monthly defect report (top subtypes, fixes shipped, open Tier 2–3 items, repeat offenders, drift signals) |

## Guardrails & Anti-patterns
- **Anti-pattern:** Routing defects based on who complained rather than what the defect type is
- **Guardrail:** Use the fix path mapping to auto-assign owner groups — defect type determines who owns the fix, not organizational politics
- **Anti-pattern:** Treating a fixed defect as closed without adding a regression test case to the gold set
- **Guardrail:** Every S0 and S1 fix requires a new gold set case before the ticket is closed; regression tracking starts from the first week
- **Anti-pattern:** Changing taxonomy labels or definitions without logging the change
- **Guardrail:** Log every taxonomy change with date, reason, and affected intents — silent changes destroy trend line integrity and make pattern detection impossible
- **Anti-pattern:** Closing a fixed defect when the same subtype reappears within 14 days without escalating
- **Guardrail:** Apply the regression rule: same subtype within 14 days = systemic failure; reopen and increase priority
