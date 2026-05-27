---
name: one-pager-build
description: Build a one-pager (single-page PDF / web page) targeted at one ICP + one use case. Reads `assets/design.md` and `strategy/`. Outputs Markdown spec ready for design or direct PDF export.
---

# Skill · one-pager-build

## What this does

Produces a single-page deliverable for a specific audience. A one-pager is what a seller emails *after* a call ("here's the summary") or hands at an event. It is NOT a deck condensation — it has its own shape.

## How to invoke

```
one-pager-build: [audience] · [use case] · [tone serious|warm|technical]
```

Examples:
- `one-pager-build: AI infra startups · cost-aware multi-model evals · technical`
- `one-pager-build: Series-B SaaS · production AI feature reliability · serious`
- `one-pager-build: enterprise GC / compliance · VPC deployment · serious`

## Steps Claude takes

1. **Read context**:
   - `assets/design.md`
   - `strategy/positioning.md`, `strategy/icp.md`, `strategy/personas.md`
   - `strategy/brand.md`
   - `pipeline/customers.md` (for proofs)

2. **Pick the layout** (one of three):

   **A. The Problem / Solution one-pager**
   ```
   Eyebrow:    [pillar from content/strategy.md]
   Headline:   [thesis in 8 words]
   Sub:        [1 paragraph context]
   3-column:   [Problem 1 / 2 / 3 with metric each]
   Solution:   [1 paragraph + 1 image/diagram]
   Proof:      [1 customer quote + 2 metrics]
   CTA:        [single action verb + URL]
   ```

   **B. The Story one-pager**
   ```
   Eyebrow:    [category]
   Headline:   [statement]
   Story arc:  Before → Interrupt → After (3 paragraphs)
   Proof:      [1 customer quote]
   CTA:        [single action]
   ```

   **C. The Comparison one-pager**
   ```
   Eyebrow:    [category]
   Headline:   [why we're different in 6 words]
   Comparison table: 5 rows × 3 columns (us vs A vs B)
   Note:      [1 paragraph honest acknowledgment of trade-offs]
   CTA:       [single action]
   ```

3. **Pick the color theme** matching the audience (same logic as `deck-build`).

4. **Generate the markdown spec** with the layout filled in:
   - Real numbers (cite source if from research)
   - Real customer quote (anonymize if not public)
   - Real diagram if applicable (otherwise leave a `<!-- diagram: ... -->` placeholder)

5. **Quality check**:
   - [ ] Single CTA (one action, one URL)
   - [ ] Numbers are real, not invented
   - [ ] No more than 200 words total body
   - [ ] At least one specific proof (quote, metric, named customer)
   - [ ] Honors `strategy/brand.md` voice

6. **Save outputs**:
   - `assets/one-pagers/YYYY-MM-DD-{audience}-{slug}.md`
   - Append entry to `assets/one-pagers/README.md` (one-pager library log)

## Anti-patterns

- Don't write a one-pager that's actually a 4-page brochure. One page = one decision.
- Don't include "Learn more" + "Book a demo" + "Read the docs" as three CTAs. Pick one.
- Don't use stock illustration for the diagram. Use a real diagram from `assets/illustrations/` or none.
- Don't generate one for "general audience". One-pagers are sharpest when targeted.

## Trace to architecture

Reads from: `strategy/`, `assets/design.md`
Writes to: `assets/one-pagers/`, `outputs/`
