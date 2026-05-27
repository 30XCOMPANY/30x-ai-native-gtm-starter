# assets/design.md · Visual brand system

> The rules every visual asset obeys. Read once, internalize. Every deck, one-pager, illustration, and landing page references this file.

---

## Color

### Primary palette

| Token | Hex | When to use |
|---|---|---|
| `paper` | `#FBF9F4` | Default page / slide background |
| `ink` | `#0F0E13` | Primary text, dark accents, ink borders |
| `ink-soft` | `#56535E` | Secondary text, captions |
| `washed` | `#EFEBE0` | Sunken surfaces, code blocks |

### Accent palette (use one per surface, not all together)

| Token | Hex | Mood |
|---|---|---|
| `sky` | `#C8E4F3` | Trustworthy, technical |
| `orange` | `#F0B080` | Warmth, urgency |
| `purple` | `#C7BCE6` | Sophistication, optionality |
| `green` | `#B6D5B0` | Growth, customers |
| `orange-deep` | `#BE5722` | Strong accent (used sparingly — links, callouts, errors) |

### Rules

- **Never** pure `#000` or `#FFF`. Use `ink` and `paper`.
- **Max two accents per surface.** Sky + orange is the default if a deck spans both serious + warm.
- **Backgrounds**: paper or accent-tinted, never gradient-pure unless making a hero.
- **Borders**: 1–1.5px solid `ink`. No greys for borders.

---

## Typography

### Families

- **Sans**: [Public Sans](https://fonts.google.com/specimen/Public+Sans) — UI, body, headlines
- **Serif**: [Instrument Serif](https://fonts.google.com/specimen/Instrument+Serif) — italic accent only, one or two words per heading at most
- **Mono**: [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) — code, captions, micro-labels

### Type scale

| Token | Size (px) | Weight | Letter-spacing | When |
|---|---|---|---|---|
| `h1` | 56–92 (clamp) | 500 | -0.028em | Hero / cover only |
| `h2` | 32–56 (clamp) | 500 | -0.025em | Section headings |
| `h3` | 18–22 | 500 | -0.02em | Sub-headings |
| `body` | 16 | 400 | -0.006em | Default body |
| `body-sm` | 14 | 400 | -0.005em | Captions, secondary text |
| `eyebrow` | 11 | 500–600 | 0.16em uppercase | Section labels |
| `mono-tiny` | 10–11 | 500 | 0.06em | Tags, metadata |

### Rules

- **Font weight cap: 500.** No 600+ except brand wordmark.
- **Hierarchy via size + color**, not weight stacking.
- **Italic = serif only.** Never italicize Public Sans.
- **All caps = mono only**, with letter-spacing.
- **Line-height**: 1.05 for headings, 1.5 for body, 1.6 for long-form blog body.
- **Headlines under 12 words.** No colons unless necessary.

---

## Spacing

8-point scale. Multiples of 8 only.

| Token | Px | Use |
|---|---|---|
| `s-1` | 8 | Inline, dense |
| `s-2` | 16 | Default gap |
| `s-3` | 24 | Section internal padding |
| `s-4` | 32 | Between cards |
| `s-6` | 48 | Block separation |
| `s-8` | 64 | Section separation (mobile) |
| `s-12` | 96 | Section separation (desktop) |

### Rules

- Vertical rhythm > horizontal cleverness.
- 16px is the most-common gap. Don't second-guess it.
- Asymmetric margins are fine — but pick one rhythm and stick to it per layout.

---

## Border radius

| Token | Px | Use |
|---|---|---|
| `r-s` | 8 | Inline chips, small buttons |
| `r-m` | 14 | Cards, inputs |
| `r-l` | 22 | Larger cards, code blocks |
| `r-xl` | 32 | Hero panels, full-width sections |

### Rules

- One radius per element type. Don't mix 8 and 14 in the same card.
- Larger surfaces = larger radius. Pills (999px) only for tags and rounded buttons.

---

## Iconography

- **System**: [Lucide](https://lucide.dev) (`width=1.5` stroke, no fill)
- **Sizes**: 14, 16, 20, 24 (match text line-height)
- **Color**: inherit `currentColor` — never hard-code

No emoji as UI elements. No emoji in formal copy (decks, one-pagers).

---

## Motion

When motion is used, use these durations + easings:

| Type | Duration | Easing |
|---|---|---|
| Hover lift / fade | 200ms | `cubic-bezier(0.16, 1, 0.3, 1)` (out-expo) |
| Scroll-reveal | 900ms | same |
| Snap / pop | 400ms | `cubic-bezier(0.5, 1.6, 0.5, 1)` (back-out) |
| Marquee / orbit | 30s+ | linear |

### Rules

- **Always respect `prefers-reduced-motion`.**
- No bouncing logos, no flashing, no rotating heroes unless intentional.
- Motion is a tool to direct attention, not a decoration.

---

## Imagery

- **Photos**: avoid stock. Either real customer/team photos or none.
- **Illustrations**: editorial flat — thin line work + 1–2 accent colors max. No 3D, no gradients, no glow.
- **Charts**: ink + one accent. Labels in mono. Don't dual-axis unless absolutely needed.

---

## Do / Don't quick reference

### Do
- Use `paper` background everywhere unless you have a reason
- Use serif italic as a *single* accent per page
- Ship code, screenshots, real numbers
- Honor the 8pt grid

### Don't
- Use pure black or pure white
- Mix two display fonts
- Use shadow > `var(--shadow-md)` (we have a defined max)
- Stack font weights above 500
- Use stock illustrations or emoji as design elements
- Animate without `prefers-reduced-motion` fallback

---

> **[PROTOCOL]**: This file is binding for `skills/deck-build`, `skills/one-pager-build`, and any landing-page work. When the brand evolves, this file is the source of truth — update here first, then propagate.
