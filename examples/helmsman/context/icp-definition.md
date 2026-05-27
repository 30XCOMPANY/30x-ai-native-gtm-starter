# Helmsman · Living ICP

> Last full revision: 2026-04-15. Evolution log below.

## Section 1 · AI-Native ICP Dimensions

### 1.1 LLM Maturity Stage

- [x] **Stage 3 — Production LLM in user-facing product** (primary)
- [x] **Stage 4 — Multi-model router** (premium primary)
- [ ] Stage 5 — fine-tuning / RAG / evals in prod *(secondary; they often build in-house, harder sell but high ACV when won)*

Stage 0-2 disqualified — they don't yet feel the eval pain.

### 1.2 Data Residency × Deployment Mode

- [x] **Public API OK** — Cloud customers (Starter, Team tiers)
- [x] **VPC required** — Enterprise tier ($50K+ ACV)
- [ ] On-prem required — not yet supported; pipeline-deferred until 2026-Q4
- [ ] Air-gapped — out of ICP for now

### 1.3 Model Spend Trajectory

- [ ] Pre-spend
- [ ] Experimental ($0-1k/mo)
- [x] **Pilot ($1k-10k/mo)** — Starter tier ICP
- [x] **Production ($10k-100k/mo)** — Team tier sweet spot
- [x] **Scaled ($100k+/mo)** — Enterprise ICP

AND growth rate:
- [x] **Growing 20-30% / month** — most fit
- [x] **Growing 30%+/month** — highest fit (will be Scaled within 6 months, sell Team now with expansion path)

## Section 2 · Traditional Filters

- **Industry**: AI-native (model labs, AI infra, AI dev tools, agent platforms); AI-heavy mid-market SaaS (where AI is becoming load-bearing)
- **Employee count**: 10-100 (sweet spot 15-50)
- **Geography**: US + Canada + UK + EU (currently SF-time-zone-friendly; Asia hours covered by async)
- **Decision-maker role**: VP Engineering, CTO, Head of AI Platform
- **Champion role**: AI Platform Engineer / Senior AI Engineer (this is the person who finds us)
- **Anti-industry**: Healthcare (HIPAA blocker until SOC2 done), defense (FedRAMP blocker), law (Harvey owns it)

## Section 3 · Anti-ICP

Patterns we explicitly avoid:

- [x] "Exploring AI in 2026" — Stage 0-2; long cycle, low close
- [x] No AI engineer on staff — no internal champion to integrate
- [x] AI used only via ChatGPT Plus / Team — no API spend = no eval pain
- [x] Customer asks "swap your eval model" in first call — they're treating us as a router; defer
- [x] Agency / consultancy buying "for clients" — never integrates, churns at month 3
- [x] Customer's CEO wants "AI strategy consulting" — wrong product
- [x] Pre-Series-A startup with <$5k/mo LLM spend — they haven't felt the pain

## Section 4 · Living ICP Cadence

- **Weekly**: Maya reviews top-of-funnel signals from `signal-library.md`. Updates Current Priorities in CLAUDE.md.
- **Monthly**: Yvonne refreshes reply-rate by signal type; flags any signal that's lost its punch.
- **Quarterly**: Full ICP revisit. Last completed 2026-04-15. Next: 2026-07-15.
- **Event-triggered**: Foundation-model release with eval-relevant capability jump → 48h re-assessment.

## Section 5 · Evolution Log

### 2026-04-15 · Raise Maturity floor from Stage 3 to Stage 3/4 mix
- **Changed**: Primary ICP from "Stage 3" to "Stage 3 (Starter) + Stage 4 (Team)"
- **Trigger**: Q1 win-rate data showed Stage 4 customers (multi-model routers) close at 47% vs Stage 3 at 22%, with 4x ACV.
- **Reasoning**: Multi-model routing teams have *more* eval pain because they're comparing across models. Our product is built for this. Lean in.
- **Affected**: Outbound list re-segmented. Three SDR sequences rewritten for multi-model context.

### 2026-03-02 · Add VPC deployment to in-ICP
- **Changed**: Data Residency Section 1.2 added VPC required as in-ICP
- **Trigger**: Three Series B AI startups asked about VPC in one week. Two of them are now closed Enterprise.
- **Reasoning**: VPC adds engineering work, but ACV jumps from $6k/yr Team to $80K+/yr Enterprise. Worth it.
- **Affected**: Daniel hired SRE; deployment-engineering pipeline started.

### 2026-01-08 · Disqualify pre-Series-A AI startups
- **Changed**: Section 3 Anti-ICP added "Pre-Series-A with <$5k LLM spend"
- **Trigger**: Q4 2025 conversion data — pre-Series-A close rate 3%, average sales cycle 4 months, churn at month 2.
- **Reasoning**: They love the product, can't justify $99/mo to budget. Sell to them after their Series A; offer Free CLI now.
- **Affected**: Maya stopped responding to pre-Series-A inbound except with Free CLI invite.

### 2025-11-12 · Drop healthcare from ICP until SOC2
- **Changed**: Section 2 Anti-industry added Healthcare
- **Trigger**: 3 healthcare deals stalled in compliance review at month 4-6. We don't have SOC2 yet.
- **Reasoning**: Burning sales cycles. Defer category until SOC2 Type II shipped (target 2026-Q3).
- **Affected**: SDR no longer prospects healthcare AI startups; Maya politely declines inbound from this segment.

## Section 6 · Qualification Framework

**Hard qualifiers** (all must be true):
- [x] LLM Maturity Stage 3 or 4
- [x] Data Residency: Public API OR VPC
- [x] Decision authority for AI tooling exists in VP Eng / CTO / Head of AI Platform role

**Soft qualifiers**:
- [x] Industry in target list (AI-native or AI-heavy SaaS) (+2)
- [x] Champion identified (specific AI Platform Engineer) (+2)
- [x] Model spend growing 20%+/month (+3)
- [x] Already on Braintrust / Langfuse / LangSmith (we win on production reliability angle) (+2)
- [x] Already uses Anthropic Claude (our default judge model) (+1)
- [x] Has shipped public MCP server (+2)
- [x] Founder publicly active on AI-native topics (+1)

**Disqualifiers** (any → auto-reject):
- Anti-ICP pattern hit
- Asks to swap eval model in first call
- Pre-Series A with <$5k LLM spend (offer Free CLI)
- Healthcare / Defense / Legal (until compliance built)

## Section 7 · Reference Cases

- **Most ICP-aligned win Q1 2026**: "Atlas Robotics" (fictional) — Series B AI agent platform, $25K/yr Team contract, expanded to $90K/yr Enterprise in 4 months
- **Surprise win**: "Glaze Studios" — design tool that recently added AI features, originally outside ICP (AI-feature-heavy SaaS, not AI-native). Closed because their head of AI eng was a Maya ex-colleague. Learning: warm intros override ICP.
- **Surprise loss**: "Vector Compute" — perfect ICP fit, lost to Braintrust because Braintrust shipped their integration with the customer's framework 2 weeks earlier. Learning: integration depth > positioning.
- **Reference customer for inbound**: Lovable case study at helmsman.ai/customers/lovable
