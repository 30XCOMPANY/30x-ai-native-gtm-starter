# context/icp-definition.md · Living ICP

> Your ICP for AI-native GTM. This is not a slide in a deck — it's a weekly-revised artifact with an evolution log.
>
> **Constitution: [#1 Living ICP](../CLAUDE.md#1-living-icp).** Evidence base: [`research/01-capability-obsolescence-and-icp.md`](../research/01-capability-obsolescence-and-icp.md).

---

## Why this file looks different from your last ICP doc

Traditional B2B SaaS ICP slices on three axes:
- **Industry** (SaaS, FinTech, Healthcare…)
- **Size** (employee count, revenue band)
- **Role** (decision-maker title)

These three axes are **nearly uncorrelated with AI purchase decisions.** A 200-person FinTech CTO and a 50-person dev-tool CEO might both be your customer or both ignore you. The deciding variable is *what AI stage they're at*.

AI-native ICP slices on three different axes — they go *first* in this file. Traditional axes go second, as supporting filters.

---

## Section 1 · The Three AI-Native ICP Dimensions

### 1.1 LLM Maturity Stage

Pick exactly one (or one range) that defines your ICP. Evidence: cited in `research/01...md` (Cursor, Glean, LangSmith, Humanloop all segment on this implicitly).

- [ ] **Stage 0 — No LLM API yet.** Has heard of ChatGPT, hasn't built anything.
- [ ] **Stage 1 — ChatGPT Plus / Team internally.** Free or low-tier consumer accounts. Not API.
- [ ] **Stage 2 — Prototyping with OpenAI / Anthropic API.** Internal demos, no production traffic.
- [ ] **Stage 3 — Production LLM in user-facing product.** Live customers, real traffic.
- [ ] **Stage 4 — Multi-model router.** Already switching between OpenAI / Anthropic / open models per use case.
- [ ] **Stage 5 — Fine-tuning + RAG + evals in production.** Internal ML/AI engineers. Custom pipelines.

> *Example*: LangSmith targets Stage 3+ explicitly — their positioning is "production observability." A Stage 1 customer would be churn.

> *Common mistake*: targeting Stage 0-1 because they're abundant. They're abundant because they don't know what to buy. **You can't sell to people who haven't felt the pain yet.** Let OpenAI educate them; you sell to the survivors of stage 1.

---

### 1.2 Data Residency × Deployment Mode

Your customer's data-governance posture **can determine whether the deal closes at all**, regardless of price or feature fit. Evidence: Harvey (Azure-only), Codeium (privacy-first sub-segment), Vellum (lists 4 deployment modes).

Pick which postures are in / out of your ICP:

| Posture | Description | In? |
|---|---|---|
| Public API OK | Customer accepts OpenAI / Anthropic public API; no special hosting | [ ] |
| Cloud-vendor managed only | Must run on Azure / AWS / GCP customer's own tenant | [ ] |
| VPC required | Must deploy inside customer's VPC | [ ] |
| On-premise required | Customer's own datacenter, no cloud | [ ] |
| Air-gapped | No external network access at all | [ ] |

> *Strategic note*: This dimension is **bimodal** for most companies — you either own the entire "VPC + on-prem" tail or you serve only public-cloud customers. Trying to span both with one team kills you. Pick a side.

> *Counter-example*: Harvey forced its entire ICP to "law firms accepting Azure OpenAI deployment." That narrowed the pool to maybe 100 firms but made every deal sign at 6+ figures.

---

### 1.3 Model Spend Trajectory

Forward-looking budget indicator. Traditional SaaS uses "annual software budget" — irrelevant here because LLM spend is token-elastic, not fixed.

Define your ICP by current LLM spend + growth rate:

- [ ] **Pre-spend** — $0 / month
- [ ] **Experimental** — $0 - $1k / month
- [ ] **Pilot** — $1k - $10k / month
- [ ] **Production** — $10k - $100k / month
- [ ] **Scaled** — $100k+ / month

AND growth rate:

- [ ] Flat (declining or steady)
- [ ] Growing 10-30% / month
- [ ] Growing 30%+ / month (will be your ICP at scale within 6 months — talk to them now)

> *Example*: A "Pilot tier + 30%+ growth" account today is a "Scaled" account in 6 months. Sell them eval / observability / multi-model-router infrastructure before they need it — they're committing now, can't churn later.

---

## Section 2 · Traditional Filters (Secondary)

Once AI-native axes are set, these refine.

- **Industry**: [fill]
- **Employee count**: [fill, range]
- **Geography / data-residency regulatory**: [fill — relates to 1.2]
- **Decision-maker role**: [fill]
- **Champion role** (often different from decision-maker in AI buys): [fill]
- **Anti-industry** (industries that look like ICP but don't convert): [fill]

---

## Section 3 · Anti-ICP

What looks like ICP but isn't. Critical because AI-native sales cycles waste *more* time on bad fits than traditional SaaS.

Common anti-ICP patterns:

- [ ] **"We're exploring AI"** — Stage 0-1 prospects with no urgency. Long sales cycle, low close rate.
- [ ] **"Curious CTO" without an AI engineer on staff** — no internal champion to drive integration.
- [ ] **High-compliance industry that hasn't budgeted compliance review** — deal sits in legal for 9 months.
- [ ] **Customer expects ChatGPT-class capability at startup pricing** — pricing expectation mismatch.
- [ ] **Customer wants to swap your underlying model** — you're being treated as a router, your differentiation is dying.
- [ ] **Your specific anti-ICP**: [fill]

---

## Section 4 · Living ICP Cadence

This file gets touched at three frequencies:

| Cadence | What happens | Time cost |
|---|---|---|
| **Weekly** | Refresh "Current priorities" + review reply rates on outbound, log surprising wins/losses | 15 min |
| **Monthly** | Update LLM Maturity Stage definitions if foundation-model release changed them, refresh anti-ICP list | 30 min |
| **Quarterly** | Full ICP revisit: add evolution log entry with reasoning, decide if dimensions themselves changed | 1 hour |
| **Event-triggered** | Foundation-model release with capability jump in your vertical → emergency revisit | 30 min same week |

> *Why event-triggered matters*: Jasper's ICP died one week after GPT-3.5 launched. Inflection's ICP was consumed by ChatGPT Free. **A static ICP doc in AI-native = a calendar invite for irrelevance**.

---

## Section 5 · Evolution Log

> Append-only. Six months of this log is more valuable than the current ICP definition.

Required fields per entry:
- **Date**
- **What changed** (which dimension, old → new value)
- **Trigger** (foundation-model release? customer feedback? competitor move? data-driven insight?)
- **Reasoning** (why this change, not just "we updated it")
- **Affected stakeholders** (who needs to know — sales, marketing, product)

**Template entry**:

```
### 2026-MM-DD · [one-line summary]
- **Changed**: [dimension] from [old] to [new]
- **Trigger**: [e.g., "Claude 4.7 released, can now handle long-context code review natively"]
- **Reasoning**: [why; what evidence; what we lose / gain by narrowing or widening ICP]
- **Affected**: [e.g., "outbound list rebuild needed; existing pipeline accounts re-scored"]
```

**Examples — what good entries look like**:

```
### 2026-04-12 · Drop Stage 2 prospects after Claude 4.7
- **Changed**: LLM Maturity floor from Stage 2 to Stage 3
- **Trigger**: Claude 4.7 released 2026-04-10. Long-context + tool use now strong enough that Stage 2 prospects can build internally without our product.
- **Reasoning**: Win rate on Stage 2 was 8% last quarter (vs 31% Stage 3+). Our wedge is post-prototype debugging — Stage 2 hasn't hit the pain yet.
- **Affected**: outbound list -40%, but pipeline conversion projected up. Reallocate SDR effort to Stage 3+ via GitHub-velocity signal.
```

```
### 2026-02-20 · Add air-gapped as in-ICP after defense customer
- **Changed**: Data Residency expanded to include "Air-gapped"
- **Trigger**: Inbound from defense contractor (Lockheed div) asking for air-gapped install.
- **Reasoning**: Air-gapped is 1 deal so far but ACV 5x mid-market median. Three other defense leads suggest a vertical exists. Worth a 2-quarter test.
- **Affected**: deployment-engineering hire JD updated; pricing page adds "Air-gapped contact us"; competitor radar adds Anduril Lattice as adjacency.
```

---

## Section 6 · Qualification Framework

When Claude scores a prospect (via `skills/icp-scoring/`), it uses these as binary qualification gates:

**Hard qualifiers** (must be true):
- [ ] LLM Maturity Stage in target range
- [ ] Data Residency posture compatible
- [ ] Decision authority for AI tooling exists in target role

**Soft qualifiers** (count points):
- [ ] Industry in target list (+2)
- [ ] Champion identified (+2)
- [ ] Model spend trajectory growing 30%+ (+3)
- [ ] Already using a competitor we displace well (+2)
- [ ] Already using a complementary tool we integrate with (+1)

**Disqualifiers** (auto-reject):
- [ ] Hit any anti-ICP pattern (Section 3)
- [ ] Asks about "swapping out the model" in first call → you're being commoditized → defer

---

## Section 7 · Reference Cases

Customers / wins / losses that anchor each dimension. Update monthly.

- **Most ICP-aligned win this quarter**: [name + why]
- **Surprise win (low expected fit, closed anyway)**: [name + why → may indicate ICP expansion]
- **Surprise loss (high expected fit, didn't close)**: [name + why → may indicate hidden disqualifier]
- **Reference customer for inbound social proof**: [name + URL to case study]

---

> **[PROTOCOL]**: When this file changes, also update `CLAUDE.md` Current priorities if the change reshuffles what's strategic. Add the change to Section 5 Evolution Log with reasoning.
