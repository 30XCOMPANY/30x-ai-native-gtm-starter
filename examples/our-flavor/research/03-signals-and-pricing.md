# Signal Sources + Pricing Patterns — Empirical Reference

> Research compiled May 2026. All pricing numbers fetched live from official pages. 22 AI-native signal sources with API + decay + example. 12 pricing teardowns. Five anti-SaaS pricing rules at the bottom.

This file backs `context/signal-library.md` and informs `context/positioning.md` pricing sections.

---

## Part 1 · 22 AI-Native Signal Sources

Traditional SaaS signals (hiring, funding, website tech stack) fail on AI-native companies — a 5-person team can be doing $10M ARR. Real signal lives in code, models, inference, token flow.

### A · Code & Open-Source Layer

#### 1. GitHub Stars Velocity (speed > absolute count)
- **API**: GitHub REST `/repos/{owner}/{repo}/stargazers` with media type `application/vnd.github.star+json` (returns starred_at timestamps).
- **Intent**: 200+ stars in a single week = viral spread, usually corresponds to "just shipped a demo video" or "just launched on HN."
- **Access**: free, 5000 req/hr (with token). You store historical snapshots locally to compute delta.
- **Decay**: 48-72 hour window. Heat decays 80% by day 7.
- **Example**: CrewAI Q1 2024 went from 5k → 25k stars in a month, seed round announced 3 weeks later.

#### 2. GitHub Repo Creation Burst (new org's first viral repo)
- **API**: GitHub Search `created:>2026-05-01 stars:>500`.
- **Intent**: A new org's first public repo crossing 500 stars in a short window = team emerging from stealth.
- **Access**: free, 30 search/min rate limit.
- **Decay**: miss the first week and you lose the "first contact" advantage.
- **Example**: Modal Labs' first public repo `modal-examples` crossed 1k stars within two weeks.

#### 3. Issues & PR velocity
- **API**: `/repos/{owner}/{repo}/issues` + `/pulls` sorted by created_at.
- **Intent**: 10+ daily issues = users are actually using it, hitting bugs, approaching PMF.
- **Access**: free REST.
- **Decay**: 7-day rolling window.

#### 4. Dependents Graph (who's integrating you)
- **API**: GitHub Dependents (semi-official, requires scraping `/network/dependents`).
- **Intent**: Which repos depend on your SDK, and how starred those dependents are = channel discovery.
- **Access**: HTML scraping.
- **Decay**: weekly.

#### 5. npm / pip download spikes
- **API**: npm `https://api.npmjs.org/downloads/range/last-week/{pkg}` / PyPI `pypistats` / pepy.tech API.
- **Intent**: Weekly downloads jumping from 1k → 50k = a big creator endorsed it, or viral spread.
- **Access**: free, no rate limit (npm).
- **Decay**: daily.
- **Example**: `anthropic` Python SDK weekly downloads 3x'd after Claude 4 release.

#### 6. Stack Overflow / GitHub Discussions question volume
- **API**: Stack Exchange `/questions?tagged={tag}` + GitHub Discussions GraphQL.
- **Intent**: Tag question volume +50% WoW = tool entering mainstream adoption (developers ask only when stuck).
- **Access**: Stack Exchange API free 10k req/day.
- **Decay**: monthly.

### B · Model & Inference Layer

