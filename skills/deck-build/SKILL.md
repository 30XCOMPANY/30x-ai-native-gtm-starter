---
name: deck-build
description: Build a presentation deck (Markdown / Reveal / PPTX-ready). Reads `assets/design.md` for visual rules, `assets/deck-style.md` for slide patterns, and `strategy/` for content. Outputs a slide-by-slide markdown spec with speaker notes, ready for export.
---

# Skill · deck-build

## What this does

Generates a complete deck for a specific audience + purpose. Reads:
- `assets/design.md` — visual rules (color, type, spacing)
- `assets/deck-style.md` — slide patterns + master types
- `strategy/positioning.md`, `strategy/icp.md` — what to say
- `strategy/brand.md` — how to say it

Outputs:
- `assets/decks/YYYY-MM-DD-{audience}-{purpose}.md` — full slide spec
- Same path with `.speaker-notes.md` — what to say per slide
- (Optional) `.pptx` via export tool

## How to invoke

```
deck-build: pitch deck for [audience] · purpose [why we're presenting] · [N] slides · [duration]min
```

Examples:
- `deck-build: pitch deck for Series-A investors · purpose raise · 12 slides · 20min`
- `deck-build: partner deck for Vercel BD team · purpose integration · 8 slides · 15min`
- `deck-build: sales discovery deck for AI infra startups · purpose first meeting · 10 slides · 30min`

## Steps Claude takes

1. **Read context**:
   - `assets/design.md` (palette, type, motion rules)
   - `assets/deck-style.md` (master types, color-by-audience)
   - `strategy/positioning.md`, `strategy/icp.md`, `strategy/brand.md`
   - `strategy/competitors.md` if pitch is competitive
   - `pipeline/customers.md` if logos / case studies needed

2. **Pick the right number of slides** based on duration:
   - 15 min → 6–8 slides
   - 20 min → 8–12 slides
   - 30 min → 10–14 slides
   - 60 min → 14–20 slides (use section dividers)

3. **Pick the right color theme** from `deck-style.md`:
   - Engineering audience → sky
   - Enterprise sales → orange
   - Investor pitch → orange-deep
   - Partner BD → purple
   - Internal → green

4. **Generate slide spec** as markdown, using this format:

```markdown
# Deck · [Title]
- Audience: [target]
- Purpose: [why]
- Duration: [min]
- Theme: [color from design.md]

---

## Slide 1 · Cover
- **Master**: cover
- **Title**: [h1, ≤12 words]
- **Eyebrow**: [mono caps, ≤4 words]
- **Meta**: [date / venue / audience]
- **Visual**: logo bottom-left, page 1/N bottom-right

## Slide 2 · Section divider OR Headline+body
...
```

5. **Generate speaker notes** for each slide:
   - 1-2 sentences of what to actually say
   - Highlight the ONE thing the audience must walk away with
   - Note objections that might come up + where to defer them

6. **Bookend the deck**:
   - Cover first slide
   - CTA last slide (NEVER a "Thank you / Q&A" slide)

7. **Save outputs**:
   - `assets/decks/YYYY-MM-DD-{audience}-{purpose}.md`
   - `assets/decks/YYYY-MM-DD-{audience}-{purpose}.speaker-notes.md`
   - Append entry to `assets/decks/README.md` (deck library log)

8. **If user requests `.pptx` export**:
   - Use `pandoc` or `marp` to convert (offer command)
   - Or output a `marp` directive at the top of the spec

## Quality filters before delivering

- [ ] Cover + CTA bookend present
- [ ] ≥1 stat slide + ≥1 diagram slide
- [ ] ≤30 words per slide (excluding speaker notes)
- [ ] ≤3 colors per slide (from `design.md` palette)
- [ ] No "AI-powered", "best-in-class", "Excited to announce"
- [ ] Logo placement consistent across slides
- [ ] Page numbers on every non-cover slide
- [ ] Brand voice from `strategy/brand.md` obeyed

If any fails: rewrite that slide. Don't deliver a draft with known issues.

## Anti-patterns

- Don't produce more slides than asked. 12 means 12.
- Don't ever use stock photos.
- Don't insert "Q&A" slide; the deck ends on a CTA.
- Don't show a competitive landscape slide (with 2x2 quadrant) — these are universally meh.
- Don't bury pricing if pricing is what they came to hear.

## Trace to architecture

This skill sits at the intersection of:
- `strategy/` (what to say)
- `assets/design.md` + `deck-style.md` (how it looks)
- `outputs/` AND `assets/decks/` (where it lives)
