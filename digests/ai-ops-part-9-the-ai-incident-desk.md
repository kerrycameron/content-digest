# AI Ops, Part 9: The AI Incident Desk

**Source:** https://1fernandoduarte.substack.com/p/ai-ops-for-support-leaders-part-9
**Date:** March 2, 2026
**Category:** 1. AI in Customer Support
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- AI failures propagate differently than product bugs: confident-sounding wrong answers travel farther, and well-intentioned emergency edits create system drift that complicates root cause analysis
- The incident desk prioritizes operations over models—the first question is "what should the team do right now to keep customers safe and agents productive?" not "why did the model fail?"
- Severity classification drives immediate action: SEV 0 (stop operations/disable flows), SEV 1 (activate safe mode/rollback), SEV 2 (mitigate same-shift), SEV 3 (log and queue to weekly quality loop)
- Five defined roles keep response intentionally small: Incident Commander, Triage Lead, Fix Owner, Comms Lead, Scribe
- Incident updates to agents must be instructions only (what's happening, who's affected, what to do now, what to stop, next update time); the narrative belongs in the post-incident review

## Frameworks / Models

### Severity-Driven Response Model
| Severity | Trigger | Immediate Action |
|----------|---------|-----------------|
| SEV 0 | Safety, privacy, compliance, financial risk | Stop operations, disable flows, route to humans, notify leadership |
| SEV 1 | High-volume wrong answers | Activate safe mode, roll back changes, narrow scope |
| SEV 2 | Localized issues | Mitigate same-shift when possible; document workarounds |
| SEV 3 | Minor quality issues | Log and route to weekly quality loop |

### Safe Mode Mitigation Menu
- Human-only routing for high-risk intents
- Retrieval-only responses (no interpretation)
- Escalate-first on low confidence
- Narrow intent scope during drift
- Agent verification step for risk tiers

### 10-Step Live Shift Runbook
1. Detect (via agents, QA sampling, escalation spikes)
2. Open incident ticket
3. Assign severity and roles
4. Freeze all random edits
5. Confirm with two real examples
6. Scope blast radius (intents, brands, languages, channels, volume)
7. Choose safest mitigation from menu
8. Communicate single instruction set
9. Validate on small gold set
10. Monitor and close

## Guardrails & Anti-patterns
- **Anti-pattern:** Allowing agents to improvise fixes mid-shift (editing macros, changing routing, adjusting prompts independently)—each change creates system drift and makes root cause analysis harder
- **Guardrail:** Freeze all edits on incident open; deploy only options from the pre-defined safe mode mitigation menu; route the permanent fix through the release train (Part 8) after the shift
