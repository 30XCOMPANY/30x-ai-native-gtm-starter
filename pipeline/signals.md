# pipeline/signals.md · AI-Native Signal Library

> Signals tell you *which* accounts are entering the buying window. AI-native signals are different from traditional SaaS signals — funding announcements and hiring posts are weak; code commits, model release reactions, and inference-spend trajectory are strong.
>
> 
---

## Why this file looks different from a traditional signal library

Traditional signal libraries track: funding announcements, hiring sprees, leadership changes, website tech-stack changes, pricing-page edits. These are designed for **detecting traditional B2B buying intent** in mid-market companies with multi-month procurement cycles.

AI-native signals are different:
- **Higher resolution** — a single tweet from Karpathy can move 1000 sign-ups in 48h. A weekly funding signal misses it entirely.
- **Faster decay** — DevDay-class announcements have 72-hour exploitation windows. Most traditional signals decay over months.
- **Code-layer, not company-layer** — a 5-person team can do $10M ARR. Their hiring posts won't exist. Their GitHub will.

This file is a *menu*. Pick the 8-12 signals most relevant to your ICP. Don't try to track all 22.

---

## Signal Schema

Every signal in your library must have:

```
### [Signal Name]
- **Layer**: [Code / Model / Compute / Community]
- **API/Source**: [URL or endpoint]
- **Intent**: [what this signal actually tells you — what's happening at the customer]
- **Detection method**: [how to extract / poll / scrape]
- **Decay**: [how long the signal stays useful]
- **Points** (in scoring): [1-5]
- **Combination bonus** (with other signals): [if applicable]
- **Hook**: [what your outbound says when this signal fires]
- **Example fired**: [historical instance for sanity check]
- **Status**: [Active / Paused / Decommissioned]
```

---

## Layer A · Code & Open-Source Signals

