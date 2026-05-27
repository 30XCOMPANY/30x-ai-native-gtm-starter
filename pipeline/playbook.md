# pipeline/playbook.md · Sales process

> How we sell. Stages, ownership, conversion targets, what each stage requires.

---

## Stages

| # | Stage | Definition | Exit criteria | Conversion target |
|---|---|---|---|---|
| 1 | **Signal fired** | A real-time event indicates buying window | Account scored against ICP | — |
| 2 | **Qualified** | Passes ICP hard qualifiers | First-touch outreach sent | 30–40% of fired signals |
| 3 | **Engaged** | Reply received OR product trial | First call scheduled | 10–20% of qualified |
| 4 | **Discovery** | First call done, problem mapped | Problem-fit confirmed | 60% of engaged |
| 5 | **Evaluation** | Trying the product / running POC | Decision criteria locked | 50% of discovery |
| 6 | **Commit** | Verbal yes, contract path | Contract sent | 60% of eval |
| 7 | **Closed** | Signed contract | Onboarding kickoff | 80% of commit |

Industry benchmark conversion (rough): qualified → closed ≈ 5–10% for AI-native B2B SaaS. Below 3% means a stage is broken — usually #3 or #5.

---

## Stage ownership

| Stage | Owner | Tools |
|---|---|---|
| 1–2 | Marketing / SDR | `skills/icp-scoring`, `pipeline/signals.md` |
| 3 | SDR or founder | `skills/outbound-sequence`, `pipeline/sequences/` |
| 4 | Founder / AE | `skills/technical-poc-brief`, `assets/decks/discovery.md` |
| 5 | AE / SE | `assets/decks/evaluation.md`, `pipeline/objections.md` |
| 6 | Founder / AE | Pricing + legal |
| 7 | CS / Ops | Onboarding flow (see `examples/helmsman/` for sample) |

---

## What each stage REQUIRES before advancing

**Signal → Qualified**:
- Hard ICP qualifiers checked (see `strategy/icp.md` Section 6)
- Champion identified (name + role)
- Decision-maker hypothesized

**Qualified → Engaged**:
- First-touch sent within 48h of signal
- Personalized (not template — signal-specific hook in first line)
- Single CTA in first touch

**Engaged → Discovery**:
- 15-min call scheduled within 7 days of engagement
- Prep doc written (`skills/technical-poc-brief`)
- One specific question prepared

**Discovery → Evaluation**:
- Pain confirmed (specific use case, not vague interest)
- Success criteria written down by them
- Timeline agreed

**Evaluation → Commit**:
- POC results documented (link from outputs/)
- Champion mapped + decision tree understood
- Pricing range floated, not silent

**Commit → Closed**:
- Legal review timeline known
- Contract owner identified on their side
- Verbal commit confirmed in writing

---

## Where to log each deal

For each active deal, create `outputs/deal-{slug}.md` with:
- Account name + URL
- Stage + last touch
- Champion + decision-maker
- Next step + due date
- Risk flags

Refresh weekly.

---

> **[PROTOCOL]**: Conversion rates from stage to stage are the most honest signal of where your process is broken. Track them. Don't optimize "more activity" — optimize the broken stage.
