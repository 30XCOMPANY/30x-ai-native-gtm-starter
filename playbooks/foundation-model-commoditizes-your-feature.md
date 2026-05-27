# Playbook · Foundation Model Commoditizes Your Feature

> Emergency response when OpenAI / Anthropic / Google ships a capability that absorbs your core wedge.
>
> This is the hardest scenario in `context/competitor-radar.md` Section 2 — capability obsolescence, real-time edition.
>
> Reference cases: see `research/01-capability-obsolescence-and-icp.md`. Especially Jasper, Inflection, PDF chat wave.

---

## How to know it's happening

Any of:
- Anthropic / OpenAI / Google DevDay agenda includes your keyword
- Their native UI now does your core feature
- Your trial → paid conversion drops 30%+ in a single month
- Customer churn reason shifts to "we just use [foundation model] for that"
- Pricing-comparable feature on the foundation model side approaches free

When this fires, you have **3 to 12 months** before commercial impact, depending on how quickly the foundation model's feature matures.

---

## Day 0 — within 24 hours of confirmation

1. **Verify the signal**. Don't act on rumor. Read the actual release / documentation.
2. **Stop spend on anything tied to the now-commoditized wedge**: outbound emphasizing the wedge, paid acquisition leaning on it, content scheduled to launch about it.
3. **Founders + senior team convene**. No customer comms yet.

---

## Day 1-3 — internal triage

### Triage question 1 · How much of our revenue is exposed?

- **<20%**: it's a roadmap problem; you have time
- **20-60%**: it's a strategy problem; pivot or fight decision needed
- **>60%**: it's an existential problem; consider sale or radical pivot

### Triage question 2 · What % of customer use cases are commoditized?

Different from revenue exposure. A customer paying you $10K/month for 5 features, 1 of which got commoditized, is at 20% feature-exposure but 100% revenue-exposure if that 1 feature was their primary buy reason.

Audit each customer:
- What's their primary use case with you?
- Does the foundation model now do that primary use case?
- What's their migration switching cost?

### Triage question 3 · Which death pattern fits?

From `context/competitor-radar.md` Section 2.2:

1. Wrapper eaten by foundation model → consider pivot up-stack or vertical
2. Foundation model burn-rate (you train your own) → existential; sell or stop training
3. Hardware loses to phone → very hard; pivot or sell
4. Information intermediary replaced → reposition around workflow / data
5. OS integration absorbs → partner with the OS vendor or vertical-pivot

---

## Day 3-14 — make the bet

You have three options. Pick one. Don't try multiple.

### Bet 1 · Pivot

**When it's right**: significant revenue exposure (40%+); customer base is broad enough that a shifted positioning still serves most of them.

**How**:
- Identify a new wedge that the foundation model *won't* replicate (workflow integration, vertical compliance, data network effect, multi-model orchestration)
- Re-position around it within 30 days (landing page, sales messaging, outbound copy)
- Tell customers transparently: "the AI capability we provided is now native in [model]. Here's what we provide that they don't."
- Lose ~15-30% of customers in the transition; expect this and don't panic.

**Example**: Jasper pivoted from individual creators using GPT-3 prompt templates → enterprise marketing teams with brand-voice features Jasper's own training adds.

### Bet 2 · Fight

**When it's right**: you have a deep moat the foundation model can't replicate quickly (regulated industry compliance, proprietary data, deeply embedded integrations).

**How**:
- Double down on the moat
- Publish your defensibility story openly (transparency = confidence signal)
- Ship faster than them in your niche (you can iterate weekly; they can't)
- Don't compete on the commoditized layer; compete on what's around it

**Example**: Cline doubled down on "BYOK + open source + enterprise compliance" — Cursor / Copilot can't easily match the moral narrative.

### Bet 3 · Sell

**When it's right**: existential exposure (>60%) AND you don't see a defensible pivot AND your team is too small / lacking right skills to compete with the foundation model.

**How**:
- Start conversations *before* metrics deteriorate visibly
- Likely buyers: the foundation model company itself (acqui-hire), an adjacent platform that wants your customer base, a strategic buyer in an industry where your tech is useful
- Be honest with team early — discovering 3 months after the founders is corrosive

**Example**: Character.AI sold to Google ($2.7B reverse acqui-hire) while still revenue-positive. Inflection sold the team to Microsoft. Both better than running out of cash trying to "fight."

---

## Day 14-30 — public + customer communication

Once the bet is made, communicate it.

**Public** (founder X post + blog):
- Acknowledge the foundation model's announcement
- Be honest about how it affects you
- Tell your story (pivot, fight, partner) without spin
- Show the new positioning / product direction in the same post

**Customers** (personal email or call):
- Specific to their use case: "[model] now does X — here's what that means for you specifically"
- Offer migration help if relevant (don't make them figure it out)
- Reaffirm what you're still uniquely doing for them

**Team**:
- Town hall within 7 days of the bet decision
- Specific roles + responsibilities
- What stays, what changes, what stops

---

## What NOT to do

- **Hide it**. Customers find out anyway, and they trust you less.
- **Compete head-on with the foundation model**. You will lose; they have infinite money.
- **Spread bet across multiple options**. Half-pivot + half-fight = full death.
- **Delay the bet hoping it'll pass**. Capability obsolescence doesn't pass; it accelerates.
- **Use marketing to mask the substance**. "Now more important than ever!" reads as panic.

---

## Reference template · the 6-month review

Set a 6-month checkpoint after the bet:

| Metric | Target | Actual | Verdict |
|---|---|---|---|
| Revenue at month 6 vs day 0 | 70-100% (pivot) / >100% (fight) | | |
| Customer churn at month 6 | <30% (pivot acceptable) | | |
| Trial → paid conversion vs day 0 | within 80% | | |
| New customer ICP shape | shifted appropriately | | |

If the bet isn't working at 6 months, re-triage. **Don't sunk-cost a failed pivot.**

---

## Reference cases

- **Jasper (Bet 1: Pivot)** — succeeded at smaller revenue; survived. Lesson: pivot before you're out of cash.
- **Character.AI (Bet 3: Sell)** — sold at strong terms. Lesson: timing the sale matters more than maximizing valuation.
- **Stability AI (No bet)** — burn rate caught up before management replaced. Lesson: silence is the worst response.
- **Cline (Bet 2: Fight)** — chose moral narrative as moat. Survived because the moat was real, not vapor.

See `research/01-capability-obsolescence-and-icp.md` for sources.
