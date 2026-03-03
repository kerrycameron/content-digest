# AI Ops For Support Leaders, Part 1: Intent Data as a Product

**Source:** https://1fernandoduarte.substack.com/p/ai-ops-for-support-leaders-part-1
**Date:** January 5, 2026
**Category:** 1. AI in Customer Support; 6. Support Leadership
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- Treat intent classification as a critical product, not a reporting label — weak intent data cascades failures through routing, QA, knowledge management, and AI systems
- Every intent must trigger at least one action (route to queue, deliver macro, surface article, prompt AI workflow, initiate follow-up task) — intent without action should be deleted
- The three-layer model keeps governance clean: executive rollups (5–10 buckets) → operational intents (30–80) → diagnostic tags (unlimited, investigation-only) — mixing layers destroys clarity
- Document inclusions and exclusions with three examples each; skipping exclusions silently degrades classification accuracy over time
- "Your goal is not a perfect taxonomy. Your goal is stable decision-making." — govern for stability, not comprehensiveness

## Frameworks / Models

### Three-Layer Operating Model

| Layer | Count | Purpose |
|-------|-------|---------|
| **Executive Rollups** | 5–10 buckets | Leadership visibility only |
| **Operational Intents** | 30–80 intents | Routing, staffing, content decisions |
| **Diagnostic Tags** | Unlimited | Investigation only — never used for routing |

Mixing layers destroys clarity and control.

### Intent Naming Principles

| Poor Examples | Strong Examples |
|--------------|-----------------|
| "Billing Team Issue" | "Payment" |
| "Portal Bug" | "Refund Request" |
| "Needs Help" | "Login," "Password Reset" |
| "Tech Issue" | "Application," "Proof of Identity" |

Rule: Short names, actionable. Verbs for actions; nouns for objects. No internal team names.

### Intent Definition Template

```
Intent Name: [short, actionable]
Definition: [one sentence]
In Scope: [3 examples]
Out of Scope: [3 examples]
Primary Actions: [route/macro/article/workflow/task]
Owner: [Support Ops] | Approver: [Support Leadership] | Reviewer: [QA]
```

### Governance Roles

| Role | Responsibility |
|------|---------------|
| **Owner** | Writes definitions; owns outcomes |
| **Approver** | Signs off changes; protects stability |
| **Reviewer** | Audits quality and drift; flags risk |

### Change Control Framework

| Change Type | Notes |
|------------|-------|
| **Add** | New intent with definition and examples |
| **Split** | One intent → two; document split date and mapping |
| **Merge** | Two intents → one; document merge date and mapping |
| **Forbidden** | Silent definition edits — destroys trend line integrity |

### Operational Metrics

| Frequency | Metrics |
|-----------|---------|
| Weekly | Unclassified rate, misroute rate, reopen rate by intent, repeat contact rate by intent |
| Monthly | Intent drift (shifts week-to-week), intent sprawl (created vs. retired), coverage (% volume in top 30 intents) |

**Diagnostic rules:**
- Rising unclassified = taxonomy failing
- Rising misroute = definitions failing
- Rising repeats = knowledge/workflows failing

### 14-Day Implementation Timeline

| Days | Task |
|------|------|
| 1–2 | Pull and rank 6–12 weeks of ticket data |
| 3–5 | Draft 30–50 intents with definitions and exclusions |
| 6 | Assign owners; establish review cadence |
| 7–10 | Parallel processing with current labels (no cutover yet) |
| 11–14 | Audit unclassified/misroutes; refine definitions, training data, routing rules |
| Then | Execute cutover; preserve change log from day one |

## Guardrails & Anti-patterns
- **Anti-pattern:** Freeform labels — agents input anything, AI guesses anything, reporting becomes unreliable fiction
- **Guardrail:** Start with 30–50 controlled operational intents; require definitions, examples, and scope boundaries before an intent goes live
- **Anti-pattern:** Over-designed taxonomies with 200+ intents — nobody remembers them; "Other" category dominates weekly
- **Guardrail:** Start small and controlled; retire intents that don't generate specific actions; grow only with deliberate governance
- **Anti-pattern:** Silent definition edits that change what an intent means without logging the change
- **Guardrail:** Log every taxonomy change — date, type, affected intents, reason, owner, approver — to preserve trend line integrity
- **Anti-pattern:** Building AI features before establishing intent classification infrastructure
- **Guardrail:** "If you lead support, build your intent system before you buy your next AI feature." Intent quality precedes successful AI implementation
