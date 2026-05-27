# Playbook · Direct Competitor Ships Your Wedge

> Emergency response when a named competitor announces / ships a feature that overlaps your core differentiation.
>
> Triggered when: `weekly-drift-audit` flags a direct competitor's product launch matching your category, OR you see it in real-time.

---

## Hour 0 — 60 minutes

**Don't react publicly yet.** First, internal assessment:

1. Read their launch material. All of it. Including documentation, not just the blog.
2. **Test their product if possible** — sign up for trial, run on a test case you know yours handles well.
3. **Identify what they actually shipped vs what they claimed**:
   - Marketing fluff vs working feature
   - Partial implementation vs full equivalence
   - Their dependencies (which model? which infrastructure?)
4. **Identify what's STILL different about you**:
   - Different model coverage?
   - Different deployment options?
   - Different workflow integrations?
   - Different pricing model?
   - Different customer shape they don't serve?

**Output**: a 3-bullet internal note: "they shipped X. We still win on Y, Z, W."

---

## Hour 1-6 — internal response

**Founder + GTM call**:
- Read the 3-bullet assessment
- Decide: which of Y/Z/W becomes our new positioning lead?
- Schedule the public response (don't post on impulse)
- Update `context/competitor-radar.md` Section 1 card immediately

**Don't**:
- Panic-DM the team to "kill it" — generates noise without action
- Tell sales reps "talk to customers about this now" — give them the messaging first
- Update marketing site that hour — too rushed

---

## Hour 6-24 — public response

Three formats that work, in priority order:

### Format A · Acknowledge + reframe
> "[Competitor] shipped [feature]. Genuinely interesting work. The way we approach [problem] is different in [specific way that matters to your ICP]. Here's why: [substance]."

Acknowledges them (high road), then reframes around what makes you different. AI-native audiences respect candor.

### Format B · Customer-evidenced comparison
> "Saw [competitor] shipped [feature]. Our customers asked, so we ran a comparison: [link to public benchmark / write-up]. Tl;dr: they win on [X], we win on [Y]. Pick by use case."

This is the most credible response — it's not marketing, it's analysis. Requires the analysis to be honest.

### Format C · Silence + product velocity
> No public response. Ship your next feature within 7 days that highlights your unique angle.

Highest-confidence move if you have something genuinely shipping that they can't.

**Do NOT**:
- Post a "we've always done that better" tweet without evidence
- Quote-tweet their launch with snark
- Email customers with "don't worry about [competitor]" — that's a tell

---

## Day 1-7 — customer reach-out

**Tier customers by exposure**:

- **Customers actively evaluating both you and them**: personal email from founder within 48h, offer to do a side-by-side eval on their use case
- **Customers who've expressed mild curiosity about competitor**: include 1-paragraph honest comparison in their next monthly check-in
- **Customers who don't know / don't care**: don't mention it; they'll find out only if it matters to them

---

## Day 7-30 — strategic moves

Based on the 3-bullet assessment, choose:

### Move 1 · Sharpen positioning
Update `context/positioning.md` to lead with the specific axis where you still win. Update landing page hero within 30 days.

### Move 2 · Ship the differentiator faster
If your roadmap has a feature that widens the gap, prioritize it. The launch is your reminder to ship.

### Move 3 · Concede the overlap, expand the surface
Accept that you lose on the overlapping feature. Build adjacent capability that this competitor can't easily copy. Often the right answer when their feature is genuinely good.

### Move 4 · Partner where you'd otherwise compete
Sometimes the right answer is to integrate with them. Counterintuitive but real — Langfuse + Helmsman is a case where the OSS observability tool and the managed eval tool both benefit from acknowledging the overlap.

---

## What to update afterward

- `context/competitor-radar.md` Section 1 card (the competitor's "Recent product moves")
- `context/positioning.md` if your lead positioning shifts
- `context/icp-definition.md` if your ICP gets sharper as a result
- `outputs/YYYY-MM-DD-competitor-response.md` — log what you did and why; future-you needs the reasoning

---

## Anti-patterns

- **Reactive product roadmap**: don't add a feature in week 2 *just because* the competitor shipped one. If your roadmap had it on the 2027 list and it gets bumped to 2026-Q3, that's fine. If you add a brand new project the team didn't plan for, that's flailing.
- **Marketing arms race**: don't enter a "who's better?" public debate. AI-native audiences read this as low-status.
- **Telling reps to "go on the offensive"**: give reps the *substantive* talking points; let them have organic conversations with customers.

---

## Reference example · Braintrust Auto-Eval v2 (Helmsman, 2026-04-30)

What we did:
- **Hour 1**: Daniel tested Auto-Eval v2 on a representative trace. Found: dev-time only; doesn't catch the multi-tenant production cases we handle.
- **Hour 4**: 3-bullet internal note: "They shipped dev-time auto-eval. We still win on multi-tenant production reliability + cross-model drift + remediation workflow."
- **Hour 24**: Maya tweeted Format A response acknowledging Braintrust's work, reframing around production reliability.
- **Day 1**: Updated `context/competitor-radar.md` Braintrust card with detailed Recent Product Moves section.
- **Day 3**: Published comparison blog: "When to use Braintrust vs Helmsman" — honest, customer-utility-focused.
- **Day 7**: Updated positioning.md to lead with "production reliability" as the headline; dev-time eval becomes a feature, not the headline.
- **Day 14**: Shipped multi-tenant baseline feature publicly — widens the gap.

Outcome: No customer churn from the launch. One pending T2 evaluator converted to us specifically because of the honest comparison post.
