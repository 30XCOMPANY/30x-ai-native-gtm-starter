# context/competitor-radar.md · Two-Layer Radar

> Your traditional competitor radar tracks other companies. Your *real* competitor radar tracks foundation-model releases.
>
> **Constitution: [#4 Capability Obsolescence Radar](../CLAUDE.md#4-capability-obsolescence-radar).** Evidence base: [`research/01-capability-obsolescence-and-icp.md`](../research/01-capability-obsolescence-and-icp.md).

---

## Why this file has two halves

Traditional competitor radars track 5-15 companies in your category. Sufficient for traditional SaaS where the competitive set is stable for years.

For AI-native, that's only **half** the radar. The other half is foundation-model capability — because the next GPT / Claude / Gemini release can commoditize your entire wedge in 90 days. Jasper, Inflection, Adept, Character, Stability all died this way.

So this file has two sections:
- **Section 1 — Traditional Competitive Radar** (companies you compete with)
- **Section 2 — Capability Obsolescence Radar** (models / platforms that could absorb you)

Both are first-class. Don't skip Section 2 because it's harder to track.

---

## Section 1 · Traditional Competitive Radar

Standard battlecard structure. Each direct competitor gets a card.

### Template

```
### [Competitor Name]
- **Last updated**: YYYY-MM-DD
- **Tier**: Direct / Adjacent / Aspirational
- **What they sell**: [1 sentence]
- **ICP overlap with us**: [%, qualitative]
- **Pricing model**: [token / seat / credit / hybrid + specific numbers]
- **Recent funding / valuation**: [if known]
- **Founder / team size**: [for asymmetry assessment]
- **Where we win**: [3 bullets with concrete situations, not generic claims]
- **Where we lose**: [3 bullets — be honest; this is what reps need]
- **Recent product moves** (last 90 days): [bullets]
- **Recent pricing moves** (last 90 days): [critical for AI-native]
- **Customer overlap evidence**: [logos that have both]
- **Honest assessment**: [1-2 sentences founder-to-founder candor]
```

### Active competitor cards

> Fill in your real competitors. Examples below show *structure*, not your situation.

#### [EXAMPLE] Cursor — incumbent
- **Last updated**: 2026-05-26
- **Tier**: Direct
- **What they sell**: AI code editor, agentic workflows, $20-200/mo + Teams + Enterprise
- **ICP overlap**: 70%+ for individual devs; 40% for Enterprise (we lose on procurement story)
- **Pricing model**: Seat + included credits + overflow at API price. Pro $20/mo, Teams $40/seat, Enterprise custom.
- **Recent funding**: $60B valuation, $2B ARR (May 2026 reports)
- **Team size**: Small (Anysphere ~50)
- **Where we win**: [your situation-specific]
- **Where we lose**: brand mass, distribution, ecosystem
- **Recent product moves**: June 2025 switched from "500 fast requests" to credit-based — user backlash that we can quote
- **Recent pricing moves**: increased Pro+ to $60, no consumer change since
- **Customer overlap evidence**: [logos]
- **Honest assessment**: We don't beat Cursor on awareness. We beat them on [specific edge]. Sales positioning must lead with that edge in first 30 seconds.

#### [Your competitor here]
[Fill]

---

## Section 2 · Capability Obsolescence Radar

This is what Maja's traditional starter kit doesn't have. The five death patterns from `research/01...md` are your warning labels.

### 2.1 Foundation-model release tracker

| Model | Last release | Next expected | Capability that threatens us |
|---|---|---|---|
| Claude (Anthropic) | 4.7 (2026-01) | 5.0 (Q3 2026?) | [identify yours — long context? tool use? coding?] |
| GPT (OpenAI) | 5.5 (2025-12) | 6.0 (2026-Q4?) | [identify yours] |
| Gemini (Google) | 3.0 (2026-02) | 3.5 (Q3 2026?) | [identify yours] |
| Llama (Meta) | 4 (2025-10) | 5? | [identify yours] |
| Mistral / DeepSeek / Qwen / others | various | various | [identify yours] |

For each model, track:
- **Release cadence** (last 4 release dates → forecast next)
- **Benchmark trajectory in your vertical** (your benchmark, not generic ones)
- **Pricing trajectory** — has cost-per-token been trending toward zero?

> *Why pricing trajectory matters*: Hume EVI had to drop to $0.04/min after gpt-realtime hit $32/$64 per 1M tokens with a 20% additional cut. Pricing is the leading indicator of commoditization.

### 2.2 The five death patterns

Track which patterns *could* apply to you. Self-assessment, monthly review.

#### Death pattern 1 · Wrapper eaten by foundation model
- **Cases**: Jasper, PDF chat wave, Copy.ai
- **Trigger**: DevDay-class announcement
- **Self-assessment**: If OpenAI / Anthropic added "[your core feature]" natively in their chat UI tomorrow, what % of your users would defect?
  - [ ] <10% — feature is deeply integrated with our other value
  - [ ] 10-30% — vulnerable but defensible
  - [ ] 30-60% — at risk
  - [ ] 60%+ — you're Jasper. Pivot now.

#### Death pattern 2 · Foundation-model burn-rate crushes you
- **Cases**: Inflection, Adept, Character, Stability
- **Trigger**: Trying to train your own foundation model + sell a consumer product against hyperscalers
- **Self-assessment**: Are you training your own foundation model?
  - [ ] No → not exposed
  - [ ] Yes, fine-tuning only → low exposure
  - [ ] Yes, pre-training → check Inflection / Character / Adept stories. Plan exit before $0 cash.

#### Death pattern 3 · Hardware loses to the phone
- **Cases**: Humane Pin, Rabbit R1, Rewind
- **Trigger**: Same underlying model, better device in user's pocket
- **Self-assessment**: Are you a hardware product whose differentiation is "AI on a different device"?
  - [ ] No → not exposed
  - [ ] Yes → your moat must be sensors / formats the phone doesn't have. Otherwise you're Humane.

#### Death pattern 4 · Information intermediary replaced
- **Cases**: Chegg, parts of Quora / Stack Overflow
- **Trigger**: LLMs answer the user's underlying question without your product
- **Self-assessment**: Is your product a paid intermediary to knowledge LLMs now hand out free?
  - [ ] No → not exposed
  - [ ] Yes → urgent re-positioning needed. What did the user *really* need beyond the answer? (Trust? Hands-on tutoring? Workflow integration?)

#### Death pattern 5 · OS integration absorbs the standalone app
- **Cases**: Rewind / Limitless, "AI email assistant" category
- **Trigger**: Apple Intelligence, Windows Copilot+, Google Workspace AI ship native capability
- **Self-assessment**: Does Apple / Microsoft / Google have a public roadmap including your core capability?
  - [ ] No → not exposed
  - [ ] Maybe → plan around being acquired or absorbed
  - [ ] Yes, dated → you have N quarters; pivot to capability they can't ship (deep verticalization, data, B2B compliance)

### 2.3 Early-warning signals (active monitoring)

These trigger an emergency capability-obsolescence review when they fire. From `research/01...md` Section "Five capability-obsolescence early-warning signals":

- [ ] **Core feature runs natively in ChatGPT / Claude / Copilot default UI** — strongest signal
- [ ] **OpenAI / Anthropic DevDay agenda includes your keyword** — 7-day warning
- [ ] **Foundation-model benchmark jumps in your vertical** — 6-month commercial-impact window
- [ ] **Customer churn reason shifts from "price" to "we just use ChatGPT now"**
- [ ] **Your prompt-engineering moat evaporates with new model versions**
- [ ] **Customers ask "what model? Can you swap?"** — you're being treated as a router
- [ ] **Hyperscaler announces "free / unlimited"** of your capability
- [ ] **OS vendor ships your capability natively**

When any fires, jump to Section 2.4.

### 2.4 Emergency Response Playbook

If a Section 2.3 signal fires:

1. **Hour 0** — pause all outbound. Stop selling into the wave you'll be absorbed by.
2. **Day 1** — convene founders + GTM lead. Read this section together. Identify the specific death pattern.
3. **Week 1** — assess time-to-impact. Most patterns have 6-12 months of runway between trigger and revenue impact. Use it.
4. **Month 1** — make the pivot vs. fight decision:
   - **Pivot** = move ICP up-stack or down-stack. Jasper pivoted from individual creators → enterprise marketing teams.
   - **Fight** = double-down on deep verticalization, data moat, integration depth that the foundation model can't replicate. Cline's BYOK + on-prem story is a fight stance.
   - **Sell** = if neither pivot nor fight is plausible, talk to potential acquirers before metrics deteriorate. Character / Inflection / Adept timing-of-sale lessons.

Add the playbook outcome to `outputs/YYYY-MM-DD-obsolescence-response.md`.

---

## Section 3 · Quarterly Radar Review

Cadence: every quarter, both halves of this radar get reviewed together.

- [ ] Update each competitor card (recent moves, pricing)
- [ ] Add new entrants discovered this quarter (especially from `signal-library.md` A2 New-org first-repo burst)
- [ ] Update foundation-model release tracker
- [ ] Re-assess each death pattern self-rating
- [ ] Check all 8 early-warning signals — has any fired?
- [ ] Decide: is our positioning still defensible? If not, plan response.

Log the review in `outputs/YYYY-MM-DD-radar-review.md`.

---

> **[PROTOCOL]**: When a Section 2.3 signal fires, also update `context/positioning.md` Technical Credibility Ladder (which rungs just got commoditized?) and add a `context/icp-definition.md` evolution log entry. Capability obsolescence is rarely isolated.
