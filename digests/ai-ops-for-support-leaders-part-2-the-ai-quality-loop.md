# AI Ops For Support Leaders, Part 2: The AI Quality Loop

**Source:** https://1fernandoduarte.substack.com/p/ai-ops-for-support-leaders-part-2
**Date:** January 12, 2026
**Category:** 1. AI in Customer Support
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- Quality degradation is caused by mundane factors — policy changes, stale knowledge articles, product flow modifications, seasonal edge cases, routing shifts, agent trust erosion — not model failures; "A demo does not survive those forces. Operations does."
- Establish one unified AI Fix intake channel with defined failure type classifications — scattered feedback dies in Slack threads and informal channels
- The six failure type taxonomy (Knowledge Gap, Knowledge Conflict, Scope Mismatch, Workflow Gap, Tool Behavior, Risk Breach) converts vague complaints into routed, ownable work
- Weekly 30-minute review with structured release process is the core operating cadence; monitor changed intents for 72 hours post-release
- Sample 1% of AI conversations per channel (minimum 25) weekly, plus 100% of AI Fix items, escalations, negative CSAT, and red-zone touches

## Frameworks / Models

### Six Failure Type Classifications

| Type | Definition |
|------|------------|
| **Knowledge Gap** | Missing articles, steps, or examples |
| **Knowledge Conflict** | Contradictory sources, outdated policies |
| **Scope Mismatch** | Wrong intent, audience, or workflow triggered |
| **Workflow Gap** | No action, route, macro, or handoff after response |
| **Tool Behavior** | Prompt, guardrail, retrieval, citation, or formatting issues |
| **Risk Breach** | PII exposure, financial transactions, legal/medical language, identity verification failures |

### Quality Rubric (0–2 scoring per dimension)

| Dimension | 0 | 1 | 2 |
|-----------|---|---|---|
| Correct Outcome | Wrong | Partial | Correct |
| Evidence Support | No source | Weak source | Matches source |
| Next Step Clarity | Unclear | Some steps | Clear steps with owner |
| Safety & Compliance | Risky | Borderline | Safe |
| Tone & Promise Control | Overpromised | Minor issue | Clean |

**Passing Thresholds:** Green topics: 8/10 · Yellow topics: 9/10 · Red topics: Block or force handoff

### Intentional Sampling Strategy

| Sample Type | Rate |
|-------------|------|
| AI conversations per channel | 1% (minimum 25) |
| AI Fix items | 100% |
| Escalations post-AI | 100% |
| Negative CSAT tied to AI | 100% |
| Red-zone topic touches | 100% |

### Weekly Review Structure (30 Minutes)

**Agenda:**
- 5 min: AI Fix count by failure type
- 10 min: Top 5 red/yellow items
- 10 min: Approve next release changes
- 5 min: Publish changelog

**Outputs:** Updated backlog with owners/due dates · Changelog entry · One coaching note for agents

### Operational Release Checklist

- Change type labeled (knowledge, workflow, prompt, routing, guardrail)
- Owner and approver assigned
- Test set reviewed
- Changelog documented
- Metric identified for monitoring

**72-Hour Post-Release Monitoring:** AI Fix volume · Escalation rate · Negative CSAT · 7-day recontact rate (all segmented by changed intents)

### Minimum Weekly Metrics

| Metric | Definition |
|--------|-----------|
| AI Fix Intake Volume | Count of reported issues |
| Time to Fix | Median days from report to release |
| Escalation After AI | Escalations ÷ AI interactions (by intent) |
| Recontact After AI | 7-day recontacts ÷ AI interactions (by intent) |
| Quality Score Pass Rate | Rubric pass percentage (by intent) |
| Drift Signal | % "Other" or "Needs Clarification" volume (by channel) |

### First Week Implementation

1. Create AI Fix intake (single tag or form)
2. Add six failure types as picklist options
3. Schedule 30-minute weekly review meeting
4. Publish first changelog entry

## Guardrails & Anti-patterns
- **Anti-pattern:** Relying on informal channels (Slack, team meetings) to surface AI quality issues
- **Guardrail:** Create one unified intake mechanism with defined failure type classifications — unstructured feedback creates unactionable noise
- **Anti-pattern:** Applying the same QA sampling rate regardless of risk or topic sensitivity
- **Guardrail:** Sample 100% of red-zone touches, escalations, and negative CSAT regardless of volume; risk-weight your QA effort
- **Anti-pattern:** Shipping AI changes without 72-hour post-release monitoring
- **Guardrail:** Monitor AI Fix volume, escalation rates, and recontact rates on changed intents for 72 hours after every release
- **Anti-pattern:** Running weekly reviews without a changelog or coaching note output
- **Guardrail:** Every review produces three outputs: updated backlog, changelog entry, one coaching note — without these, the loop doesn't close
