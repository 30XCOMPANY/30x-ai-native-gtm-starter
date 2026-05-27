# Playbook · Capability Obsolescence Emergency

> When `strategy/competitors.md` Section 2.3 early-warning signal fires — and confirms — this playbook governs the response in the first 30 days.
>
> Different from `foundation-model-commoditizes-your-feature.md`: that's for when it's already happened. This is for the *preemptive* response when you see it coming.

---

## When to invoke

Any of these from `competitor-radar.md` Section 2.3 fires:

- DevDay-class agenda includes your keyword **AND** the timeline is < 90 days
- Foundation model's benchmark in your vertical jumped >15% in latest release
- Hyperscaler announced "free / unlimited" for your category
- OS vendor's roadmap publicly mentions your capability

This is **not** the playbook for "competitor shipped something." For that, see `competitor-ships-equivalent.md`.
This is **not** the playbook for "it already happened." For that, see `foundation-model-commoditizes-your-feature.md`.

This is for: **a frame-shaking event is coming, you have weeks not months.**

---

## Day 0 — confirmation + scenario planning

### Step 1: Verify, don't assume

- Read all the source material
- Confirm the timeline (some announcements are years out; some are weeks)
- Cross-reference: is anyone else in your space reacting yet? (If yes, it's serious. If no, you might be wrong about scope.)

### Step 2: Model 3 scenarios

For each scenario, write 2-3 sentences:

**Scenario A · Mild impact**: The announced capability ships at 50% of marketed depth, addresses 30% of your use cases. Your revenue impacted ~15%.

**Scenario B · Moderate impact**: Capability ships at 70% depth, covers 50% of your use cases. Revenue impacted 30-50%.

**Scenario C · Severe impact**: Capability ships at >85% depth, covers >70% of your use cases. Revenue impact >60%. Existential.

**Probability assignment**: don't be optimistic. Assume Scenario B is the baseline.

---

## Day 1-7 — preparation, not response

### Don't go public yet

You're preparing, not reacting. Public reactions before the actual event waste credibility (people forget your warning if the event is mild) or create alarm (in customers, partners, employees).

### Internal moves

1. **Audit pipeline**: which open deals are exposed? Re-score with the scenario in mind. Some will move from likely-close to high-risk.
2. **Audit customers**: which existing customers are most exposed to the upcoming event? Plan personalized check-in calls.
3. **Audit roadmap**: which planned features now look obsolete? Which look more important?
4. **Audit team**: do you have the right skills to execute the response? Hiring decisions may need to shift.

### Strategic decision

By Day 7, founders make a call on **prepared response posture**:

- **Sharpen current positioning** to lead with what's unique even after the event
- **Pre-ship adjacent features** to widen the gap before the event
- **Public thought leadership** to claim category authority before the event
- **Quiet repositioning** to move slightly away from the soon-commoditized capability

---

## Day 7-21 — execute the preparation

### Sharpen positioning (if chosen)

- Update `strategy/positioning.md` Rung 5 — capability obsolescence resistance gets explicit
- Update landing page hero — leading with what's unique
- Sales script update — reps prepared to handle "but won't [foundation model] do this for free?" before it does

### Pre-ship features (if chosen)

- Choose 1-2 features that widen your moat post-event
- Ship within 3 weeks (not 3 months)
- Public release with framing that hints at why now: "We're investing in [direction] because we believe [direction] is what matters in 2026"

### Public thought leadership (if chosen)

- Founder publishes a substantive post on the impending shift (NOT a self-promo piece)
- Quote / interview / podcast appearances about your category
- Sponsor a benchmark or analysis that establishes your authority

### Quiet repositioning (if chosen)

- Update marketing site without announcement
- Sales reps gradually shift conversation
- New outbound copy frames product around the *not-soon-commoditized* dimension

---

## Day 21-30 — event happens (or doesn't)

### If it happens at Scenario A intensity

- Your preparation was over-investment, but cheap insurance
- Tweet about how your prep paid off
- Customer comms note "we were ready"

### If it happens at Scenario B intensity

- Your preparation is now critical
- Trigger `foundation-model-commoditizes-your-feature.md` playbook
- The pivot/fight/sell decision is informed by your Day 7 prepared response

### If it doesn't happen (delayed, withdrawn, smaller than expected)

- Your sharpened positioning is still good
- Your pre-shipped features are still valuable
- Don't tell people you "got worked up over nothing" — silence is fine here

---

## What NOT to do

- **Tell customers your category is dying** — even if you think so, this kills your credibility. Repositioning happens through behavior, not announcements.
- **Stop selling current product** — you have 30-90 days of revenue from existing positioning before the event matters. Take the revenue.
- **Lay off team preemptively** — until you know the event's actual impact, don't act on speculation
- **Sell prematurely** — sale conversations should wait until the event happens and impact is known. Pre-event sale conversations get bad terms.

---

## Pattern in the wild

Maya wrote (in the Helmsman sample-company `positioning.md` Rung 5 example): a January 2026 post "Why we don't compete with Anthropic on evals" predicted Anthropic would commoditize dev-time evals.

She didn't:
- Tell customers Helmsman was dying
- Stop selling current eval product
- Pivot to a new product before Anthropic actually shipped

She did:
- Sharpen positioning around "production reliability + multi-model + remediation" as the resilient layer
- Publicly establish Helmsman's category authority (the post itself)
- Begin SOC 2 (so when Anthropic shipped, Helmsman could capture regulated buyers Anthropic couldn't serve)

When Anthropic shipped Claude 5.0 with native dev-time evals (hypothetically in our sample company timeline), Helmsman was ready. Revenue dipped 18% in Q4, recovered in Q1 of the next year, and Helmsman emerged as the multi-model reliability brand. **The preemptive playbook is what made it possible.**

---

## Reference cases

- **Anthropic's MCP donation** (real, 2024-11): preemptive standardization to avoid being commoditized by OpenAI's plugin ecosystem
- **Vercel's v0 launch** (real, 2024): preemptive move into AI codegen before the foundation models did it natively
- **Stability AI** (real, 2023-2024): did *not* preemptively move; lost the moment to Midjourney + DALL-E 3

The lesson: capability obsolescence emergencies happen. Companies that prepare survive smaller; companies that wait die bigger.
