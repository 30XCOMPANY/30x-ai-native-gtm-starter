# 30x AI-Native GTM Starter

> The Claude Code repo for go-to-market when your product changes weekly, your buyer is an engineer, and your next competitor might be the next model release.

This file is the lobby. Claude reads it on every session. Skim in 2 minutes, then dive into `context/` for depth.

---

## What this repo is

A starter kit for **AI-native companies** — model labs, AI infrastructure, agent companies, AI-first developer tools — to run GTM through Claude Code instead of rebuilding context in every chat window.

Clone it. Fill in `context/` once. Run GTM tasks from a single prompt.

---

## Why AI-native GTM needed its own repo

Traditional B2B SaaS GTM playbooks assume: quarterly product cycles, business buyers, LinkedIn outbound, seat-based pricing, competitors who don't ship 10x improvements overnight. **None of that holds for AI-native companies.**

| Dimension | Traditional SaaS GTM | AI-Native Reality |
|---|---|---|
| Product cadence | Quarterly | Weekly (sometimes daily) |
| ICP stability | Refresh every 6 months | Drifts every month |
| Buyer profile | Business leader | Engineer / AI-curious PM |
| Primary GTM motion | Sales-led outbound | PLG + community + open source + integrations |
| Pricing model | $X / seat / month | Tokens, GPU hours, capacity |
| Competitor set | Same-category companies | Same-category + the next foundation model |

