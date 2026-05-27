# strategy/positioning.md · Technical Credibility Ladder

> Replaces traditional "value pillars" and "messaging matrix." AI buyers don't read marketing copy — they read benchmarks, code, and commit graphs. This file defines the proof rungs your customer climbs before buying.
>
> 
---

## Why this file is structured as a ladder

Traditional positioning frameworks (value pillars, jobs-to-be-done, messaging matrix) assume your buyer is a *business decision-maker* who needs persuasion. AI-native buyers are *engineers and AI-curious PMs* who need **proof, in a specific order**:

1. Does it exist? (Quick technical sniff test)
2. Does it work? (Benchmark / demo)
3. Does it work in my situation? (Integration depth)
4. Does it scale? (Production evidence)
5. Will it still work in 6 months? (Capability obsolescence resistance)

Each of these is a rung. The customer climbs in order. **You can't skip rungs** — leading with "case study" before the customer can verify the basic claim wastes the call.

Cursor scaled to $2B ARR by **letting the product be the proof at every rung**. Cline shipped $32M Series A on a single rung: *"we don't profit on inference."* Modal ships rungs in this order: docs → code samples → GPU price page → customer logos.

---

## The Five Rungs

### Rung 1 · "Does it exist?" — The Sniff Test

What a developer / technical PM checks in the first 30 seconds.

- **Public GitHub repo** with recent commits (last 7 days)?
- **Live demo on landing page** (not a contact form)?
- **Pricing visible** (or explicit "self-serve" badge)?
- **Docs link in nav** (not buried in footer)?
- **Founders on Twitter / X** with technical posts?

**Failure mode at Rung 1**: pitch deck-style landing page, "request a demo" gate, no public GitHub. The buyer bounces in 10 seconds.

**Your Rung 1 proof points** (fill in):
- [ ]
- [ ]
- [ ]

---

### Rung 2 · "Does it work?" — Benchmark or Working Demo

What the buyer verifies in the first 5 minutes.

**Proof artifacts** (you need 2-3, not all):
- **Benchmark vs alternative**: a chart or table showing your output / latency / cost beating a named comparison (yourtool vs OpenAI / Cursor / Together / Modal).
- **Code sample they can copy-paste**: 5-10 lines that does something valuable in <60 seconds.
- **Live playground**: in-browser demo with default examples + edit-and-run.
- **One-click reproduction**: a CodeSandbox / Replit / v0 / Vercel template that recreates your demo in their environment.

**Failure mode at Rung 2**: vague claims ("10x faster," "more accurate") with no comparison artifact. The technical buyer either downgrades you mentally or builds their own bench, both of which kill the sale.

**Your Rung 2 proof points** (fill in):
- [ ]
- [ ]
- [ ]

---

### Rung 3 · "Does it work in my situation?" — Integration Depth

What the buyer evaluates over the first hour.

**Proof artifacts**:
- **SDKs for their stack** (Python + TypeScript at minimum; Go / Rust for infra; Swift / Kotlin for mobile).
- **Pre-built integrations**: which tools you already integrate with (LangChain, Vercel AI SDK, Cursor, Claude Code, n8n, Zapier).
- **MCP server** so your tool is callable from any AI agent (this is agent-native distribution — see `CLAUDE.md`).
- **Deployment options** that match their Data Residency posture (see `icp-definition.md` Section 1.2).
- **API parity with OpenAI / Anthropic SDK shape** (where applicable) — buyer doesn't have to learn new SDK semantics.
- **Latency / throughput numbers under realistic load**.

**Failure mode at Rung 3**: technically working product that requires 2 days of integration work for evaluation. The buyer pauses the eval, never returns.

**Your Rung 3 proof points** (fill in):
- [ ]
- [ ]
- [ ]

---

### Rung 4 · "Does it scale?" — Production Evidence

What the buyer (or their security/architecture review) confirms before signing.

**Proof artifacts**:
- **Logos of similar-shape customers** (similar maturity stage, similar deployment posture).
- **Public customer stories** with quantifiable outcomes (latency / cost / quality numbers).
- **Status page** with uptime history (last 90 days).
- **SOC 2 / ISO 27001 / HIPAA / FedRAMP** (whichever your ICP requires).
- **Capacity & scaling commitments** (concurrent throughput, rate limit policy, GPU availability).
- **On-call / incident response policy**, especially for inference customers.

