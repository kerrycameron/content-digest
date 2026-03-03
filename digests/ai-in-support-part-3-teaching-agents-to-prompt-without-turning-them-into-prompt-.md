# AI in Support, Part 3: Teaching Agents To Prompt Without Turning Them Into Prompt Engineers

**Source:** https://1fernandoduarte.substack.com/p/ai-in-support-part-3-teaching-agents
**Date:** December 1, 2025
**Category:** 1. AI in Customer Support
**Recency Score:** 0-6 months (full weight)

## Key Takeaways
- Support agents need one simple pattern — not prompt engineering training — to get consistent, safe AI outputs during normal work shifts
- The five-element structure (Context + Task + Constraints + Tone + Format) maps directly to how agents already think about customer interactions
- Structured prompts reduce rewrites, protect policy and tone adherence, and conserve agent attention during peak periods
- All training examples must come from actual organizational tickets; generic internet samples don't translate to support contexts
- QA integration is the key to sustained adoption: add "Did agent provide sufficient context and constraints?" to the QA form

## Frameworks / Models

### Five-Element Prompt Pattern

| Element | Definition | Example |
|---------|------------|---------|
| **Context** | Situation overview, customer type, prior events, relevant links | "This is a first-contact email from a parent asking about application status" |
| **Task** | Single clear action verb | summarize / draft / translate / explain / list / highlight |
| **Constraints** | Rules, guardrails, what to avoid — policy limits | "Do not make promises. Do not add information not in policy." |
| **Tone** | Voice appropriate to channel and audience | friendly, direct, calm, formal |
| **Format** | Output shape | bullets, paragraphs, numbered steps, tables, length limit |

### Seven Operational Prompt Templates

| Template | Use Case | Key Constraint |
|----------|----------|----------------|
| Call/Chat Summary | Ticket logs | No promises; no added information |
| Draft Reply from Policy | Email/chat responses | Only use policy text; do not change dates/amounts |
| Translation with Tone Fit | Bilingual support | Preserve meaning and tone; short sentences |
| Explain Policy in Plain Language | Customer education | No legal terms; include next steps |
| Find Policy Details & Risk Points | Agent research | Bullet points; highlight higher-risk parts |
| Build Customer Checklist | Process guidance | Numbered steps; one sentence each |
| Summarize Account History | Escalation prep | Key events, decisions, promises; end with current status |

### Five-Step Training Sequence

1. **Live Demo with Real Tickets**: Show vague vs. structured prompt outputs using three actual tickets (simple, messy, escalation)
2. **One-Page Prompt Guide**: Pattern + seven templates with one example each; post in agents' reference locations
3. **Small Group Practice**: Distribute real tickets; agents write prompts using the pattern; share and compare outputs
4. **QA Integration**: Add to QA form: "Did agent provide sufficient context and constraints?" Review AI-assisted tickets in one-on-ones
5. **Monthly Refresh**: Collect strong prompts from floor staff; update guide with new examples; retire unused patterns

## Guardrails & Anti-patterns
- **Anti-pattern:** Teaching prompt engineering as a specialized skill requiring study and expertise
- **Guardrail:** Frame prompting as a safety habit — agents already think contextually and rule-based; AI just needs that reasoning made explicit
- **Anti-pattern:** Vague prompts like "Help me reply to this customer"
- **Guardrail:** Require all five elements; the constraints field is the most important — it prevents policy invention and hallucination
- **Anti-pattern:** Using generic internet prompt examples during training
- **Guardrail:** Source all training examples from actual organizational tickets; abstract examples don't build habit in context
- **Anti-pattern:** Deploying prompting training without QA accountability
- **Guardrail:** Add prompt structure as a QA metric from day one; what gets measured gets practiced
