# AI Ops, Part 8: The AI Release Train

**Source:** https://1fernandoduarte.substack.com/p/ai-ops-for-support-leaders-part-8
**Date:** February 24, 2026
**Category:** 1. AI in Customer Support
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- AI changes drift without a schedule because words function like product behavior, retrieval like a data pipeline, and routing like org design—small edits across any layer reshape customer outcomes
- Every customer-facing AI change qualifies as a release: prompts, knowledge edits, retrieval rules, routing logic, escalation triggers, model settings, safety filters, agent assist macros
- Three risk-based tracks control cadence: Track A (routine, weekly), Track B (controlled, bi-weekly), Track C (gated, monthly + emergency path); identity, money movement, eligibility, and compliance default to Track C
- "No release ticket, no change" — each ticket requires exact before/after text, a rollback plan, test pass/fail criteria, and three post-ship metrics to monitor
- Emergency fixes are allowed but require a paper trail: log within 24 hours, add test coverage within 48 hours, share postmortem at next weekly review

## Frameworks / Models

### Three-Track Release Model
| Track | Risk Tier | Cadence | Approver |
|-------|-----------|---------|----------|
| A – Routine | Tier 0–1 | Weekly | One operational approver |
| B – Controlled | Tier 2 | Bi-weekly | Support leader + policy partner |
| C – Gated | Tier 3 | Monthly + emergency path | Executive sponsor |

### Weekly Release Train Schedule
- **Monday:** Triage intake, reject vague requests, assign owners, set track
- **Tuesday:** Build changes, update test coverage
- **Wednesday:** Run tests, review promise language and policy risk
- **Thursday:** Write release notes, prepare rollback steps, set monitoring
- **Friday:** Ship Track A; hold Track B and C for planned windows

### Go/No-Go Gate
Release ticket complete · Source of truth verified · Test suite passed · Rollback steps written · Monitoring ready · Release notes drafted · Approvals logged

## Guardrails & Anti-patterns
- **Anti-pattern:** Making prompt or knowledge edits outside a release cadence—"quick tweaks" obscure metric trends and accumulate trust debt through escalations, coaching time, and incident management
- **Guardrail:** Route all customer-facing AI changes through one intake path, one backlog, one approval flow, one changelog, and one rollback plan; when any go/no-go line fails, move the change to the next train