**Failure mode at Rung 4**: live customers but no public proof + no compliance certifications. Security review blocks deal at month 4.

**Your Rung 4 proof points** (fill in):
- [ ]
- [ ]
- [ ]

---

### Rung 5 · "Will it still work in 6 months?" — Capability Obsolescence Resistance

What the technical-savvy buyer assesses last. **Most underrated rung** — and where you can win deals against incumbents.

**Proof artifacts**:
- **Public stance on foundation-model dependency**: are you trying to outrun GPT-N+1, or are you complementary to whatever model wins?
- **Model-agnostic architecture**: can you swap from OpenAI → Anthropic → open models without code change for the customer?
- **Workflow / data moat narrative**: what proprietary work do you do that no foundation model can replace?
- **Recent product velocity**: shipping cadence in the last 6 months (commit graph, changelog).
- **Founder posts on capability shifts**: public reflection on past model releases — does the founder understand the obsolescence dynamic?

**Failure mode at Rung 5**: silence. Buyer assumes you'll be Jasper in 12 months.

**Your Rung 5 proof points** (fill in):
- [ ]
- [ ]
- [ ]

---

## Anti-Positioning · What Not To Say

These phrases trigger immediate downgrades in AI-native technical buyers:

- **"AI-powered"** — meaningless; what AI?
- **"Best-in-class"** — by what benchmark?
- **"Game-changing"** — generic SaaS-speak; AI buyers smell it.
- **"Trusted by leading enterprises"** — name them or don't say it.
- **"Powered by [GPT-4 / Claude / Gemini]"** as primary positioning — the model isn't your product. If you lead with "powered by GPT-4," buyer asks why they don't just use GPT-4 directly. (See Jasper death case.)
- **"Save N hours per week"** — quantify by *what tasks*, *vs which baseline*. Bare time-saving claims are SaaS marketing residue.

---

## Messaging by Channel

**Landing page hero (above the fold)**:
- 1 sentence specific claim that addresses Rung 2 directly.
- 1 code snippet or visual that demonstrates Rung 2.
- 1 "Try it" CTA (live playground) AND 1 "View docs" CTA.
- NOT "Book a demo" as primary CTA at this stage.

**Twitter / X founder post template** (the Lovable / Bolt pattern from `examples/our-flavor/research/02-gtm-motions-by-company.md`):
- Specific number + specific time period
- "We just shipped X" / "we hit Y" / "we're now at Z"
- Optional: short demo video
- Optional: ARR-class transparency if you're comfortable
- Almost never: marketing copy adjectives

**Sales call open** (first 30 seconds):
- Skip qualifying questions until rung 2.
- Lead with: "Here's a 30-second demo, then you ask me anything." Then *actually demo*.

**Sales call close** (last 5 minutes):
- Confirm which rung the customer is on.
- Set explicit next step matching that rung — "here's the SDK link" (rung 3) or "introducing you to a similar-shape customer" (rung 4).

---

## Rung Diagnostic for Existing Pipeline

Quarterly exercise: for each open opportunity, mark which rung the customer is on:

| Account | Rung | Stalled? | Next action |
|---|---|---|---|
| [name] | 1-5 | yes/no | [action matched to rung] |

**Stalled-rung diagnostics**:
- Stalled at Rung 1 → fix landing page; you have a sniff-test problem.
- Stalled at Rung 2 → build the missing benchmark / demo; you have a proof problem.
- Stalled at Rung 3 → ship the missing SDK / integration; you have a fit problem.
- Stalled at Rung 4 → invest in case studies + compliance; you have a trust problem.
- Stalled at Rung 5 → write the foundation-model obsolescence narrative; you have a defensibility problem.

---

> **[PROTOCOL]**: When this file changes (new rung proof point added, anti-positioning updated), check `skills/technical-poc-brief/` and `skills/signal-to-content/` — outbound copy templates often quote rung proof points directly.