#### 7. HuggingFace trending models
- **API**: HF Hub `https://huggingface.co/api/models?sort=downloads&direction=-1` and `?sort=trending`.
- **Intent**: A model going from 1k → 100k weekly downloads = becoming SOTA in its vertical, downstream apps will pour in.
- **Access**: free, via [openapi.json](https://huggingface.co/.well-known/openapi.json).
- **Decay**: 3-7 days.
- **Example**: DeepSeek-V3 0324 hit trending, Together AI listed it at $2.10/M within a week.

#### 8. HuggingFace Space creation velocity
- **API**: HF Hub `/api/spaces?sort=createdAt`.
- **Intent**: Surge of Spaces built on a particular base model = ecosystem forming.
- **Access**: free REST.
- **Decay**: weekly.

#### 9. OpenRouter Model Usage Leaderboard
- **Source**: [openrouter.ai/rankings](https://openrouter.ai/rankings) (public page).
- **Intent**: A model's OpenRouter token traffic +200% WoW = real paid apps are switching base models.
- **Access**: HTML scraping, no official API.
- **Decay**: daily. One of the most sensitive signals.
- **Example**: Sonnet 4.5 hit OpenRouter #1 within 48h of launch, corresponding to Cursor and Cline overnight switching default models.

#### 10. Foundation-model release window
- **Source**: Anthropic / OpenAI / Google AI / Meta / Mistral blog + RSS + Twitter accounts.
- **Intent**: First 72 hours after a new model release, every wrapper-class AI app enters "integration race" — golden window for selling prompt-eval / observability / routing tools.
- **Access**: RSS / Twitter API ($100/mo X Basic) / web scraping.
- **Decay**: 72-hour hard window.
- **Example**: Claude 4 launch day, Braintrust / LangSmith / Helicone posted same-day social.

#### 11. ChatGPT / Claude plugin & app appearance
- **Source**: OpenAI GPT Store, Claude.ai connectors list.
- **Intent**: Companies on these surfaces = already exposed to AI-user funnel, often under-monetized, GTM-ready.
- **Access**: scraping (no official API).
- **Decay**: 30-day post-listing curve is most critical.

#### 12. Cursor / Windsurf / Cline plugin & MCP integration
- **Source**: docs.cursor.com integrations, Cline marketplace, [modelcontextprotocol.io/servers](https://modelcontextprotocol.io/servers).
- **Intent**: Companies that publish MCP servers = already AI-native thinkers, understand distribution, high-quality leads.
- **Access**: scraping.
- **Decay**: MCP ecosystem in early phase 2026, every new entry worth tracking.

### C · Compute-Consumption Layer

#### 13. Modal / Beam / Replicate public model deployment count
- **Source**: Replicate's `/v1/models` public API, Modal Examples GitHub, Beam Cloud public templates.
- **Intent**: A team with 7 fine-tuned models on Replicate = model-layer startup, prime customer for GPU optimization.
- **Access**: free API (Replicate).
- **Decay**: weekly.

#### 14. Vercel AI SDK adoption + AI Gateway usage
- **Source**: npm `ai` downloads, Vercel public templates, GitHub repos with `@ai-sdk/*` deps.
- **Intent**: Next.js + AI SDK = ~100% Vercel-deployed, infer Vercel Pro/Enterprise customer.
- **Access**: free npm API.
- **Decay**: weekly.

#### 15. Inference-provider price-change events
- **Source**: Together / Fireworks / Replicate / Modal pricing pages (diff monitoring).
- **Intent**: A provider cutting prices suddenly = customer-leakage pressure, ideal time to capture new signups.
- **Access**: periodic WebFetch + diff, free.
- **Decay**: 24-48 hours per change event.
- **Example**: Together AI repeatedly cut Llama 70B prices in 2025, each event triggered wrapper-company migration waves.

### D · Community & Intent Layer

#### 16. Discord server member growth
- **Source**: [disboard.org](https://disboard.org) public listing, Discord Widget API (public servers).
- **Intent**: An AI tool's Discord adding 500+ weekly = user-education stage, needs dev-rel tooling.
- **Access**: Disboard scraping + Discord widget JSON (free, only for servers with widget enabled).
- **Decay**: weekly.

#### 17. HN front-page AI stories + comment heat
- **API**: [HN Algolia](https://hn.algolia.com/api): `/api/v1/search?tags=story&query=ai` sorted by points.
- **Intent**: Single post >300 points and >150 comments = team entered SOTA visibility, will see inbound flood within 48h.
- **Access**: Algolia API completely free, 10k req/hr.
- **Decay**: 48-hour hard window.
- **Example**: Modal's cold-start optimization HN post hit #2 on front page, 72h later +1000 signups.

#### 18. ProductHunt AI category ranking
- **API**: [Product Hunt GraphQL](https://api.producthunt.com/v2/api/graphql), topic slug `artificial-intelligence`.
- **Intent**: #1-3 of the day = early-user wave incoming, but PMF unproven — check retention 3 months later.
- **Access**: free token on registration.
- **Decay**: launch day + 48h.

#### 19. Reddit r/LocalLLaMA / r/MachineLearning / r/singularity mentions
- **API**: Reddit OAuth (free, 60 req/min). Pushshift unstable.
- **Intent**: Tools mentioned in top comments of open-model evaluation threads = real developer selection.
- **Access**: Reddit API, register and go.
- **Decay**: 3-7 days.

#### 20. arXiv paper → commercialization window
- **API**: [arXiv](http://export.arxiv.org/api) `cs.LG`, `cs.CL`.
- **Intent**: 30 days after a paper's GitHub repo goes live = commercialization window (authors are usually fundraising or starting up).
- **Access**: free, no rate limit (suggest 3-second interval).
- **Decay**: 30-90 days.

#### 21. AI newsletter mentions (TLDR AI / Ben's Bites / The Rundown)
- **Source**: subscribe + parse / scrape archive.
- **Intent**: Mention = editorially-verified "worth watching," but content lags HN by 12-24h.
- **Access**: scraping.
- **Decay**: 24h.

#### 22. Twitter/X AI KOL mentions & retweet graph
- **API**: X API ($100/mo Basic, 10k tweets/month) or Nitter scraping (unstable).
- **Intent**: Karpathy / Swyx / Simon Willison / Logan Kilpatrick mentions = 24h traffic burst warning.
- **Access**: X API paid or third-party scraper.
- **Decay**: 12-48h.

---

## Part 2 · 12 Pricing Teardowns (live data May 2026)

### 1. Anthropic Claude API
Source: [claude.com/pricing](https://claude.com/pricing) + [docs.claude.com](https://docs.claude.com/en/docs/about-claude/pricing)

| Model | Input / 1M | Output / 1M |
|---|---|---|
| Claude Opus 4 | $15 | $75 |
| Claude Sonnet 4.6 | $3 | $15 |
| Claude Haiku 4.5 | $1 | $5 |

Mechanics: Prompt caching +25% write / -90% read. Batch API -50%. Tier system T1 ($5 deposit) → T4 ($400+) with 100x rate-limit step.

Consumer: Pro $17 annual / $20 monthly, Max from $100/mo, Team Standard $20/seat annual / $25 monthly, Team Premium $100/seat annual, Enterprise = seat fee + API usage.

**Reverse pricing signal**: Sonnet 4.5 → 4.6 same price ($3/$15), but **Haiku 4.5 priced UP** ($0.25 → $1 input) vs Haiku 3. Anthropic no longer competing on low-end; pushing mid-tier for margin.

### 2. OpenAI API
Source: [developers.openai.com](https://developers.openai.com/api/docs/pricing) (403) + aggregators

| Model | Input / 1M | Cached / 1M | Output / 1M |
|---|---|---|---|
| GPT-5.5 | $5.00 | $0.50 | $30.00 |
| GPT-5.4 | $2.50 | $0.25 | $15.00 |
| GPT-5.4 mini | $0.75 | — | $4.50 |
| GPT-5.4 nano | $0.20 | — | $1.25 |
| GPT-4o | $2.50 | — | $10.00 |

Mechanics: cached input 90% off. Batch API -50%. 5 tiers by deposit.

**Reverse pricing signal**: GPT-5.5 output $30 = 2x Sonnet 4.6, but cached input slammed to $0.50 (close to Sonnet's $0.30 cache read). "High sticker + aggressive cache discount" locks long-context enterprise customers.

### 3. Cursor
Source: [cursor.com/pricing](https://cursor.com/pricing)

| Plan | Price |
|---|---|
| Hobby | free |
| Pro | $20/mo |
| Teams | $40/user/mo |
| Enterprise | custom |

Mechanics: each plan includes "model usage credit," overflow billed at API rate (in arrears). Mid-2025 switched from "500 fast requests" to dollar credit pool.

**Reverse pricing signal**: Cursor's 2025 Fast Request cut caused user backlash, settled into "$20 includes $X usage + post-paid overflow" — landmark moment for AI products moving from "monthly bundle" to "monthly bundle + usage."

### 4. Windsurf
Source: [windsurf.com/pricing](https://windsurf.com/pricing)

| Plan | Price | Note |
|---|---|---|
| Free | $0 | basic access |
| Pro | $20/mo | "Unlimited" with overflow at API price |
| Teams | $40/user/mo | central billing |
| Enterprise | custom | Devin Cloud agents |

**Reverse pricing signal**: "Unlimited at API pricing" softens the seat+usage hybrid framing. Essentially same as Cursor.

### 5. Replicate
Source: [replicate.com/pricing](https://replicate.com/pricing)

| GPU | $/s | $/h |
|---|---|---|
| T4 | 0.000225 | 0.81 |
| L40S | 0.000975 | 3.51 |
| A100 80GB | 0.001400 | 5.04 |
| H100 | 0.001525 | 5.49 |
| 2x L40S | 0.001950 | 7.02 |
| 2x A100 | 0.002800 | 10.08 |

Mechanics: Public models billed only by run time. Private models charge setup + idle + active (brutal). Fast-Booting fine-tunes charge active only.

**Reverse pricing signal**: Public-vs-private billing gap is Replicate's hidden push to make users open-source models — open = others use = your cost amortized.

### 6. Together AI
Source: [together.ai/pricing](https://together.ai/pricing)

Serverless per 1M tokens: Llama 3.3 70B $0.88/$0.88, DeepSeek V4 Pro $2.10 cached $0.20 / $4.40, Kimi K2.6 $1.20/$4.50, GLM-5.1 $1.40/$4.40.

Dedicated GPU: 1xH100 $6.49/h on-demand $5.49/h, 1xH200 $6.79/h, 1xB200 $11.95/h cluster $9.95/h, Reserved 7+ days $3.99-9.65/h.

**Reverse pricing signal**: Same input/output price ($0.88/$0.88 Llama 70B) — vs Anthropic's 5x gap = "we don't arbitrage on output, we win on scale."

### 7. Modal
Source: [modal.com/pricing](https://modal.com/pricing)

| GPU | $/s | $/h |
|---|---|---|
| H100 | 0.001097 | 3.95 |
| A100 80GB | 0.000694 | 2.50 |
| A100 40GB | 0.000583 | 2.10 |
| A10 | 0.000306 | 1.10 |
| L4 | 0.000222 | 0.80 |
| T4 | 0.000164 | 0.59 |

CPU $0.0000131/core/s, Memory $0.00000222/GiB/s (min 0.125 core), Volumes $0.09/GiB/mo (1 TiB free included).

Plans: Starter $30/mo free credit / 3 seats / 10 GPU concurrent, Team $250+/mo (with $100 credit), 1000 containers, Enterprise volume discount.

**Reverse pricing signal**: Modal H100 at $3.95/h beats Together $6.49 by ~40%, but enforces GPU concurrency caps (Starter 10). "Low unit price + hard concurrency wall" cleanly separates self-serve from sales-led.

### 8. Beam Cloud
Source: [docs.beam.cloud](https://docs.beam.cloud/v2/resources/pricing-and-billing)

| Resource | $/s | $/h |
|---|---|---|
| H100 | 0.000972 | 3.50 |
| A10G | 0.000292 | 1.05 |
| RTX 4090 | 0.000192 | 0.69 |
| CPU/core | 0.0000528 | 0.190 |
| RAM/GB | 0.0000056 | 0.020 |

Storage free. Only runtime billed (incl. warm-up); image-pull not counted.

**Reverse pricing signal**: H100 $3.50/h is 11% cheaper than Modal, sacrificing ecosystem — typical "low-price inversion" to attack Modal/Replicate.

### 9. Fireworks AI
Source: [fireworks.ai/pricing](https://fireworks.ai/pricing)

- Cached input 50% off (weaker than OpenAI/Anthropic's 90%)
- Batch inference same price
- Fine-tuning per 1M tokens: ≤16B LoRA SFT $0.50 / Full $1.00; 16-80B $3/$6; 80-300B $6/$12; >300B $10/$20
- Embeddings: ≤150M $0.008/M tokens, Qwen3 8B $0.10/M
- GPU on-demand: H100/H200 $7/h, B200 $10/h, B300 $12/h

**Reverse pricing signal**: Fireworks H100 $7 > Modal $3.95 > Beam $3.50 — same hardware, 2x spread. Fireworks bets on "speed-optimized inference engine premium," not bare GPU price.

### 10. ElevenLabs
Source: [elevenlabs.io/pricing](https://elevenlabs.io/pricing)

| Plan | Price | Credits | ≈min TTS |
|---|---|---|---|
| Free | 0 | 10k | 10 |
| Starter | $6 | 30k | 30 |
| Creator | $11 | 121k | 121 |
| Pro | $99 | 600k | 600 |
| Scale | $299 | 1.8M | — |
| Business | $990 | 6M | — |
| Enterprise | custom | — | — |

Per 1000 chars $0.17-0.36 (tier-discounted). Voice cloning: Starter → Instant, Creator → Professional, Scale → 3, Business → 10.

**Reverse pricing signal**: Free tier only 10 min (stingy). Pro $99/600 min = $0.165/min, Business $990/6M = $0.10/min — incentive to skip middle tiers and jump to Business.

### 11. Hume AI
Source: [hume.ai/pricing](https://www.hume.ai/pricing)

EVI (voice) per minute: Starter $0.07 / Creator $0.07 / Pro $0.06 / Scale $0.05 / Business $0.04.

Expression Measurement: video+audio $0.0828/min, audio $0.0639/min, image $0.00204/image, text $0.00024/word.

**Reverse pricing signal**: Hume $0.04-0.07/min vs ElevenLabs ~$0.165 (Pro) — Hume *differentiates on "empathic" but prices BELOW*. Betting on enterprise voice-agent volume.

### 12. Perplexity Sonar API
Source: [docs.perplexity.ai](https://docs.perplexity.ai/guides/pricing)

Token per 1M: Sonar $1/$1, Sonar Pro $3/$15, Sonar Reasoning Pro $2/$8, Sonar Deep Research $2/$8 + citation $2 + reasoning $3.

Request per 1k requests (search-context size): Sonar low $5 / med $8 / high $12; Sonar Pro $6/$10/$14; Sonar Reasoning Pro $6/$10/$14; Pro Search mode $14/$18/$22; Search queries (Deep Research) $5/1k.

Total cost = token + request fee (dual-axis).

**Reverse pricing signal**: Only company with dual-axis token + request pricing — because their cost includes LLM token *and* search-API + index cost. The pricing structure exposes the actual COGS structure.

### Bonus · v0 / Vercel + Notion AI + HuggingFace + OpenRouter

- **v0**: Free $5 credit + 7 messages/day cap; Team $30/user with $30 credit + $2/day login bonus; Business $100/user (same credit, default training opt-out); Enterprise custom + no training. **Business premium $70 over Team is pure data-privacy premium.**
- **Vercel AI Gateway**: pass-through, no markup. Vercel Agent $0.30/action + token pass-through.
- **Notion AI**: Custom Agents $10/1000 monthly credits (pay-as-you-go). Notion was *forced* to break "AI included in seat" because inference isn't fixed cost.
- **HuggingFace**: PRO $9/mo, Team $20/seat, Enterprise $50/seat. Inference Endpoints T4 $0.50/h → H100 $4.50/h → B200 $9.25/h. Inference Providers free $0.10, PRO $2, Team/Ent $2/seat. **Markup zero (pass-through).**
- **OpenRouter**: token zero markup, **profit on top-up fee 5.5% (card) / 5.0% (crypto), $0.80 minimum**. BYOK 1M req/mo free, 5% rate over. The middleware's only sustainable model.

---

## Five Anti-SaaS Pricing Rules

### 1 · Usage-based is the default; subscription is a patch
- Traditional SaaS: $20/user/mo, all features unlimited.
- AI-native: $20/user/mo **includes** $20 usage credit, overflow at API price.
- Evidence: Cursor, Windsurf, Vercel, v0 all follow `seat + included credits + overflow at cost`.
- Why: tokens are real COGS (30-70%); SaaS marginal cost ≈ 0.
- **Counter-intuitive**: the monthly fee = usage floor + psychological anchor, **not** "unlimited use."

### 2 · Cache / batch discounts are real cost-allocation, not marketing
- Anthropic prompt caching: read -90%.
- OpenAI cached input: -90%.
- Fireworks cached: -50%.
- All Batch API: -50%.
- **Counter-intuitive**: discount is not "promotion" — it's "we can plan capacity if you commit to behavior, so we share savings." **This is the customer making a behavioral commitment in exchange for price.**

### 3 · Self-serve → sales-led is triggered by usage walls, not arbitrary segmentation
- Modal Starter: 10 GPU concurrent hard limit.
- Anthropic API Tier 4: needs $400+ cumulative deposit.
- HF Inference Endpoints: A100+ 8x requires contact.
- v0 Business: Training opt-out is the unlock.
- **Counter-intuitive**: Traditional SaaS enterprise = SSO + SLA + sales support. AI-native enterprise = "you're already burning cash, we must help you optimize or you'll leave." **Sales-led trigger is usage, not logo.**

### 4 · Pricing is a strategic public statement; every price cut is an attack signal
- Together AI's repeated Llama price cuts → attacking Replicate / HF users.
- Modal H100 $3.95 vs Beam $3.50 vs Fireworks $7 → three different strategic positions at same hardware.
- Anthropic Haiku 4.5 priced UP ($0.25 → $1) → public statement "we're not competing on low-end."
- OpenAI cached input 90% off → locking long-context enterprise.
- **Counter-intuitive**: A pricing page is a strategy document. Monitoring competitor pricing diffs is more valuable signal than monitoring Crunchbase funding. **For AI-native GTM, a pricing-diff webhook is mandatory intel infrastructure.**

### 5 · Multi-axis pricing units: token / second / credit / minute / word / image / action
- Anthropic: per token
- Modal / Beam: per GPU-second
- v0: per credit
- ElevenLabs: per character
- Hume: per minute
- Vercel Agent: per action
- Perplexity: per token + per request (dual)
- **Counter-intuitive**: SaaS uses "per seat / month" — one axis. AI-native bills "per real cost driver" — and **the unit IS positioning.** A "per second" company sells infrastructure. A "per action" company sells agent value. **Read the unit, infer the product essence — more accurate than the homepage copy.**

---

## Source Index

- [Claude pricing](https://claude.com/pricing) · [Claude docs pricing](https://docs.claude.com/en/docs/about-claude/pricing) · [Cursor pricing](https://cursor.com/pricing) · [Replicate pricing](https://replicate.com/pricing) · [Together pricing](https://www.together.ai/pricing) · [Modal pricing](https://modal.com/pricing) · [Fireworks pricing](https://fireworks.ai/pricing) · [ElevenLabs pricing](https://elevenlabs.io/pricing) · [Hume pricing](https://www.hume.ai/pricing) · [Vercel pricing](https://vercel.com/pricing) · [v0 pricing](https://v0.app/pricing) · [HuggingFace pricing](https://huggingface.co/pricing) · [Notion pricing](https://www.notion.com/pricing) · [Granola pricing](https://www.granola.ai/pricing) · [Windsurf pricing](https://windsurf.com/pricing) · [Beam pricing](https://docs.beam.cloud/v2/resources/pricing-and-billing) · [Perplexity Sonar pricing](https://docs.perplexity.ai/guides/pricing) · [OpenRouter pricing](https://openrouter.ai/pricing) · [OpenAI pricing summary](https://costgoat.com/pricing/openai-api) · [Product Hunt API](https://api.producthunt.com/v2/docs) · [HN Algolia API](https://hn.algolia.com/api) · [HuggingFace Hub API](https://huggingface.co/docs/hub/api)
