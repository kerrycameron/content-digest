# AI Ops For Support Leaders, Part 4: Risk, Privacy, and Hallucinations

**Source:** https://1fernandoduarte.substack.com/p/ai-ops-for-support-leaders-part-4
**Date:** January 26, 2026
**Category:** 1. AI in Customer Support
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- Three critical risk categories — hallucinations (invented facts), missing constraints (skipped rules), and data exposure (PII leakage) — each require distinct detection and mitigation approaches
- The Verify-Then-Trust Loop establishes priority order for sources of truth: system of record → official docs → internal KB → runbook → AI suggestion (lowest priority)
- The four-tier risk framework determines verification intensity: Tier 0 (link and move) through Tier 3 (stop and escalate) — agents must assign a tier before drafting any response
- "No Hero Moves Rule": no guessing, no improvised policy, no unverified links, no quoting sensitive data back to customers, no "I think" on high-risk tickets
- Accuracy matters more than speed — every tier escalates complexity, requiring stricter documentation and sourcing standards as risk increases

## Frameworks / Models

### Risk Tier Framework

| Tier | Scope | Standard |
|------|-------|----------|
| **Tier 0: Link and Move** | General how-to, navigation, troubleshooting | Use approved KB only; verified link only |
| **Tier 1: Verify the Record** | Account access, profile updates, routine workflows | Check system of record; use template; add internal verification note |
| **Tier 2: Two-Source Verify** | Money movement, identity, access changes, entitlements | Verify via system + official docs; use structured script; escalate on conflicts |
| **Tier 3: Stop and Escalate** | Fraud, security, legal threats, compliance requests | Do not respond publicly; escalate to security/legal/compliance |

### Five Hallucination Signals & Detection

| Signal | Detection Method | Action |
|--------|-----------------|--------|
| **Confident Policy** | Rule stated without source | Search KB; confirm official policy page exists |
| **Fabricated System State** | "Application approved," "Payment sent" | Open system of record; verify status and timestamps |
| **Phantom Link** | Plausible URL with unfamiliar path | Open link; confirm correct domain and page |
| **Extra Steps** | More steps than official process | Compare to runbook; remove ghost steps |
| **Audience Mix-up** | Wrong user type (vendor data to parent) | Confirm role in system; match process to user type |

### Verify-Then-Trust Loop (7 Steps)

1. **Name the Intent**: Single sentence describing the request
2. **Assign Risk Tier**: Tier 0–3
3. **Pull Sources of Truth (in order)**: System of record → Official docs → Internal KB → Runbook → AI suggestion
4. **Verify Critical Fields**: Identity, transaction details, eligibility
5. **Draft Response**: Short steps; avoid unsupported claims; use approved language
6. **Add Verification Note**: Log intent, tier, sources, fields verified, next action
7. **Escalate on Triggers**: Conflicting sources, missing docs, customer exceptions, legal language, new policy claims, identity/money/fraud/eligibility requests

### Internal Verification Note Template

```
INTENT: [Single sentence]
RISK TIER: [0/1/2/3]
SOURCES CHECKED: ☐ System  ☐ Docs  ☐ KB  ☐ Runbook
CRITICAL FIELDS: Identity [Y/N]  Amount/ID [Y/N]  Eligibility [Y/N]
REDACTION: [Yes, redacted / No]
NEXT ACTION: [Specific step]
```

### Privacy Operating Rules

**Data Minimization:** Request only the smallest dataset needed for the next step; avoid sensitive data during triage

**Redaction Requirements:** Mask SSN, DOB, bank details, document numbers, and full addresses (when unnecessary) in public replies and internal notes

**Channel-Specific Rules:**

| Channel | Rule |
|---------|------|
| Chat | No sensitive documents, bank details, or full DOB requests |
| Email | Use secure upload links (not attachments); do not quote sensitive data back |
| Internal Tools | No customer sensitive data in Slack or non-secure channels; no screenshots with sensitive fields outside secure channels |

### QA Scorecard for Tier 1+ Tickets

Score on: Clear intent statement · Correct risk tier assigned · Sources logged in internal note · Critical fields verified · Approved structure used · Redaction performed · Escalation triggers handled

### 5-Day Training Implementation

| Day | Activity |
|-----|---------|
| 1 | Risk tier and intent labeling on 20 real tickets |
| 2 | Verification loop drills and internal note writing |
| 3 | Privacy and redaction drills with channel examples |
| 4 | Hallucination spotting; rewrite unsafe AI drafts |
| 5 | Live QA review of tickets from prior week |

## Guardrails & Anti-patterns
- **Anti-pattern:** Trusting confident-sounding AI output without source verification ("I think the policy says...")
- **Guardrail:** Apply the No Hero Moves Rule — any specific policy claim requires a documented source before it reaches the customer
- **Anti-pattern:** Treating AI suggestions as the primary source of truth
- **Guardrail:** AI suggestions are the lowest-priority source — always behind system of record, official docs, internal KB, and runbook
- **Anti-pattern:** Sending sensitive data (SSN, DOB, bank account numbers) through AI tools to improve response quality
- **Guardrail:** Use placeholder fields in prompts; redact all sensitive identifiers from AI drafts before including in official records
- **Anti-pattern:** Responding to fraud, security, or legal threat contacts through normal support channels
- **Guardrail:** Tier 3 contacts stop completely at the agent level — no public response; escalate directly to security/legal/compliance
