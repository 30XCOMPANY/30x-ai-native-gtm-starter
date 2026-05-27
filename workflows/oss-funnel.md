# Workflow · OSS Community → Customer Funnel

> For humans, not Claude. Decision tree for how an open-source user becomes a paying customer.
>
> Implements Constitution #3 (Community → Customer Funnel). Operationalized by skill `oss-pipeline-track`.

---

## The funnel stages

```
Aware (star) → Active (Discord/clone) → Engaged (issue/PR) → Trial → Paid → Enterprise
```

Industry benchmarks for AI-native OSS funnels (rough; varies by category):

- Aware → Active: 8-15%
- Active → Engaged: 5-12%
- Engaged → Trial: 15-30%
- Trial → Paid: 8-20%
- Paid → Enterprise: 5-15%

**Multiply these together** and you get end-to-end OSS → Enterprise conversion of ~0.001-0.01%. Which is why **stage-by-stage measurement matters** — you can't optimize an end-to-end number this small, only stage-to-stage.

---

## Stage 1 · Aware (GitHub Star)

**What "Aware" means**: user starred your repo. May or may not have read the README.

**How to advance them to Active**:
- README has a "5-minute quickstart" up top
- README has a "Try this in your browser" link (Replit / CodeSandbox / playground)
- Discord / community invite linked from README *above* the fold
- Recent commits visible (they're checking; an active repo says "this isn't abandoned")

**Don't**:
- Track who starred and email them. Mass-DM is anti-pattern for AI-native devs.
- Run conversion ads. Wrong funnel.

**Metric to track**: stars → Active conversion rate, weekly.

---

## Stage 2 · Active (Discord member OR repo clone OR docs visit)

**What "Active" means**: they did *something* beyond starring. Joined Discord, cloned the repo, visited docs more than once.

**How to advance them to Engaged**:
- Discord has clear "introductions" channel with template — gives lurkers a first-post template
- Issue templates that make it easy to file good bugs
- "Good first issue" labels on real (not-too-hard) work
- Weekly "office hours" Discord call announced in #announcements
- Bi-weekly digest of community activity sent to Discord

**Don't**:
- Auto-DM new Discord joiners
- Surveys / forms with >2 questions
- Webinars with registration gates

**Metric**: Active 30-day → Engaged conversion rate.

---

## Stage 3 · Engaged (filed issue / opened PR / commented in discussion)

**What "Engaged" means**: they care enough to write something. This is the high-value pool.

**How to advance them to Trial**:
- Respond to every issue / PR within 24h (founder-grade response, not bot)
- When relevant, mention the managed offering in the issue resolution — *only when the issue itself reveals the use case where managed wins*
- Founder DMs (personal, not template) to engaged users who match ICP — at most 2 per week, max
- Public showcase: feature engaged user's work in monthly community post

**Mass-action anti-pattern**: do NOT email all engaged users with "try our managed product." Engaged users are sophisticated; mass touch poisons the relationship.

**Metric**: Engaged → Trial conversion + DM-touch reply rate.

---

## Stage 4 · Trial (signed up, hasn't paid)

**What "Trial" means**: they created an account on your managed product.

**How to advance them to Paid**:
- First-week activation checklist: did they do the 3 things that correlate with conversion?
- Day 7: human-written email (not template) asking what's missing
- Day 14: founder-grade follow-up if still inactive
- Pricing visible without log-in (this matters for AI-native — they verify pricing before committing)

**Don't**:
- 7-email drip sequence. Two human-written follow-ups beats six automated ones.
- Push-notify the in-product UI to upgrade. Annoyance kills.

**Metric**: 14-day trial → paid conversion, by signup source.

---

## Stage 5 · Paid (active subscription, low tier)

**How to advance to Enterprise**:
- Usage telemetry shows when they're approaching tier limits
- Outreach when usage crosses 70% of tier — "want to talk about scaling?"
- Enterprise expansion happens at *real* moments, not arbitrary calendar days:
  - New compliance requirement from their customer (need VPC)
  - Team-size growth that crosses seat limits
  - Multi-environment need (staging + prod separate)
  - Custom SLA / dedicated CSM ask

**Don't**:
- Quarterly business reviews with no purpose. Waste both sides' time.
- Push Enterprise on customers who don't need it. The expansion conversation must answer "what NEW outcome do you get."

**Metric**: Paid → Enterprise conversion, time-to-expansion.

---

## Stage 6 · Enterprise

**Retention is the new acquisition.** Enterprise customers churn slower but harder — when they go, they take a public-relations hit with them.

- Dedicated Slack Connect channel
- Monthly check-in with their internal champion
- Quarterly success review against their stated success metrics
- Capability obsolescence transparency — proactively tell them when foundation model changes affect their use case

---

## Stage-to-stage diagnostics

Use this to diagnose where your funnel is broken:

| Symptom | Likely problem | Action |
|---|---|---|
| High stars, low Discord | README missing community invite, or community looks dead | Fix README; seed Discord conversations |
| High Discord, low issues | No "good first issue" labels; community feels passive | Make contribution paths obvious |
| High issues, low trial | Free CLI satisfies them; no clear "managed wins here" moment | Add visible managed-wins use cases to docs |
| High trial, low paid | Activation broken in first 7 days | Audit first-run UX with 3 users |
| High paid, low Enterprise | No clear expansion trigger | Document the "you need Enterprise when X" criteria |

---

## Run this monthly

The `skills/oss-pipeline-track` skill automates the measurement. The human work is **interpreting the bottleneck** and **deciding what experiment to run next month** to unblock it.

One experiment per month. Don't change three things at once — you won't know what worked.
