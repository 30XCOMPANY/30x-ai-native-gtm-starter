# Sequence · MCP Server Publisher × Stage 3-4 AI Startup

> Example sequence for AI-native companies that just shipped an MCP server. Signal source: `pipeline/signals.md` B6.
>
> Status: **example only**. Replace with your real sequences. Track reply rate; kill if <8% after 30 sends.

---

## When to send

Triggered by a B6 signal (new MCP server published in your category) AND the publishing org passes ICP hard qualifiers (Stage 3-4 LLM Maturity, target industry).

**Hot window**: 7 days after MCP publication. After day 14, switch to a different signal angle.

---

## Cadence

| # | Day | Channel | Word cap | Goal |
|---|---|---|---|---|
| 1 | 0 | Founder DM on X | 50 | Signal-specific first contact |
| 2 | 4 | Email | 60 | Provide value (no ask) |
| 3 | 10 | Email | 40 | Direct ask (single Y/N) |
| 4 | 24 | Email | 30 | Break-up (acknowledges silence, low pressure) |

---

## Touch 1 · Day 0 · Founder DM on X

> Sent from founder's account (not a sequencing tool). Personal.

```
{first_name} —

Saw {their_org}/{repo}-mcp went up. Curious — how are you handling agent-initiated session quality vs human-initiated? That bifurcation is where most teams hit a wall.

Built [our product] for exactly that shape. Repo (open): github.com/[us]/[repo]

If interesting, happy to do 15 min next week.
```

**Why this works**:
- First line references the actual signal (the MCP server)
- One specific technical question shows we've read their work
- "If interesting" gives them a graceful exit
- No marketing language

---

## Touch 2 · Day 4 · Email · provide value

```
Subject: that thing about agent-initiated quality

{first_name},

Followed up on the MCP server thread. Wrote up the metric question more carefully here:
{link to your blog post or research file on agent-initiated session retention}

Tldr: most teams treat "user opened app" and "agent invoked tool" as one funnel. The retention curves look very different — agent users churn 3-5x faster in our data.

No ask, just thought you'd find it useful.
```

**Why this works**:
- Subject is conversational (lowercase, no clickbait)
- References Touch 1 without restating it
- Gives away a real insight (not gated content)
- Explicit "no ask" — reduces defensiveness

---

## Touch 3 · Day 10 · Email · direct ask

```
Subject: 15 min next week?

{first_name},

Two questions if you have a sec:

1. Is the agent-session quality thing actually a problem you're feeling, or is it noise?
2. If yes, want to compare notes? 15 min.

Either answer is fine.
```

**Why this works**:
- One clear ask
- Binary question, easy to answer (especially "no")
- "Either answer is fine" removes the social pressure that kills replies

---

## Touch 4 · Day 24 · Email · break-up

```
Subject: closing this loop

{first_name},

Last one from me — I'll stop unless you say otherwise.

If you ever do want to compare notes on the agent-quality problem, the door's open: {your_email}.

Best of luck with {their_org}.
```

**Why this works**:
- "Last one from me" is a real signal, not a fake one
- No CTA pressure
- Leaves the door open without begging
- Wishes them well — costs nothing, builds reputation

---

## Anti-patterns explicitly avoided

- ❌ "I hope this finds you well"
- ❌ "I came across your company and was impressed by..."
- ❌ Two CTAs in one email
- ❌ Pasted product feature list
- ❌ Calendar link before they've shown interest
- ❌ Following up 7 times — by Touch 5 you're spam

---

## Variants to A/B test

**Variant A (Touch 1)**: technical question first (current version)
**Variant B (Touch 1)**: shared connection ("Saw [X] commented on your launch — we're working on adjacent problem...")
**Variant C (Touch 1)**: customer quote ("X at Y had same shape problem, here's how they solved it — open to chat?")

Test 10 sends each. Pick winner by reply rate after 3 weeks.

---

## Expected metrics

| Metric | Target | Kill criteria |
|---|---|---|
| Touch 1 reply rate | 15-25% | <8% over 30 sends → rewrite Touch 1 |
| Touch 2 → meeting | 5-8% | <3% → drop the value email |
| Touch 3 → meeting | 2-5% | <1% → kill sequence |
| Overall meeting booked | 8-15% | <5% → kill |

---

## Deliverability notes

- Send from a warmed domain (not founder@30xcompany.com directly if you're at-scale)
- Personalize first name + org name only (NOT 5 mail-merge fields — looks templated)
- Max 30 sends per day per sending address
- Reply-to: real human inbox monitored daily
