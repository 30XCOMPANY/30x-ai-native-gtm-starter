---
name: outbound-sequence
description: Generate a multi-touch outbound sequence (4–7 touches) tied to a specific signal + ICP. Reads `pipeline/signals.md`, `strategy/icp.md`, `strategy/brand.md`. Outputs sequence spec ready to load into Instantly / lemlist / Smartlead.
---

# Skill · outbound-sequence

## What this does

Build a tested-pattern outbound sequence for one signal type × one ICP segment. Not generic cold spray — each touch references the specific signal that fired.

## How to invoke

```
outbound-sequence: [signal name] · [ICP segment] · [N touches] · [channel: email|linkedin|x|mixed]
```

Examples:
- `outbound-sequence: GitHub stars velocity · Stage 3-4 AI infra · 4 touches · email`
- `outbound-sequence: MCP server published · Series A AI startups · 5 touches · mixed`
- `outbound-sequence: Foundation model release · existing customers (expansion) · 3 touches · email`

## Steps Claude takes

1. **Read context**:
   - `pipeline/signals.md` — the signal definition + hook template
   - `strategy/icp.md` — the segment qualifiers
   - `strategy/personas.md` — the buyer profile
   - `strategy/brand.md` — voice rules
   - `pipeline/objections.md` — anticipated pushback

2. **Pick the cadence**:

   | Touches | Spacing | Total | Best for |
   |---|---|---|---|
   | 3 | day 1, day 5, day 12 | 12 days | Hot signal, short window |
   | 4 | day 1, day 4, day 9, day 18 | 18 days | Standard outbound |
   | 5 | day 1, day 3, day 7, day 14, day 24 | 24 days | High-ACV enterprise |
   | 7 | weekly | 6 weeks | Very long sales cycle |

3. **Generate each touch** following these rules:

   - **Touch 1**: 60-word max. Signal-specific in first line. One specific outcome. One CTA.
   - **Touch 2**: 40-word max. Different angle (not "just checking in"). Reference a related signal or piece of content.
   - **Touch 3**: 50-word max. Provide value (link to relevant research / case / one-pager) — no ask.
   - **Touch 4**: 30-word max. Direct ask. Single yes/no question.
   - **Touch 5+**: optional break-up email (acknowledges silence, no guilt).

4. **Quality filters per touch**:
   - [ ] Signal-tied first line
   - [ ] No "Hope you're well" / "I came across your company"
   - [ ] No marketing adjectives
   - [ ] One CTA, never two
   - [ ] Word count cap respected

5. **Generate variant set** if requested:
   - A/B variant for touch 1 (different opening angle)
   - Persona variant (engineer vs PM) — different vocabulary

6. **Save outputs**:
   - `pipeline/sequences/YYYY-MM-DD-{signal-slug}-{icp-slug}.md`
   - Include: cadence diagram, all touches in order, deliverability notes, expected reply rate range

## Format of the output spec

```markdown
# Sequence · [Signal] × [ICP] · [Date]

## Cadence
[Diagram showing day-by-day]

## Touch 1 · Day 1 · Email
Subject: [subject line]
Body:
[body]

Why this works: [1 line]

## Touch 2 · Day 4 · Email
...

## Deliverability notes
- Send from: [warmed domain, not founder@30xcompany.com directly]
- Volume: [max sends/day to maintain reputation]
- Reply-to: [setup details]

## Expected metrics
- Open rate: X% target
- Reply rate: X% target
- Meeting booked: X% target
- Kill criteria: if <X% reply after 30 sends, kill this sequence
```

## Anti-patterns

- Don't write "Hi {first_name}, I hope this finds you well." This is the cold-email plague.
- Don't reference a signal that isn't really fresh (>14 days = no longer fresh).
- Don't ask for a 30-min meeting in touch 1. Ask for 15.
- Don't include 2+ CTAs in one email — kills response rate.
- Don't write a sequence longer than the signal's useful window (per `pipeline/signals.md` decay table).

## Trace to architecture

Reads from: `pipeline/signals.md`, `strategy/icp.md` + `personas.md` + `brand.md`
Writes to: `pipeline/sequences/`