This repo is structurally inspired by [gtm-starter-kit](https://github.com/KarlRaf/gtm-starter-kit), but philosophically rebuilt around the five constitutions below.

---

## The Six Constitutions

Every file in `context/`, `skills/`, and `workflows/` derives from one of these six mental models. If a contribution doesn't trace back to one, it doesn't belong here.

Each one is backed by empirical evidence in `research/`. None of these is a hot take.

### 1. Living ICP
Your ICP drifts because your product drifts and because foundation models drift. A static ICP doc rots in 30 days. This repo treats ICP as a weekly-revised artifact with an evolution log. Six months of the log is more valuable than the current definition.

**AI-native ICP has three dimensions traditional SaaS doesn't:** LLM Maturity Stage, Data Residency × Deployment Mode, and Model Spend Trajectory. See `context/icp-definition.md`.

### 2. Technical Credibility Ladder
AI buyers don't read "value pillars." They read benchmarks, code samples, integration depth, latency numbers, and your GitHub commit graph. Replace "messaging matrix" with a credibility ladder: each rung is a piece of proof a technical buyer can verify in 5 minutes.

**Cursor scaled to $2B ARR with zero marketing spend** because the product itself was the proof. See `context/positioning.md`.

### 3. Community → Customer Funnel
Cold outbound to engineers underperforms. The funnel that works for AI-native: **GitHub star → Discord active → docs read → trial → paid → enterprise**. Every stage transition is measurable. Outbound exists, but only as the *last* step, not the first.

**Anthropic's enterprise logos are 54% self-serve.** Bolt.new went from $0 to $40M ARR in 5 months without an outbound team. Lovable hit $100M ARR in 8 months via founder Twitter content alone.

### 4. Capability Obsolescence Radar
Your traditional competitor radar tracks Notion, Linear, Apollo. Your *real* competitor radar tracks GPT-5.5 → 6, Claude 4.7 → 5, Gemini 3.0 → 3.5, and whether the next release commoditizes your moat.

**Jasper's ARR dropped from $90M projected to ~$55M after GPT-3.5.** Chegg lost 48% market cap in one day after disclosing ChatGPT impact. Character.AI sold to Google for $2.7B in a reverse acqui-hire. Capability obsolescence is a first-class concept here. See `context/competitor-radar.md`.

### 5. Integration-Led Growth
Marketing doesn't compound. Sales doesn't compound. **Integrations compound.** Every platform you ship into (Vercel, Cursor, Claude Code, Raycast, Slack, Linear) is a new growth curve.

**v0 reached 4M users by riding Vercel's 6M-developer base** — every v0 generation has a one-click "Deploy to Vercel" button. The integration *is* the GTM.

### 6. Agent-Native Distribution
This is the 2026 entry. **Your product must be callable by another AI agent**, not just a human. New users will increasingly discover you through Claude / ChatGPT / Cursor agents that invoke your product on their behalf, not through Google.

**Anthropic open-sourced MCP and donated it to the Linux Foundation.** Why? To own the protocol that all AI agents speak — 10,000+ public MCP servers shipped in H2 2025. If you don't have an MCP server, an Agent Skill, or an OpenAI Apps SDK integration in 2026, you're effectively invisible to the fastest-growing distribution channel in the industry. See `workflows/agent-native-distribution.md`.

---

## Directory map

```
30x-ai-native-gtm-starter/
├── CLAUDE.md                       ← you are here, 2-min lobby
├── README.md                       ← public-facing intro
├── context/                        ← institutional knowledge, grows weekly
│   ├── profile.md                  ← who we are, what we ship, who we sell to
│   ├── icp-definition.md           ← Living ICP + evolution log
│   ├── signal-library.md           ← AI-native signals + decay + combos
│   ├── positioning.md              ← Technical Credibility Ladder
│   ├── competitor-radar.md         ← competitors + Capability Obsolescence
│   └── personas/                   ← one file per buyer persona
├── skills/                         ← repeatable actions (SKILL.md format)
│   ├── setup/                      ← auto-fill from domain
│   ├── technical-poc-brief/        ← account research, technical-buyer-shaped
│   ├── signal-to-content/          ← signal → blog / tweet / launch post
│   ├── signal-to-integration-pitch/← signal → integration partner outreach
│   ├── icp-scoring/                ← score accounts on technical + commercial fit
│   ├── weekly-drift-audit/         ← what changed this week, what's stale
│   └── oss-pipeline-track/         ← GitHub star → customer funnel tracking
├── workflows/                      ← decision trees for humans
├── playbooks/                      ← emergency response scripts
├── sync/                           ← live data connectors (MCP-first)
├── outputs/                        ← every produced artifact, archived
├── research/                       ← empirical evidence base (case studies, signal taxonomy, pricing teardowns)
└── examples/sample-company/        ← a fully-filled fictional AI company
```

---

## How Claude should behave in this repo

1. **Always read `context/` before answering GTM questions.** Don't ask the user to re-explain ICP or positioning. It's already in the repo.
2. **Trace every recommendation to one of the six constitutions.** If you propose a tactic that doesn't fit, flag it. Cite `research/` evidence when relevant.
3. **Write outputs to `outputs/` with date prefixes.** Every research brief, every sequence, every campaign, archived for future learning.
4. **When unsure, default to the technical buyer.** AI-native buyers are engineers first. Lead with proof, not promise.
5. **Don't invent context.** If `context/` is missing something you need, ask the user to fill it. Don't fabricate.

---

## Current priorities

Fill this section weekly. Two to four bullets. This is what Claude prioritizes when the user asks "what should we focus on?"

- [ ] *Example:* Ship Vercel integration by end of June (Integration-Led Growth)
- [ ] *Example:* Re-score top 50 accounts after v0.4 launch (Living ICP)
- [ ] *Example:* Track GPT-5.5 release impact on our positioning (Capability Obsolescence Radar)

---

## Quickstart

```bash
git clone <this-repo> my-gtm
cd my-gtm
claude
# then say: "run the setup skill on https://yourcompany.com"
```

Claude reads `CLAUDE.md`, runs `skills/setup`, and populates `context/` from your public footprint. Refine over coffee. Ship outbound by lunch.

---

## Acknowledgment

Structurally inspired by [`gtm-starter-kit`](https://github.com/KarlRaf/gtm-starter-kit) by Maja Voje, Nico Druelle, and Karl Rafidimanana (April 2026). They built the scaffold for traditional B2B SaaS GTM in Claude Code. This repo rebuilds the philosophy for the AI-native case.

## License

MIT. Use, fork, ship. Attribution appreciated, not required.
