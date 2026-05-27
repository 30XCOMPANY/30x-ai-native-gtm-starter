---
date: 2026-05-27
channel: blog
pillar: capability-obsolescence
status: example
anchor-signal: research/01-capability-obsolescence-and-icp.md · Jasper case
audience: AI founders building wrapper products
---

# Why Jasper went from $90M projected ARR to ~$55M in 9 months — and what every wrapper company missed

> A teardown of the first publicly documented capability-obsolescence death in AI.

October 2022: Jasper raises $125M Series A at $1.5B valuation. Projected 2024 ARR: $250M.

September 2023: Both founders (CEO + CTO) resign within the same week. Internal valuation marked down 20%. ARR projection cut from $90M to ~$55M.

What happened in between is one thing: **ChatGPT shipped, then GPT-4 shipped**, and Jasper's product — a GPT-3 wrapper with prompt templates for marketing copy — got commoditized in user behavior overnight.

This piece is the post-mortem nobody wrote, with three lessons every wrapper founder should internalize.

---

## What Jasper actually was, in technical terms

Strip the marketing away. Jasper's product in 2022 was:

1. A wrapper around the OpenAI Completion API (GPT-3, later GPT-3.5)
2. A library of prompt templates ("write a blog intro", "write a Facebook ad")
3. A workspace UI with brand voice settings
4. Team / billing infrastructure on top

The technical moat was layer 2 (the prompt templates) and layer 3 (the UX). Layer 1 was rented from OpenAI. Layer 4 was Stripe.

In late 2022 this was a real product. The prompt templates required real expertise — GPT-3 needed a lot of coaxing to produce usable marketing copy.

---

## The trigger event

November 30, 2022: ChatGPT launches. Free.

In one weekend, every Jasper user discovered they could open ChatGPT and ask "write a Facebook ad about [their product]" and get output that was 80% as good as Jasper's, without the $49/month subscription.

The 20% gap — Jasper's brand voice tooling, the team workspace, the integrations — was real but no longer the headline. The headline was: *the underlying capability is free now*.

Six months later, GPT-3.5 shipped via the API. The 20% gap shrank further.

---

## Three things Jasper did right, slowly

By the time Jasper resigned to repositioning (mid-2023), they made three correct moves:

1. **Repositioned from "individual creators" to "marketing teams at mid-market companies"**. Teams need workspace + governance + brand voice consistency — features ChatGPT didn't have for B2B buyers.
2. **Invested in a brand voice model** — fine-tuning customer-specific text generation. Genuinely additive on top of base GPT.
3. **Built integrations** (Surfer SEO, Google Docs, etc.) — workflow embedding that GPT alone couldn't replicate.

These moves saved the company. As of late 2023 they were still operating, just at a much smaller valuation than the 2022 high.

---

## Three things they should have done in late 2022

When ChatGPT launched, Jasper had 6 months of cash runway and a strong brand. The correct moves, in retrospect:

### 1. Re-baseline ICP immediately

The ICP that worked in October 2022 (individual creator + SMB marketer) was incompatible with the post-ChatGPT world. The team-of-10+ marketing org was still viable.

This is one of the three AI-native ICP dimensions: **LLM Maturity Stage**. An individual creator at Stage 1 (using ChatGPT directly) will not pay for Jasper. A marketing team at Stage 3 (running production content workflows with governance) will.

Most wrapper companies don't have an ICP framework that includes this axis at all.

### 2. Pre-announce the rebrand BEFORE revenue collapsed

Jasper repositioned in mid-2023 — six months after ChatGPT. Six months of declining revenue, falling team morale, and external press writing "Jasper is dead" content.

The right move: when ChatGPT launched, publicly announce within 30 days that Jasper was repositioning. Get ahead of the narrative. The story would have been *"Jasper pivots fast to enterprise"* instead of *"Jasper struggles to keep up."*

### 3. Make pricing a strategic weapon, not a defense

Jasper kept its existing pricing through most of 2023. The right move would have been to either (a) drop the entry tier to $9/month to compete on price with the friction of opening ChatGPT, or (b) consolidate to a $99+ Teams plan and stop trying to defend the SMB segment.

Doing neither — defending pricing while losing the market — is the worst of both.

---

## What this teaches every AI wrapper company in 2026

Three things you do today if you're a wrapper:

1. **Write down your `strategy/capability-radar.md`** — list the next 6 months of expected model releases and self-assess whether your moat survives each.
2. **Build the workflow / data / integration layer that doesn't live in the foundation model.** Brand voice models, team workspaces, deep integrations, vertical compliance — these are where Jasper invested too late and where you should invest early.
3. **Decide your "pivot trigger" in advance.** When does the foundation model becoming "good enough" force your pivot? Write the date. When the date approaches, pivot before metrics deteriorate, not after.

---

## Sources

- The Information — "Jasper cuts internal valuation as growth slows" — 2023-08
- Maginative — "Jasper cuts internal valuation as AI growth slows" — 2023-09
- LinkedIn post-mortem by ex-employees describing the "120M → 55M" collapse

Full case studies of nine other AI startups that died similar deaths: see [`examples/our-flavor/research/01-capability-obsolescence-and-icp.md`](../../examples/our-flavor/research/01-capability-obsolescence-and-icp.md).

---

## How this fits the scaffold

This post is an example of `content/blog/` output. If you're using this repo:

- Anchor signal lives in `pipeline/signals.md` (the death case is a referenceable example of capability obsolescence)
- Brand voice it follows is in `strategy/brand.md`
- The "pivot trigger" advice connects to `playbooks/foundation-model-commoditizes-your-feature.md`

To produce a post like this, run `skills/signal-to-content: blog mode · capability obsolescence pillar · audience AI founders`.
