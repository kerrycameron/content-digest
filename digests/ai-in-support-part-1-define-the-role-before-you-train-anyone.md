# AI in Support, Part 1: Define the Role Before You Train Anyone

**Source:** https://1fernandoduarte.substack.com/p/ai-in-support-part-1-define-the-role
**Date:** November 17, 2025
**Category:** 1. AI in Customer Support
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- Most AI implementation failures in customer support stem from lack of organizational clarity, not technical limitations — establish a written AI Charter before training staff on tools
- Support teams fill knowledge gaps about AI with anxiety about job security, surveillance, and accountability; addressing these directly converts fear into concrete, manageable questions
- Agents own what they send; leaders own system design and guardrails — AI output is input, not an accountability shield
- Explicitly document which data signals (acceptance rates, edit frequency, handle time) will and will not be used for performance ratings; silence invites worst-case interpretations
- A one-page charter covering purpose, scope, guardrails, metrics, and feedback cadence builds adoption more effectively than any marketing messaging

## Frameworks / Models

### Five Core Team Concerns (and How to Address Them)

| Concern | What to Clarify |
|---------|-----------------|
| Job Security | State whether goals involve volume increase (same headcount) or role evolution; address layoffs directly |
| Accountability & Blame | "Agents own what they send; leaders own system design and guardrails" |
| Surveillance & Micro-Metrics | Define which data signals will/won't be used for performance ratings |
| Quality & Hallucination Risk | Identify topics requiring verification; establish process for reporting wrong AI outputs |
| Workload & Change Pace | Map which tasks shrink, move to AI-assist mode, or shift to higher-value work |

### Five AI Implementation Principles

- **AI Assists, Humans Decide**: AI drafts, summarizes, classifies, suggests — humans own what goes to customers
- **Human Accountability**: Failures prompt systemic review (design? training? guardrails?), not blame assignment
- **Clear Boundaries**: Hard lines on refunds, identity changes, escalated complaints, policy exceptions
- **Privacy & Data Protection**: Operational clarity on approved tools and data flow restrictions
- **Transparency for Teams**: Visible AI footprint, feedback mechanisms, rule change communication

### One-Page AI Charter Template

| Section | Content |
|---------|---------|
| Purpose | One paragraph explaining why AI exists in your context |
| Scope | Channels/question types AI participates in; work that stays human-only |
| What AI Does | Draft replies, summarize interactions, classify tickets, suggest resources, answer narrow FAQs |
| What AI Does Not Do | Approve financial decisions, change account ownership, override policy, make final high-risk decisions |
| Guardrails | No passwords in prompts; mandatory review for refunds/denials/escalations; feedback mechanism |
| Metrics | Containment rates, handle time trends, reopen rates, CSAT impact, incident count |
| Training & Feedback | Onboarding timeline, coaching integration, feedback process, charter review cadence |

### Charter Implementation Sequence

1. Draft with mixed group (leader, manager, QA/training, 2 senior agents)
2. Align leadership (operations, product, legal)
3. Present to full team for feedback on vagueness, fairness, and realism
4. Pilot under charter; track metrics; iterate visibly
5. Scale with consistent messaging

## Guardrails & Anti-patterns
- **Anti-pattern:** Jumping to tool training before addressing "What is AI for?" with the team
- **Guardrail:** Publish a written charter that defines AI's role, boundaries, and accountability before any tool rollout
- **Anti-pattern:** Using "efficiency" as a benefit without mapping which tasks change for whom
- **Guardrail:** Link efficiency claims to specific task changes — what shrinks, what moves to AI-assist, what shifts to higher-value work
- **Anti-pattern:** Hiding which data signals will be used for performance review
- **Guardrail:** Explicitly state which metrics will and won't factor into ratings; hidden logic destroys trust
- **Anti-pattern:** Treating AI output as an escape hatch from agent accountability
- **Guardrail:** Establish that agents own what they send — AI output is input, not a shield
