# AI in Support, Part 6: Governance

**Source:** https://1fernandoduarte.substack.com/p/ai-in-support-part-6-governance
**Date:** December 22, 2025
**Category:** 1. AI in Customer Support; 6. Support Leadership
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- Governance prevents quality drift, policy decay, workaround proliferation, and agent distrust — the four compounding failure modes that follow unmanaged AI rollouts
- Every metric requires an assigned owner; unowned metrics should be deleted rather than tracked without accountability
- "Agents report issues. Owners fix systems." — the golden rule that separates functional governance from blame culture
- Change control requires three core elements: one change log (single source of truth), one release note (consistent communication), and one rollback path (recovery mechanism)
- Risk-tiered QA protects both customers and agents — uniform quality control is less effective than concentrating scrutiny on high-risk interactions

## Frameworks / Models

### Core Ownership Framework (Seven Roles)

| Role | Responsibilities |
|------|-----------------|
| **Support Ops Owner** | Workflows, routing, tags, reporting, release notes |
| **Knowledge Owner** | Accuracy, freshness, structure, policy-tied updates |
| **QA Owner** | Sampling, scoring, calibration, coaching themes |
| **Tool Owner** | Configuration, prompts, guardrails, integrations |
| **Engineering Partner** | Reliability, logging, permissions, data pipelines |
| **Support Leadership** | Risk acceptance, red zones, escalation paths, resourcing |
| **Frontline Leads** | Coaching, surfacing floor patterns |

### Decision Rights Matrix

| Change Type | Owner | Approver | Reviewer |
|---|---|---|---|
| Policy answer changes | Knowledge Owner | Policy partner/program owner | QA |
| Workflow changes | Support Ops Owner | Support leadership | Leads & QA |
| Prompt framework changes | Tool Owner | Support Ops | QA |
| Red zones & exclusions | Support leadership | Exec sponsor (high-risk) | QA & policy partner |
| Routing & escalation logic | Support Ops | Support leadership | Engineering |

### Risk-Tiered Quality Control

| Risk Level | Examples | QA Approach |
|-----------|---------|-------------|
| **Low** | Navigation help, status updates, simple clarifications | Light sampling; clarity and tone focus |
| **Medium** | Eligibility explanations, documentation guidance, multi-step workflows | Higher sampling; source verification required |
| **High** | Money movement, appeals, identity changes, legal exposure | AI excluded OR strict human verification + escalation rules |

### AI-Ready Knowledge Base Standards

- Clear, specific titles
- One task per article
- Short section lengths with examples and edge cases
- Last updated date visible
- Source links for all policy claims

### Knowledge Decay Triggers
Policy updates · State-specific exceptions · Seasonal deadlines · New forms or processes · Internal workflow changes

### Incident Response Playbook (Seven Steps)

1. Freeze the failing use case
2. Post stop-use message to team
3. Deploy workaround macro
4. Assign owner with next update timeline
5. Run targeted QA sweep
6. Ship fix with release note
7. Reopen only after validation

### 30-60-90 Day Implementation Plan

| Phase | Goal | Key Deliverables |
|-------|------|-----------------|
| Days 1–30: Stop the Drift | Halt quality erosion and clarify ownership | Ownership map, decision rights, change log, risk tiers, incident playbook, weekly release notes |
| Days 31–60: Normal Operations | Embed governance into standard workflows | Monthly QA calibration, knowledge gap feedback loop, metric owners, failure modes documented |
| Days 61–90: Scale Quality | Expand without losing stability | Quarterly risk review cadence, red zones refreshed, expansion checklist finalized |

## Guardrails & Anti-patterns
- **Anti-pattern:** Quality drift cascade — quality erodes → policy ages → workarounds spread → leads become cleanup crews → agents distrust the system
- **Guardrail:** Publish ownership map and decision rights before expanding scope; clear accountability prevents the drift spiral
- **Anti-pattern:** Making changes without a change log, making root cause analysis impossible when issues arise
- **Guardrail:** Every change gets a log entry — date, description, owner, reason, risk tier, impacted queues, validation plan, rollback plan
- **Anti-pattern:** Applying uniform QA intensity to all interactions regardless of risk
- **Guardrail:** Use risk-tiered QA — light sampling for low-risk, mandatory source verification for medium, AI exclusion or strict human review for high-risk; "No unsourced certainty"
- **Anti-pattern:** Leaving retired content accessible instead of removing it
- **Guardrail:** Retire outdated macros and articles explicitly — inactive content left in place becomes a source of hallucination and agent confusion
