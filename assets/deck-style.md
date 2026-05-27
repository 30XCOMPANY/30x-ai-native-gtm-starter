# assets/deck-style.md · Deck template rules

> How decks look in this brand. Read after `design.md`. `skills/deck-build` references both files.

---

## Aspect ratio + size

- **16:9** (standard). Width 1920px export.
- **4:5** vertical decks only for short-form social.

---

## Slide masters

A working deck has only six master types. Don't invent new layouts on the fly.

### 1. Cover
- Title (h1, max 12 words)
- Eyebrow (mono caps, ≤4 words)
- Date / venue / audience (mono tiny)
- Logo bottom-left, page number bottom-right

### 2. Section divider
- Single large word (serif italic optional)
- Number top-left (`01 / 04`)
- Color-backed panel (sky / orange / purple)

### 3. Headline + body
- H2 (≤10 words) top
- 1 paragraph body OR 2–4 bullets — NEVER both
- Plenty of whitespace below — no need to fill

### 4. Stat / metric slide
- One big number (h1, possibly numeric, mono-tiny)
- One label (mono caps)
- One context sentence below
- Use this slide TYPE for proofs — "we have N customers", "X% conversion", etc.

### 5. Diagram / illustration
- One central diagram, max 12 elements
- 2-line caption max
- Use accent colors from `design.md` consistently

### 6. CTA / close
- One single ask (action verb + object)
- Founder name + email/URL
- No phone tree, no calendar QR — one decision

---

## Universal slide rules

- **Never more than 3 colors per slide.** Pick from `design.md` palette.
- **Never more than 30 words per slide.** Read the audience, not the slide.
- **Page number bottom-right.** Mono tiny.
- **Logo bottom-left.** SVG inline. Same size every slide.
- **No "Thank you / Q&A" slide.** Last slide is a CTA, not an apology.

---

## Build-mode behavior

When `skills/deck-build` produces a deck, it must:

1. Pick the right number of slides (default 8–12; if >15, push back)
2. Start with cover, end with CTA — bookended
3. Lead with the headline that's most counterintuitive (audience-tailored)
4. Use at minimum one stat slide and one diagram slide
5. Save to `assets/decks/YYYY-MM-DD-{audience}-{purpose}.{pptx|key}`
6. Generate a `.md` companion file with speaker notes per slide

---

## When to use which color theme

| Audience / setting | Primary palette | Accent |
|---|---|---|
| Engineering teams | paper + ink | sky |
| Enterprise sales | paper + ink | orange |
| Pitch (investor) | paper + ink | orange-deep |
| Partner BD | paper + ink | purple |
| Internal team | paper + ink | green |

Don't mix accents within one deck.

---

## Common failures (don't ship these)

- A 30-slide deck for a 15-min meeting
- Wall of bullets
- Stock photo of "diverse business people pointing at laptop"
- Logo soup as social proof on slide 2 (when you can't yet validate)
- Pricing slide buried behind 10 build-up slides — show it on slide 3 if it's the question

---

## Deck library log

Maintain `assets/decks/README.md` listing every deck with:
- Date
- Audience
- Purpose
- Outcome (won / lost / no-decision)
- What worked
- Speaker notes URL

---

> **[PROTOCOL]**: When `design.md` changes, audit all decks in `assets/decks/` and re-export the outdated ones. The `skills/deck-build` skill must read both files at runtime.
