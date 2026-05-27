# Helmsman · Technical Credibility Ladder

> Filled-in example. Last revised 2026-05-12.

## Rung 1 · Sniff Test

- [x] **Public GitHub repo with active commits**: `github.com/helmsman-ai/helmsman-cli` (last commit < 24h, average 5 commits/day)
- [x] **Live demo on landing page**: yes — `helmsman.ai/demo` has live agent trace running with eval scoring updating in real time
- [x] **Pricing visible**: yes, public pricing page with concrete numbers ($99/$499/Custom)
- [x] **Docs link in nav**: top-level "Docs" link, opens to quickstart
- [x] **Founders on Twitter / X with technical posts**: @mayacheng_ai (weekly), @danielpark_eng (technical deep-dives)

## Rung 2 · Does It Work?

Working proofs:

1. **Benchmark vs alternative**: chart on landing page showing Helmsman detects 87% of regression types vs Braintrust 71% vs DIY rolled-your-own 43%. Methodology link goes to GitHub repo with reproduction script.

2. **Code sample that runs in <60 seconds**:
```python
from helmsman import Evaluator

eval = Evaluator(judge="claude-4.6", baseline="2026-05-01")
result = eval.run(agent_traces_url="https://your-otel-endpoint")
print(result.regression_score)  # 0.0-1.0, > 0.3 = concerning
```
The customer's first `pip install helmsman && python eval.py` returns a number within 60 seconds.

3. **Live playground**: `helmsman.ai/playground` lets visitor paste an OTel trace JSON, runs eval client-side, shows result. No signup.

## Rung 3 · Integration Depth

- [x] **SDKs**: Python + TypeScript both mature; Go + Rust experimental.
- [x] **Pre-built integrations**:
  - Vercel AI SDK (auto-export traces) — `@helmsman/vercel-ai`
  - LangChain (tracer hook) — `helmsman-langchain`
  - Vercel AI Gateway (auto-instrument) — native partner
  - OpenTelemetry (any tracer that exports OTLP)
- [x] **MCP server**: `helmsman-mcp` — agents can query "is my last response in a regression band?" from any MCP-compatible client. **This is our Constitution #6 implementation.**
- [x] **Deployment options**: SaaS default, VPC for Enterprise (Helm chart available), on-prem in pipeline
- [x] **API parity**: matches OpenTelemetry standard at trace ingest; matches Anthropic SDK shape for judge calls
- [x] **Latency / throughput**: ingest p95 < 12ms, eval batch p95 < 800ms (judge-model bound), throughput tested to 10k traces/sec/customer

## Rung 4 · Does It Scale?

- [x] **Similar-shape customers visible**: Lovable, Modal, [three undisclosed Series B] — case studies at helmsman.ai/customers
- [x] **Quantified outcomes in case study**: "Lovable cut LLM-related incidents by 73% in 8 weeks"
- [x] **Status page**: status.helmsman.ai · last 90 days uptime 99.97%
- [ ] **SOC 2 Type II** — in progress, target 2026-Q3 (currently Rung 4 weakness)
- [ ] **HIPAA / FedRAMP** — not yet (intentional ICP exclusion)
- [x] **Capacity commitments**: published in Team-tier SLA, 99.9% uptime + 10s alert latency
- [x] **On-call / incident response**: Enterprise tier includes dedicated CSM + Slack Connect + 1-hour critical-incident response

**Stalled-customer recovery pattern**: any account stalled at Rung 4 over the SOC 2 issue is offered "we'll send you our pen-test report + insurance certificate; SOC 2 ships Q3" — converts ~60% of stalled deals.

## Rung 5 · Capability Obsolescence Resistance

- [x] **Public stance on foundation-model dependency**: Maya's January 2026 blog post "Why we don't compete with Anthropic on evals" — argues that **dev-time evals will be commoditized by Anthropic / OpenAI, but production-time reliability monitoring with multi-model + remediation will not** (because the model vendors don't want to be on the hook for multi-model judgment).
- [x] **Model-agnostic architecture**: Helmsman supports Claude / GPT / Gemini / open-model judges; customer can swap.
- [x] **Workflow / data moat**: every customer's eval baseline becomes proprietary regression model trained on *their* traces. Generic eval can't replicate.
- [x] **Recent product velocity**: 47 commits per week (rolling 4-week avg); biweekly release cadence; public roadmap at github.com/helmsman-ai/roadmap
- [x] **Founder posts on capability shifts**: Maya wrote within 48h of Claude 4.7 release with concrete impact analysis; she did the same after GPT-5.4. Pattern of public reflection demonstrates we're tracking capability obsolescence actively.

## Your Rung 5 weakness to address

If a customer challenges with: *"Anthropic just shipped native evals in Claude Console. Why pay you?"*

Response:
> "Anthropic ships single-model dev-time evals. We ship **production-time reliability monitoring across multiple models**, including catching regressions when you swap from Claude 4 to 4.7. The eval primitive is commoditizing; the multi-model + remediation + drift-tracking workflow is not. Plus we'll auto-import any Anthropic evals you've already written so you don't lose work."

This response is rehearsed in every Maya sales call. It's also publicly documented in the Q4 2025 blog post.

## Anti-Positioning

Never used in our copy or sales:
- "AI-powered observability" → meaningless
- "Best eval platform" → who decided
- "Powered by Claude" as primary → that's underneath, not the value
- "Save engineering time" → quantify (we say "cut regression-related incidents by N%")

## Messaging by Channel

- **Landing page hero**: "Catch AI agent regressions before your users do. Open-source CLI in 60 seconds." + live demo + 2 CTAs ("Try CLI" / "View docs")
- **X founder post template**: "[number] [time] [what shipped or hit]" — Maya's standard format
- **Sales call open**: Maya leads with "Want me to run Helmsman on your production agent right now? Takes 5 minutes." Then actually does it.

## Rung Diagnostic for Current Pipeline (May 2026)

| Account | Rung | Stalled? | Action |
|---|---|---|---|
| Vega Synth | 5 | yes — SOC 2 gate | Send pen-test + offer Aug delivery |
| Atlas Robotics | 4→5 expand | no | Schedule capability-resistance conversation Q3 |
| Glaze Studios | 3 | no | Ship Vercel AI SDK integration (in flight) |
| Quill AI | 2 | yes — needs benchmark | Build benchmark for *their specific use case*; 1-week sprint |
| (...) | | | |
