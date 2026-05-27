---
name: objection-handle
description: Draft a tested response to a specific sales objection. Reads `pipeline/objections.md`, `strategy/positioning.md`, `strategy/capability-radar.md`. Outputs the response + a follow-up question + a DQ signal so reps know when to walk away.
---

# Skill · objection-handle

## What this does

When a rep hits an objection in a call, this skill produces (1) what to say, (2) what to ask next, (3) when to stop fighting and DQ. Adds the new objection + response to `pipeline/objections.md` so the pattern is captured.

## How to invoke

```
objection-handle: "[objection verbatim]"
```

Examples:
- `objection-handle: "Why wouldn't OpenAI just do this in their next release?"`
- `objection-handle: "We can build this in-house with our AI team"`
- `objection-handle: "Your pricing is too high"`
- `objection-handle: "We'll wait until we figure out our LangChain migration"`

## Steps Claude takes

1. **Classify the objection** into one of seven archetypes:
   - **Capability obsolescence** (will the foundation model do this?)
   - **Build vs buy** (we have engineers, we'll do it)
   - **Price** (too expensive)
   - **Timing** (not now, we're focused elsewhere)
   - **Trust / risk** (you're too new / small)
   - **Compliance** (security / data residency / contract terms)
   - **Personal** (champion lacks authority / left the company)

2. **Read context**:
   - `pipeline/objections.md` — existing tested responses
   - `strategy/positioning.md` — moat narrative
   - `strategy/capability-radar.md` — if obsolescence-class objection
   - `strategy/pricing.md` — if price objection
   - `strategy/about.md` — if trust/scale objection

3. **Draft three components**:

   ### A. Translation
   What they actually mean. Most objections are surface for a deeper concern.
   Example: "Pricing is too high" usually means one of:
   - ROI not clear → reframe to outcomes
   - Tier mismatch → suggest different tier
   - Genuine budget cap → discount with strings OR DQ

   ### B. Response (≤ 50 words)
   - Acknowledge their concern (1 sentence, don't dismiss)
   - Counter with a specific (number, case, quote)
   - Don't oversell — leave room for them to push

   Example for capability obsolescence:
   > "Honest concern — Anthropic might. Our wedge is multi-model production reliability + remediation + drift-tracking, which is the workflow layer they don't want to own. Customer X just hit 3 model swaps in 6 weeks; we caught 4 regressions for them. That use case scales differently."

   ### C. Follow-up question
   Re-engages discovery. Forces them to clarify.
   Example: "What's the foundation model release that would worry you most?"

   ### D. DQ signal
   When to stop. Honest founders walk away from misfit deals — the alternative is a customer who churns at month 3.
   Example: "If they say 'all our engineers love prompt-engineering and build everything in-house', they will build. Walk away."

4. **Save outputs**:
   - Update `pipeline/objections.md` — append to the existing pattern OR add a new entry
   - Write to `outputs/YYYY-MM-DD-objection-{slug}.md` for the specific call context

## Quality filters

- [ ] Response ≤ 50 words (the rep has to say it naturally)
- [ ] Includes specific proof (number, name, quote) — never generic
- [ ] Acknowledges the concern before countering
- [ ] DQ signal is real, not "always keep fighting"
- [ ] Tests against `strategy/brand.md` voice (no marketing adjectives)

## Anti-patterns

- **Don't write a 200-word response.** The rep has to say it. 50 words max.
- **Don't dismiss the objection.** Buyers can tell.
- **Don't list 5 reasons we're better.** Pick one specific.
- **Don't promise things we can't deliver.** Lying to close = churn at month 3.
- **Don't run this skill repeatedly for the same objection.** Capture the response once in `objections.md` and reuse.

## Trace to architecture

Reads from: `pipeline/objections.md` (existing patterns), `strategy/*` (truth)
Writes to: `pipeline/objections.md` (new patterns), `outputs/` (call-specific)
