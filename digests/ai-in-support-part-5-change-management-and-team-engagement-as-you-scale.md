# AI in Support, Part 5: Change Management and Team Engagement as You Scale

**Source:** https://1fernandoduarte.substack.com/p/ai-in-support-part-5-change-management
**Date:** December 15, 2025
**Category:** 1. AI in Customer Support; 6. Support Leadership
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- AI adoption fails due to confusion, mistrust, absent ownership, missing feedback mechanisms, lack of structured coaching, and gradual usage decline post-launch — not technology gaps
- Three-phase rollout (controlled release → team rollout → scale & expand) prevents the most common failure modes by controlling pace and building trust incrementally
- Three defined ownership roles are required: AI Ops Owner (rollout and decisions), QA Partner (sampling and coaching), Security/Privacy Partner (boundaries and incidents)
- "No source, no promise" — agents must verify every specific claim against documented sources before sending; red-flag categories require mandatory human verification
- The coaching loop must focus on work product quality and patterns, not individual performance; share two positive and two negative patterns weekly

## Frameworks / Models

### Three-Phase Rollout Sequence

| Phase | Scope | Key Activities |
|-------|-------|----------------|
| **Phase 1: Controlled Release** | Single queue or workflow | Designated owner oversight; daily output reviews; real-time prompt refinement |
| **Phase 2: Team Rollout** | Full team, same workflow | Weekly calibration sessions; clear escalation pathways; track adoption by shift |
| **Phase 3: Scale & Expand** | Second workflow added | Gradually add decision points; strengthen controls with expanded permissions |

### Ownership Model (Three Roles)

- **AI Ops Owner**: Manages rollout plan, measurement, weekly changes, decision documentation
- **QA Partner**: Handles sampling, defect classification, coaching insights
- **Security/Privacy Partner**: Establishes boundaries, approves access, manages incidents

### Red Flag Categories (Require Human Verification)

| Category | Examples |
|----------|---------|
| Money and eligibility decisions | Refunds, approvals, denials |
| Deadlines and commitments | Processing times, due dates |
| Legal and enforcement language | Violations, penalties, appeals |
| Identity and account access | Password resets with ID verification |
| Sensitive personal information | SSN, DOB, financial data |

### The 10-Second Stop Rule
1. Identify the specific claim in the AI output
2. Locate the source documentation
3. Write the reply with a source reference
4. Escalate if no source exists — "No source, no promise"

### Weekly Adoption Metrics (Single-Page Report)

| Metric | Action |
|--------|--------|
| Usage rate by workflow | Flag declining adoption for coaching |
| Reopen rate for AI-assisted replies | Signal output quality issues |
| QA defect rate linked to AI outputs | Drive coaching focus |
| Escalation volume by red flag category | Surface scope expansion needs |
| Time saved in specific workflow | Validate efficiency claims |

### Coaching Loop Protocol (Weekly)

- Review 10 AI-assisted replies per agent
- Tag defects by category, not blame
- Share 2 positive and 2 negative patterns weekly
- Focus on work product quality, not individual performance

## Guardrails & Anti-patterns
- **Anti-pattern:** Leadership pressure for adoption before agents trust AI outputs
- **Guardrail:** Build trust through transparent metrics and visible fixes before expanding mandates; "Change management is the product. Tooling is the easy part."
- **Anti-pattern:** Power users advancing while the broader team disengages
- **Guardrail:** Track adoption by shift and team unit — not just total usage volume — and intervene when segments fall behind
- **Anti-pattern:** Deployment without guardrails causing incidents that derail momentum
- **Guardrail:** Define red-flag categories and the 10-second stop rule before rollout; publish what requires verification and what can flow directly
- **Anti-pattern:** Rewarding usage volume as the adoption metric
- **Guardrail:** Reward clean outcomes — correct answers, no rework, resolved first contact — not the number of AI-assisted interactions
- **Anti-pattern:** Adding multiple workflows simultaneously when scaling
- **Guardrail:** One workflow at a time; one new data source at a time; re-run red flag testing after each change
