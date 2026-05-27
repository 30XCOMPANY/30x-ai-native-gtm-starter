# Helmsman · Company Profile

## Quick identity

- **Company name**: Helmsman
- **One-line description**: Continuous evaluation and reliability monitoring for production AI agents.
- **URL**: https://helmsman.ai *(fictional)*
- **Founded**: 2024-10 by Maya Cheng (CEO) + Daniel Park (CTO)
- **Headcount**: 14 (May 2026)
- **Funding stage**: Series A
- **Total raised**: $14.5M (Seed $2.5M, Series A $12M)
- **Headquarters**: San Francisco

## What we ship

- **Primary product**: Helmsman Cloud — managed agent-eval-as-a-service. Hooks into your production agent via OpenTelemetry trace export; runs continuous LLM-as-judge + custom-scorer evals; alerts on regression; recommends prompt / model swaps.
- **Built on top of**: OpenTelemetry standard, Claude (as eval judge default), customer-bring-your-own-model option
- **Open-source components**:
  - `helmsman-cli` — eval runner CLI, MIT license, 4.2k stars
  - `helmsman-mcp` — MCP server exposing eval results to agents, MIT license, 1.1k stars
- **Deployment shapes available**: Cloud SaaS (default), VPC (Enterprise tier), on-prem (Enterprise tier, longer onboarding)

## Who we sell to

> See `icp-definition.md` for full ICP. Summary below.

- **Primary persona**: AI Platform Engineer at Series A-C AI-native startups (10-100 engineers, $5k-50k/mo LLM spend, running agents in production)
- **Secondary persona**: VP Engineering at AI-feature-heavy mid-market SaaS (where AI is becoming load-bearing)
- **Anti-persona**: Pre-PMF AI startups still iterating on prompt; non-AI-native companies "exploring" AI; agency / consultancies
- **Reference customers** (public-listed, fictional): Lovable (OSS users), Modal (Cloud), three undisclosed Series B AI infra companies

## Strategic origin story

Maya led Anthropic's internal eval tooling 2022-2024. She watched every customer (including Cursor, Vercel, Notion) build their own eval pipeline because off-the-shelf was either too generic (LangSmith) or too research-y (HumanEval, MMLU). Daniel saw the same pattern at Stripe — every payment infra team built reliability monitoring because the off-the-shelf APM tools didn't understand financial state machines.

The thesis: **AI agents are state machines whose failure modes are non-deterministic, and observability of those failures is a 2026 must-have, not a 2028 nice-to-have.** Window: 18-24 months before Anthropic / OpenAI ship "good enough" native evals that commoditize the dev-time use case — but the production reliability use case (multi-model, multi-customer, with remediation) is defensible longer.

## Current strategic phase

- [x] Early PMF — initial 40 paying customers love the product; scaling acquisition hypothesis
- [ ] Pre-PMF
- [ ] Scaling
- [ ] Defending / expanding

## Constraints to be aware of

- **Compliance constraints**: SOC 2 Type II in progress (target 2026-Q3). HIPAA + FedRAMP not yet — disqualifies healthcare + defense buyers until 2027.
- **Industry restrictions**: We don't sell to law firms (Harvey owns that; we're not differentiated there).
- **Brand stance**: We don't publicly compare ourselves to Anthropic's tools. Maya is ex-Anthropic; we maintain warm relationship.
- **Founder-led content stance**: Maya posts weekly on X (@mayacheng_ai). Daniel posts technical deep-dives on the company blog monthly.

## What we are NOT

- We are not a prompt-management tool (no prompt versioning / playground feature). Use Humanloop / Braintrust for that.
- We are not LangSmith. LangSmith is dev-time tracing tied to LangChain. We are production-time reliability monitoring, framework-agnostic.
- We are not RPA / agentic automation. We don't run agents; we evaluate agents others run.
- We do not offer model fine-tuning or training infrastructure.

## Team for GTM purposes

- **Technical sales calls**: Maya (CEO, up to 5 calls/week), Daniel (CTO, technical deep dives only, max 2/week)
- **Compliance / security review**: Daniel + outside counsel (Gunderson)
- **Content engine owner**: Maya for content strategy + posts; Yvonne (DevRel hire 2026-03) executes weekly content calendar
- **Inbound handling**: maya@helmsman.ai initially; routes to Yvonne for low-priority items
