# Helmsman · Active Signal Library

> Our 9 active signals (of 22 in the parent library). Chosen based on Helmsman ICP (Stage 3-4 AI-native startups with $5k-50k LLM spend).

## Active Set

### A1 · GitHub Stars Velocity (active)
- **Tracking**: any repo in `Awesome AI Agents` lists, plus `awesome-langchain`, `awesome-llm-apps`
- **Threshold**: 200+ stars in 7 days fires alert
- **Hook**: "Saw {repo} jump {N} stars this week. We help teams in your shape catch agent regressions when traffic surges from launches like this. 15 min?"
- **Combination**: +2 if their tech profile (from `helmsman-cli` inferred-dep scanning) shows multi-model use → strong fit

### A2 · New-Org First-Repo Burst (active)
- **Tracking**: GitHub Search `created:>{last_30d} stars:>500 in:description "agent" OR in:description "llm"`
- **Threshold**: any new org breaking 500 stars in first 30d
- **Hook**: "Saw {org}/{repo} just shipped. Quick technical chat about how you're planning to monitor reliability as you scale? 15 min."

### B3 · OpenRouter Usage Leaderboard (active, high priority)
- **Tracking**: weekly scrape of openrouter.ai/rankings
- **Threshold**: any new entrant in top 100, or any model jumping >200% in week
- **Hook (for the company behind the new model)**: "Noticed your model jumped to #X on OpenRouter. As customers swap to you, they'll hit regression-detection pain. Want our analysis of typical first-week regression patterns?"

### B4 · Foundation-Model Release Window (active, critical)
- **Tracking**: RSS on Anthropic blog, OpenAI blog, Google AI blog
- **Threshold**: every major release (model number bumps)
- **Action**: Maya posts within 6 hours with our analysis; SDR sequence within 24h to all Stage 3-4 ICP accounts
- **Hook**: "Claude 4.7 dropped {N hours} ago. Your eval baselines need to re-run before your users notice. We can ship that for you today."
- **Combination**: +3 if account has previously evaluated us → highest priority

### B6 · MCP Server Publication (active)
- **Tracking**: weekly scrape of modelcontextprotocol.io/servers, plus PRs to anthropic/skills repo
- **Threshold**: any new MCP server from a company in our ICP
- **Hook**: "Saw your MCP server for {capability}. Curious how you're tracking agent-initiated vs human-initiated quality. Quick chat?"
- **Status**: highest signal — MCP publishers are 100% AI-native (this is our Constitution #6 wedge)

### C1 · Replicate / Modal Public Model Deployments (active)
- **Tracking**: weekly poll of Modal public templates + Replicate models filtered to user accounts that publish > 3 models in 30 days
- **Threshold**: company with 3+ deployments
- **Hook**: "You're shipping models fast on {provider}. We help teams catch the quality drift across {N} different deployments simultaneously. Demo?"

### C3 · Inference-Provider Price-Change Events (active)
- **Tracking**: weekly diff of Together / Fireworks / Replicate / Modal pricing pages
- **Threshold**: any 10%+ change in any GPU/token price
- **Action**: Maya tweets + Yvonne writes blog within 24h analyzing impact on customers
- **Hook (to existing customers of the provider that cut)**: "Together just cut Llama 70B 20%. Worth checking your eval baseline — provider price cuts often correlate with quality drift. Want to run a comparison?"

### D1 · HN Front-Page AI Story (active)
- **Tracking**: HN Algolia API poll, 3x/day
- **Threshold**: >300 points + AI keyword in story
- **Hook**: "Saw your post on HN. The traffic surge you're about to see usually breaks something in agent reliability. We can be your insurance for 30 days, free."
- **Combination**: +3 if account already on our radar from B3 or B6

### D7 · AI KOL Twitter Mentions (active, limited paid quota)
- **Tracking**: X API queries for product-name mentions by named KOLs (Karpathy, Swyx, Simon Willison, Logan Kilpatrick, Hamel Husain, Eugene Yan)
- **Threshold**: any positive mention of our product or category by these accounts
- **Action**: Maya replies in-thread within 30 min; Yvonne traces traffic spike to landing page
- **Hook**: outbound NOT triggered directly; this is a brand signal, used for trend tracking

## Signal Combination Rules (Helmsman-specific)

- **A1 (GH velocity) + B4 (model release)** → company is scaling on the new model. Outbound this week, priority alert.
- **B6 (MCP server publish) + C1 (multi-model deployer)** → AI-native technical posture confirmed. Auto-assign to Maya for personal touch.
- **C3 (price cut at provider X) + customer using provider X** → cross-sell "monitor for price-cut-induced drift." Existing customer expansion play.
- **D1 (HN frontpage) + Stage 3-4 ICP** → highest immediate value outbound; 24h window.

## Decommissioned Signals

- **Funding announcements** (traditional) — tested in 2026-Q1, low correlation with eval purchase intent. Removed.
- **LinkedIn employee growth** — tested, AI-native companies hire faster than LinkedIn updates. Removed.
- **Job postings** — tested, anti-pattern for our ICP (real engineers don't broadcast eval-tool needs in JDs).

## Quarterly Signal Audit

Run `skills/weekly-drift-audit` on signal performance every 4 weeks.

Last audit (2026-05-04):
- B4 reply rate: 41% (highest of all signals)
- B6 reply rate: 38%
- D1 reply rate: 27%
- A1 reply rate: 18% (in decline; reconsider weighting)
- C1 reply rate: 22%

Action: weight B4 + B6 higher in `icp-scoring`; deprecate A1 thresholds tighter.
