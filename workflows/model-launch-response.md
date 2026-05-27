# Workflow · Foundation-Model Launch Response

> When Anthropic / OpenAI / Google ship a major model, you have a 72-hour exploitation window. This workflow makes the window productive.
>
> `strategy/capability-radar.md` operational counterpart.

---

## What counts as a "major" model launch

- Model number bumps (Claude 4 → 4.5 → 4.6 → 4.7 → 5)
- DevDay-class announcements with new capabilities
- Pricing changes >20% on a frontier model
- Public benchmark releases showing >10% jumps in vertical-relevant tasks

Skip:
- Minor patches (4.6.1)
- API-only changes that don't shift capability
- Provider-side infra updates without user-facing change

---

## Hour-by-hour playbook

### Hour 0 — first 60 minutes

- **Read the release notes**. All of them. Including the benchmark methodology if relevant.
- **Identify capability shifts that touch your product**:
  - Does this model improve at *your specific task*?
  - Does this model commoditize a feature you were charging for?
  - Does this model unlock a new use case you can serve?
- **Decide**: opportunity or threat? (Sometimes both.)

**Outputs**:
- 1-paragraph internal summary to founder + GTM lead
- 1-line for the X post

### Hour 0-6 — public response

- **Founder X post** with our take. Three formats that work:
  - "Re: [model]. Here's what I think." Direct.
  - "We tested [model] on our customer's use case. Here are 3 things we noticed." Specific.
  - "What [model] means for [your category]." Analytical.
- **Do not**: do a victory lap if it helps you ("now Helmsman is more valuable than ever"). Tone-deaf for AI-native audiences.
- **Do**: be intellectually honest about both opportunity and risk.

### Hour 6-24 — customer communication

- **Email to all customers** with:
  - "We tested [model] on our platform"
  - What changed for them
  - Action they should consider (re-baseline evals? Migrate? Wait?)
  - Our support availability if they want help
- **Slack Connect channels (Enterprise)**: post personalized note in each
- **Blog post** if your analysis goes beyond what fits in an email

### Hour 24-72 — pipeline action

- **Re-score top 50 pipeline accounts** — has the model launch shifted their LLM Maturity Stage? Did anyone just become a fit? Did anyone just become disqualified?
- **Outbound sequence** targeted at accounts whose ICP score improved
- **Re-evaluate Rung 5** of `positioning.md` — does your obsolescence-resistance narrative still hold?

### Day 3-7 — follow-up content

- **Customer case study** featuring the model launch if you have a clean story (Lovable, Modal type)
- **Technical post-mortem** if you discovered something specific about the model
- **Sales-enablement update** for any reps — new talking points for the next 30 days

---

## When the launch is a *threat* (capability commoditizes your wedge)

Different playbook. Goes from offensive to defensive.

### Day 0
- Pause outbound that leans on the now-commoditized wedge. Stop selling something that's about to be free.

### Day 1
- Founder call. Read `strategy/competitors.md` Section 2.4 Emergency Response Playbook.
- Decision: pivot, fight, or sell? Set a 30-day deadline to commit.

### Day 7
- If pivot: identify the new wedge. Often it's the *workflow / data / integration* layer that the foundation model can't replicate.
- If fight: identify the 3 things you do that the foundation model won't do (compliance, multi-model, data moat). Lead with those.
- If sell: start the conversation now while metrics are still good.

### Day 14
- Public-facing positioning update. Don't be silent — silence reads as panic.

---

## Reference example · Claude 4.7 (Helmsman, 2026-04-10)

What we did within 24 hours:
- **Hour 2**: Maya tweeted "Re Claude 4.7 — here's our test on production agent regression. Headline: it's quietly the biggest tool-use jump since 4.0." With chart.
- **Hour 6**: Customer email: "We re-baselined our eval reference set. Highlights: ..."
- **Day 1**: Daniel published methodology doc on the company blog.
- **Day 2**: Re-scored top 50 pipeline. Two accounts upgraded from T3 to T1 because their use cases became viable.
- **Day 3**: Two-customer call about 4.7 migration risks; converted both to higher-tier eval setup.

ROI: 3 new T1 outbound conversations, 2 customer expansions, 1 founder-quoted X thread (12K impressions).

---

## Don't do these (failure modes)

- **Ignoring** the launch. The launch is happening whether you respond or not.
- **Marketing-heavy response** ("our product is more valuable than ever!"). AI-native readers smell desperation.
- **Comparing yourself unfavorably** to the foundation model. They're the platform; you're an app. Different shape.
- **Updating product positioning the same day**. Take 48 hours to think.
