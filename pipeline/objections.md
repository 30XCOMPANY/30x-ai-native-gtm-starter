# pipeline/objections.md · Objection handling

> Tested responses to common pushback. Update when a new pattern emerges.

---

## Schema

```
### Objection
> "[Quote of how prospects phrase it]"

**Translation** (what they actually mean): [...]

**Response** (tested): [...]

**Follow-up question**: [...]

**When this is a real DQ (don't push)**: [...]
```

---

## Common objections (template — fill from your reality)

### Objection: "Can't you just be wrapped by OpenAI's next release?"
> _Common from AI-curious technical buyers_

**Translation**: They want to verify our moat isn't temporary prompt engineering.

**Response**: Tell them our specific moat (multi-model / data network effect / compliance / integration depth) and point to `strategy/capability-radar.md` Section 2 self-assessment. Acknowledge the risk; show the work.

**Follow-up question**: "What's the foundation model release that would worry you most?" — surfaces their threat model so we can address it specifically.

**When this is real DQ**: If our moat is genuinely just prompt engineering, walk away from this deal honestly. They'll churn.

---

### Objection: "Why not just build this in-house?"
> _Common from technically capable buyers_

**Translation**: They're estimating build vs buy cost.

**Response**: Use specific data — our customers spent N engineer-months building before switching, the integration breadth would cost them M more, our weekly updates compound. Don't argue ROI in the abstract.

**Follow-up question**: "What's your AI engineering team focused on for the next quarter?" — if they have a roadmap that doesn't include this, build vs buy is decided.

**When this is real DQ**: If they have 3+ AI engineers and a clear roadmap to build, they will build. Move on.

---

### Objection: "We need to wait for [framework / standard / model release]"
> _Common stalling tactic_

**Translation**: Lower-priority than other initiatives.

**Response**: Quantify cost of waiting in their specific terms. If they're losing N% per quarter to capability drift, waiting two quarters is M. Show them the math.

**Follow-up question**: "What event would un-stall this?" — if they can name it, plan around it; if not, it's stuck.

---

### Objection: "Pricing is too high"
> _The most common_

**Translation**: One of three things — (1) ROI not clear, (2) tier mismatch with team size, (3) genuine budget issue.

**Response**: Discover which one. Don't discount before knowing.

**Follow-up question**: "If pricing were [X% lower], would you sign this week?" — surfaces whether price is real or scapegoat.

**When this is real DQ**: If their LLM API spend is <$5K/mo, they're not at the maturity stage for our product. Refer to free tier; revisit in 6 months.

---

## Your additions

> Add objections as they emerge in real calls. One a quarter is normal.

### Objection: [...]
**Translation**: 
**Response**: 
**Follow-up question**: 
**When this is real DQ**: 

---

> **[PROTOCOL]**: Run `skills/objection-handle` when a new objection appears to draft a tested response. Don't write from scratch each call.
