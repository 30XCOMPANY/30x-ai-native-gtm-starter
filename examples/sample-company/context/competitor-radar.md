# Helmsman · Two-Layer Competitor Radar

> Last full review: 2026-05-12. Next: 2026-08-12.

---

## Section 1 · Traditional Competitive Radar

### Braintrust — direct, the one to beat
- **Last updated**: 2026-05-12
- **Tier**: Direct
- **What they sell**: LLM eval + observability + dev playground. SaaS, eng-focused.
- **ICP overlap with us**: ~70%
- **Pricing model**: Free → Pro $50/seat → Enterprise. Per-seat + usage hybrid.
- **Recent funding / valuation**: $35M Series A 2025-Q2 (announced); est. $200M post-money
- **Founder / team size**: founded by Stripe / Figma alums. Estimated ~35 people.
- **Where we win**:
  - Production reliability monitoring (they're dev-time-focused; we're prod-time)
  - Multi-model judging (they prefer single judge model; we explicitly multi-model)
  - OSS CLI runs without their cloud (Cline-style trust narrative)
- **Where we lose**:
  - Brand recognition; they have stronger ecosystem partnerships (LangChain endorsement)
  - Better playground / dev-time UX
  - Strong DevRel pipeline already
- **Recent product moves**: 2026-04 shipped "Auto-Eval" — uses Claude to autonomously write evals from production traces. Direct overlap with our Q3 roadmap. We need to move.
- **Recent pricing moves**: 2026-03 added per-trace overage charges. Customer feedback was negative.
- **Customer overlap evidence**: Lovable evaluates both; Atlas Robotics evaluated Braintrust before us.
- **Honest assessment**: We do not beat Braintrust on dev-time evals — they're better there. We beat them when the buyer cares about *production reliability* (their primary concern is regression detection, not prompt iteration). Sales positioning leads with "we monitor what you ship, they help you ship faster" — complementary framing rather than head-on.

### Langfuse — OSS-led, complementary more than competitive
- **Tier**: Adjacent
- **What they sell**: Open-source LLM tracing + analytics. Self-hosted by default; managed cloud as upsell.
- **ICP overlap**: ~50% (we both attract OSS-friendly buyers, but their primary use is observability not eval)
- **Pricing model**: OSS free; Cloud $59/mo Pro → Enterprise custom
- **Founding / team**: German team, est. ~12 people. Strong dev-community presence (8k+ stars).
- **Where we win**: Eval depth, especially regression detection; managed VPC option
- **Where we lose**: Self-hosted parity (their entire product is open source; ours has a paid managed core)
- **Honest assessment**: Langfuse customers often *also* use Helmsman — they observe; we evaluate. Joint customer story for outbound: "use Langfuse for tracing, Helmsman for eval & alert."

### LangSmith (LangChain commercial arm) — incumbent, eroding
- **Tier**: Direct
- **What they sell**: LangChain's observability + eval platform. Coupled with LangChain.
- **ICP overlap**: ~40% (their customers are LangChain users; we're framework-agnostic)
- **Pricing**: Free → Pro $50/seat → Enterprise. Per-trace pricing.
- **Where we win**: Framework agnosticism. As more teams move *off* LangChain to Vercel AI SDK / Mastra / DIY, we capture them.
- **Where we lose**: Built-in to LangChain. If buyer is LangChain-native, very sticky.
- **Recent product moves**: 2026-03 layoffs + new pricing tier. Reads as company-stage stress signal.
- **Honest assessment**: LangSmith is in a declining phase; capture displaced LangChain users as they migrate.

### Humanloop — adjacent
- **Tier**: Adjacent
- Not really competitive on production reliability; more prompt management. Mention in completeness only.

---

## Section 2 · Capability Obsolescence Radar

### 2.1 Foundation-model release tracker

| Model | Last release | Next expected | Capability that threatens us |
|---|---|---|---|
| Claude (Anthropic) | 4.7 (2026-04-10) | 5.0 (Q3 2026?) | **Native eval surface in Claude Console** — Anthropic shipped basic eval in 4.6; expecting expansion to "auto-eval my production agent" in 5.0 |
| GPT (OpenAI) | 5.5 (2025-12) | 6.0 (Q4 2026?) | OpenAI Evals product growing; less of a direct threat (different audience) |
| Gemini (Google) | 3.0 (2026-02) | 3.5 (Q3 2026?) | Vertex AI evaluation tools — enterprise threat |
| Llama (Meta) | 4 (2025-10) | 5? | Not directly threatening our category |

### 2.2 Five death patterns (Helmsman self-assessment)

#### Pattern 1 · Wrapper eaten by foundation model
- **Our exposure**: if Anthropic ships "auto-eval my production agent" with same depth as us, we lose 40-50% of dev-time-eval users. Production-reliability + multi-model + remediation use case remains.
- **Plan**: position production-reliability as the core; dev-time eval is the loss-leader entry tier (Free CLI).
- **Score**: 30-60% at risk if Anthropic ships eval expansion in 5.0. Not catastrophic, but plan needed.

#### Pattern 2 · Foundation-model burn-rate crushes you
- **Our exposure**: low. We don't train our own foundation model.
- **Score**: not exposed.

#### Pattern 3 · Hardware loses to phone
- **Our exposure**: not applicable (software product).

#### Pattern 4 · Information intermediary replaced
- **Our exposure**: low. We don't sell knowledge; we sell ongoing monitoring + alerts + a workflow.
- **Score**: not exposed.

#### Pattern 5 · OS / platform integration absorbs the standalone app
- **Our exposure**: medium. If Vercel AI Gateway / Cursor / Claude Code build native eval, we lose entry point.
- **Counter-strategy**: be the partner that ships the integration first. We already shipped Vercel AI SDK partner integration. Cursor extension in flight.
- **Score**: medium exposure, actively defended.

### 2.3 Early-warning signals actively monitored

- [ ] Anthropic DevDay agenda 2026 (when announced) — keyword "production eval" → emergency review
- [ ] Anthropic Skills directory includes "evaluation" category → emergency review
- [ ] OpenAI Evals product roadmap update → 7-day review
- [ ] Customer churn reasons shifting to "we'll just use Anthropic's eval" → 30-day review
- [ ] More than 30% of Cursor / Claude Code users adopt their native eval (when it ships) → review

### 2.4 Emergency response — pre-written

If Anthropic ships full production-eval in Claude 5.0 (2026-Q3 likely):
- **Hour 0**: Maya posts on X within 6 hours acknowledging + framing as "great for the category; here's how our offering remains complementary"
- **Day 1**: founder + GTM + product call; pull SOC 2 forward to capture displaced healthcare/regulated customers
- **Week 1**: Email all customers with comparison + explicit "here's what stays Helmsman, here's what becomes Anthropic, here's why both coexist"
- **Month 1**: Pivot positioning to lead with "multi-model reliability" — drop "evaluation" from the homepage entirely. Eval becomes a tier-1 feature, not the headline.

---

## Section 3 · Quarterly Radar Review Checklist

- [ ] Update each competitor card
- [ ] Add Auto-Eval-class new entrants (Braintrust shipped one in April, expect more this year)
- [ ] Update Section 2.1 with most-recent model release info
- [ ] Re-self-assess Pattern 1 exposure based on Q2 customer mix
- [ ] Run signal-check against `signal-library.md` capability obsolescence signals
