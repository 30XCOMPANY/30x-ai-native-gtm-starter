---
name: signal-to-content
description: Convert a fired signal (from `context/signal-library.md`) into shippable content — blog post, X thread, launch post, or short video script. Designed for the Lovable / Bolt / Cursor pattern where founder-led content IS the distribution channel.
---

# Skill · signal-to-content

## What this does

The Lovable + Bolt model from `research/02-gtm-motions-by-company.md`: founder tweets ARR milestones, Bolt users post screen-recordings, Cursor publishes its product feedback as content. Each fired signal becomes one piece of content within 24 hours.

This skill turns a signal trigger into ready-to-ship copy.

## How to invoke

```
signal-to-content: [signal name] fired for [target / context]
```

Examples:
- `signal-to-content: B4 (model release) — Claude 5 launched`
- `signal-to-content: A1 (GH velocity) — our SDK hit 1k stars`
- `signal-to-content: D7 (KOL mention) — Karpathy retweeted us`

## Steps Claude takes

1. **Read** `context/profile.md` (voice), `context/positioning.md` (rung proof points), `context/personas/*.md` (audience).

2. **Identify the signal type**:
   - **Outward-facing signal** (something happened to us): ARR milestone, GitHub star milestone, customer ship, KOL endorsement → output is *announcement content*.
   - **Inward-facing signal** (something happened in market): model release, competitor pricing cut, foundation-model benchmark jump → output is *reactive content*.

3. **Match to format**:

   | Signal type | Best format |
   |---|---|
   | ARR / user milestone | X thread, single tweet, optional LinkedIn |
   | Product ship | X thread + blog post + (optional) launch video |
   | Customer win | X thread (anonymized OK), blog post if customer permits naming |
   | Model release reaction | Blog post + X thread within 24h |
   | Competitor pricing move | Quote-tweet or comment thread (not separate post) |
   | KOL endorsement | Reply thread, NOT a "thank you for noticing" post |
   | New benchmark vs alternative | Blog post w/ live benchmark + X thread |

4. **Draft 3 versions of each format**:
   - **Version A**: numbers-first (the Anton @ Lovable style)
   - **Version B**: story-first (the Eric Simons @ Bolt founder-narrative style)
   - **Version C**: technical-first (the Cline / Aman @ Cursor proof-led style)

5. **Apply quality filters** (in order):
   - **"Remove the CTA test"** (borrowed from `gtm-starter-kit` and confirmed in our research): delete the "Try us / DM me / Sign up" CTA. Does the post still have value to the reader? Yes → it passes. No → it's a pitch, rewrite.
   - **"Specific numbers test"**: Does the post contain at least 1 specific number? If no, rewrite. ("Faster" fails; "37ms" passes.)
   - **"Adjective audit"**: Count marketing adjectives (powerful, leading, transformative, best-in-class, game-changing). If >0, rewrite. AI-native audiences allergic.
   - **"5-minute verifiability"**: Could a technical reader verify your claim in 5 minutes? If no, add a link / repo / playground / screenshot.

6. **Save drafts** to `outputs/YYYY-MM-DD-content-{signal-name}.md` with the 3 versions clearly labeled.

7. **Suggest distribution sequence**:
   - X first (founder account)
   - LinkedIn second (12-24h later, lightly reformatted)
   - Blog post if substance warrants
   - Email newsletter / Substack if applicable

## Anti-patterns

- Don't use the same content on all platforms. X is short + numbers; LinkedIn is slightly longer + accessible context; blog is the proof artifact.
- Don't write "I'm humbled" / "I'm grateful" openers. AI-native audiences read this as Linkedin-pollution.
- Don't auto-DM responders. The signal-to-content engine creates inbound — let the inbound come, then warm-DM only on direct engagement.
- Don't post during US business hours unless the signal is time-locked (e.g., reaction to a 9am PT model release). Post when devs are at keyboards: early morning PT, evening Asia hours.

## Trace to constitution

Constitution #3 (Community → Customer Funnel) — content IS the top-of-funnel for AI-native. This skill makes the funnel mechanical instead of artisanal.
