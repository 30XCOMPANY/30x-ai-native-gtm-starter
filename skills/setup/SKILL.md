---
name: setup
description: Bootstrap a fresh repo with company context. Given a domain, populates `strategy/about.md` from public sources (website, GitHub, Crunchbase, Wellfound, LinkedIn) and prompts the user to refine the three AI-native ICP dimensions.
---

# Skill · setup

## What this does

First thing a new fork of this repo runs. Goes from empty templates to "Claude can talk meaningfully about us" in one prompt.

## How to invoke

```
run setup on https://your-company.com
```

Or just paste a URL and Claude will infer.

## Steps Claude takes

1. **Fetch public footprint**:
   - Company website (homepage, /about, /pricing, /docs)
   - GitHub org (if exists) — recent repos, contributor count, language mix
   - Crunchbase / Wellfound entry (funding, team size)
   - LinkedIn page (employee count band, founding date)
   - HN / X mentions in the last 90 days

2. **Populate `strategy/about.md`** with the discovered fields. Leave clearly-marked `[needs user input]` placeholders where public data is missing.

3. **Draft `strategy/icp.md` Section 1** with best-guess defaults:
   - LLM Maturity Stage inferred from product type (e.g., dev tool → likely targets Stage 3+)
   - Data Residency posture inferred from pricing/security pages
   - Model Spend Trajectory left blank — user must input

4. **Ask the user 5 questions** to refine:
   1. What's the one sentence you'd say to a technical buyer to make them try the product in 5 minutes? (→ informs Rung 2 of `positioning.md`)
   2. Who is your most ICP-aligned customer? (→ seeds reference cases)
   3. What's your most embarrassing loss in the last quarter? (→ seeds anti-ICP)
   4. Which foundation-model release most threatens or accelerates you? (→ seeds `competitor-radar.md` Section 2)
   5. Which platform integration would 10x your distribution if it shipped? (→ seeds CLAUDE.md Current Priorities)

5. **Save outputs** to `outputs/YYYY-MM-DD-setup-summary.md` and update `CLAUDE.md` Current priorities section based on the answers.

## Anti-patterns

- Do not invent funding amounts, employee counts, or customer logos. Leave `[needs user input]` and ask.
- Do not pull customer lists from social media that aren't on the company's own site.
- Do not skip the 5 questions. The auto-fill is 70% accurate at best; the 5 questions are where this skill becomes valuable.

## Where this fits
This skill bootstraps ICP maintenance and #2 (Technical Credibility Ladder) so subsequent skills have material to work with.