### A1 · GitHub Stars Velocity
- **Layer**: Code
- **API**: `GET /repos/{owner}/{repo}/stargazers` with header `Accept: application/vnd.github.star+json` (returns `starred_at`)
- **Intent**: Repo gaining 200+ stars in a week = viral spread, often "demo went on HN or X." Team is overwhelmed with inbound — perfect time for outbound (you're noise reduction, not noise addition).
- **Detection**: Daily poll, store snapshots, compute 7-day delta.
- **Decay**: 48-72h hard window. 80% heat-decay by day 7.
- **Points**: 3 (5 if delta >1000)
- **Combination**: +2 if also Stage 3 LLM Maturity per ICP
- **Hook**: "Saw `{repo}` jump 400 stars this week. We help teams in your shape handle the [eval / observability / billing] surge that follows. 15 min?"
- **Example fired**: CrewAI Q1 2024, 5k → 25k stars in one month → seed round 3 weeks later.
- **Status**: Active.

### A2 · New-Org First-Repo Burst
- **Layer**: Code
- **API**: `GET /search/repositories?q=created:>2026-MM-DD+stars:>500`
- **Intent**: A brand-new GitHub org's first public repo crossing 500 stars = team emerging from stealth. First contact opportunity.
- **Detection**: Daily search query with rolling 14-day window.
- **Decay**: First week or you lose first-mover advantage.
- **Points**: 4
- **Hook**: "Saw `{org}/{repo}` — looks like first public release. Curious what's behind the curtain. 15 min low-key chat?"
- **Status**: Active.

### A3 · Issues & PR Velocity
- **Layer**: Code
- **API**: `GET /repos/{owner}/{repo}/issues?state=open&sort=created`
- **Intent**: 10+ new issues per day on your competitor's repo = users hitting real bugs. They're shopping.
- **Decay**: 7-day rolling.
- **Points**: 2
- **Combination**: +2 if competitor's CEO is publicly addressing the issues.
- **Status**: Active.

### A4 · Dependents Graph
- **Layer**: Code
- **API**: Scrape `https://github.com/{owner}/{repo}/network/dependents` (no official API)
- **Intent**: Who's integrating your SDK / library — direct channel discovery. Star-weighted dependents are higher quality leads than star-weighted stargazers.
- **Decay**: Weekly.
- **Points**: 3
- **Status**: Active.

### A5 · npm / pip Download Spikes
- **Layer**: Code
- **API**: `https://api.npmjs.org/downloads/range/last-week/{pkg}`; PyPI via `pypistats`; aggregator at pepy.tech
- **Intent**: Weekly downloads jumping 5x = big creator endorsed, or viral spread on dev social.
- **Decay**: Daily check; the spike itself decays in 5-7 days.
- **Points**: 3
- **Status**: Active.

### A6 · Stack Overflow / GitHub Discussions Question Spikes
- **Layer**: Code
- **API**: Stack Exchange `/questions?tagged={tag}`; GitHub Discussions GraphQL
- **Intent**: +50% WoW question volume on a tag = mainstream adoption phase (devs only ask when stuck).
- **Decay**: Monthly.
- **Points**: 2
- **Status**: Active.

---

## Layer B · Model & Inference Signals

### B1 · HuggingFace Trending Models
- **Layer**: Model
- **API**: `GET https://huggingface.co/api/models?sort=trending`
- **Intent**: A model on the trending list = downstream apps will integrate within 7 days. Companies running those apps need new infra.
- **Decay**: 3-7 days.
- **Points**: 3
- **Example fired**: DeepSeek-V3 0324 trended; Together AI listed it at $2.10/M within a week.
- **Status**: Active.

### B2 · HuggingFace Space Creation Velocity
- **Layer**: Model
- **API**: `/api/spaces?sort=createdAt`
- **Intent**: Surge of Spaces built on a particular base model = ecosystem forming around that model.
- **Decay**: Weekly.
- **Points**: 2
- **Status**: Active.

### B3 · OpenRouter Usage Leaderboard
- **Layer**: Model
- **Source**: `https://openrouter.ai/rankings` (scrape)
- **Intent**: A model's OpenRouter token traffic +200% WoW = real paid apps switching base models. Most sensitive signal in this entire library.
- **Detection**: Daily scrape, store, compute deltas.
- **Decay**: Daily.
- **Points**: 5
- **Example fired**: Sonnet 4.5 → OpenRouter #1 within 48h → Cursor + Cline overnight switch.
- **Status**: Active.

### B4 · Foundation-Model Release Window
- **Layer**: Model
- **Source**: Anthropic / OpenAI / Google AI / Meta / Mistral blogs + RSS + Twitter
- **Intent**: First 72h after a major model release, every wrapper enters "integration race." Golden window for selling eval / observability / routing tools.
- **Decay**: 72h hard.
- **Points**: 4
- **Combination**: +3 if release shifts benchmark in customer's vertical
- **Hook**: "Claude 4.7 ships in 48h, your eval suite needs to re-baseline. We can ship you that in one afternoon."
- **Example fired**: Claude 4 launch day → Braintrust / LangSmith / Helicone all posted within 24h.
- **Status**: Active.

### B5 · ChatGPT / Claude Plugin & App Appearance
- **Layer**: Model
- **Source**: OpenAI GPT Store, Claude.ai connectors list (scrape — no API)
- **Intent**: Companies that appear here are exposed to AI-user funnel, often under-monetized, GTM-ready.
- **Decay**: 30-day post-listing growth curve is most important.
- **Points**: 3
- **Status**: Active.

### B6 · Cursor / Windsurf / Cline / MCP Server Publication
- **Layer**: Model
- **Source**: docs.cursor.com, Cline marketplace, [modelcontextprotocol.io/servers](https://modelcontextprotocol.io/servers)
- **Intent**: Companies that ship MCP servers in 2026 = AI-native thinkers, understand distribution. Premium ICP candidates.
- **Decay**: All new entries worth tracking — MCP still early.
- **Points**: 4
- **Status**: Active. **High priority.**

---

## Layer C · Compute Consumption Signals

### C1 · Replicate / Modal / Beam Public Model Deployments
- **Layer**: Compute
- **API**: Replicate `/v1/models`; Modal Examples on GitHub; Beam public templates.
- **Intent**: A team with 5+ fine-tuned models on Replicate = serious model-layer company, candidate for GPU optimization / fine-tuning infra / observability.
- **Decay**: Weekly.
- **Points**: 4
- **Status**: Active.

### C2 · Vercel AI SDK Adoption
- **Layer**: Compute
- **Source**: npm `ai` downloads, Vercel templates, GitHub repos with `@ai-sdk/*` deps
- **Intent**: Next.js + AI SDK = ~100% Vercel-hosted = inferred Vercel Pro/Enterprise customer.
- **Decay**: Weekly.
- **Points**: 2
- **Status**: Active.

### C3 · Inference-Provider Price-Change Events
- **Layer**: Compute
- **Source**: Diff-monitor pricing pages for Together / Fireworks / Replicate / Modal
- **Intent**: A provider cutting prices suddenly = customer leakage pressure on competitors. Customers of cut-prices-from provider are wobbling.
- **Decay**: 24-48h per change.
- **Points**: 3
- **Example fired**: Together AI's repeated Llama 70B cuts in 2025 each triggered wrapper-company migration waves.
- **Status**: Active.

---

## Layer D · Community & Intent Signals

### D1 · HN Front-Page AI Story
- **Layer**: Community
- **API**: `https://hn.algolia.com/api/v1/search?tags=story&query=ai` sorted by points
- **Intent**: Single post >300 points and >150 comments = SOTA visibility, inbound flood within 48h. Team is overwhelmed.
- **Decay**: 48h hard.
- **Points**: 4
- **Example fired**: Modal's cold-start post → #2 front page → +1000 signups in 72h.
- **Status**: Active.

### D2 · ProductHunt AI Category Ranking
- **Layer**: Community
- **API**: `https://api.producthunt.com/v2/api/graphql` topic slug `artificial-intelligence`
- **Intent**: #1-3 of the day = early-user wave; PMF unproven. Check retention at 3 months.
- **Decay**: Launch day + 48h.
- **Points**: 2
- **Status**: Active.

### D3 · Reddit r/LocalLLaMA / r/MachineLearning Mentions
- **Layer**: Community
- **API**: Reddit OAuth (free, 60 req/min)
- **Intent**: Tools mentioned in top comments of evaluation threads = real developer selection.
- **Decay**: 3-7 days.
- **Points**: 2
- **Status**: Active.

### D4 · arXiv Paper → Commercialization Window
- **Layer**: Community
- **API**: `http://export.arxiv.org/api` `cs.LG`, `cs.CL`
- **Intent**: 30 days after a paper's GitHub repo goes live = commercialization window (authors often fundraising or starting up). High-quality first-contact opportunity.
- **Decay**: 30-90 days.
- **Points**: 3
- **Status**: Active.

### D5 · AI Newsletter Mentions
- **Layer**: Community
- **Source**: TLDR AI / Ben's Bites / The Rundown (subscribe + parse / archive scrape)
- **Intent**: Editorially-validated "worth watching," but lags HN by 12-24h.
- **Decay**: 24h.
- **Points**: 2
- **Status**: Active.

### D6 · Discord Server Member Growth
- **Layer**: Community
- **API**: disboard.org public listing + Discord Widget JSON
- **Intent**: AI tool's Discord adding 500+/week = user-education phase, needs dev-rel tooling.
- **Decay**: Weekly.
- **Points**: 2
- **Status**: Active.

### D7 · AI KOL Twitter / X Mentions
- **Layer**: Community
- **API**: X Basic $100/mo OR Nitter scraping (unstable)
- **Intent**: Karpathy / Swyx / Simon Willison / Logan Kilpatrick mention = 24h traffic burst warning.
- **Decay**: 12-48h.
- **Points**: 3
- **Status**: Active — paid API required at scale.

---

## Signal Combination Rules

Signals are not additive — they multiply through context.

**High-value combinations**:

- **A1 (GH velocity)** + **B4 (model release window)** = team scaling on the back of a new model. *Outbound NOW, this week only.*
- **A2 (new org first-repo)** + **D7 (KOL mention)** = stealth team breakout. Highest first-contact opportunity, 24h window.
- **B6 (MCP server published)** + **C2 (Vercel AI SDK)** = AI-native technical posture confirmed. ICP score +5 minimum.
- **C1 (Replicate deploys)** + **C3 (provider price-cut)** = customer is sensitive to inference cost, considering alternatives. Sell observability + routing.
- **B4 (model release)** + **D7 (KOL critical of new release)** = doubters about new model = retention opportunity for old-model users.

**Anti-combinations** (signals that look strong but are weak together):
- A1 (GH stars) + paid traffic on landing page = artificial spike, probably not viral signal.
- Funding announcement alone = traditional signal, weak intent for AI-native sales. Look for A2 / B6 / C1 to confirm.

---

## Decay Reference Table

| Signal type | Hot window | Useful window | Discard after |
|---|---|---|---|
| HN front page | 48h | 7 days | 14 days |
| Model release reaction | 72h | 14 days | 30 days |
| GitHub star velocity | 7 days | 30 days | 90 days |
| KOL mention | 24h | 7 days | 14 days |
| ProductHunt top-3 | 48h | 14 days | 30 days |
| MCP server publish | 7 days | 90 days | 180 days |
| Funding announcement | 30 days | 180 days | n/a (traditional signal, slow decay) |

> **Decay rule of thumb**: code/community signals decay in days. Compute/spend signals decay in weeks. Traditional signals (funding, hiring) decay in months.

---

## How Claude uses this file

When asked to find / score / route an account, Claude:

1. Reads ICP from `icp-definition.md`.
2. Pulls signals from this library that apply to that ICP.
3. Polls live sources via `sync/` (or asks user to fetch if no sync available).
4. Applies decay table — signals older than "useful window" are de-weighted, older than "discard after" are dropped.
5. Outputs scored list to `outputs/YYYY-MM-DD-account-scoring.md`.

---

## Active Signal Set

> Mark 8-12 signals as `[x]` based on your ICP. Don't try to monitor all 22 — you'll drown.

Code layer:
- [ ] A1 GitHub stars velocity
- [ ] A2 New-org first-repo burst
- [ ] A3 Issues & PR velocity (competitors')
- [ ] A4 Dependents graph
- [ ] A5 npm / pip download spikes
- [ ] A6 Stack Overflow / Discussions

Model layer:
- [ ] B1 HF trending models
- [ ] B2 HF Space velocity
- [ ] B3 OpenRouter leaderboard
- [ ] B4 Foundation-model release window
- [ ] B5 ChatGPT / Claude plugin appearance
- [ ] B6 MCP server publication

Compute layer:
- [ ] C1 Replicate / Modal deployments
- [ ] C2 Vercel AI SDK adoption
- [ ] C3 Inference price-change events

Community layer:
- [ ] D1 HN front page
- [ ] D2 ProductHunt top
- [ ] D3 Reddit mentions
- [ ] D4 arXiv → commercialization window
- [ ] D5 AI newsletter mentions
- [ ] D6 Discord growth
- [ ] D7 KOL Twitter mentions

---

> **[PROTOCOL]**: When a new signal is added, also update `sync/` with the data-pull mechanism (MCP server or script) and update `skills/signal-to-content/` and `skills/signal-to-integration-pitch/` with the outbound hook templates. A signal without a sync mechanism is a signal that won't fire.
