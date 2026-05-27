# Helmsman · Sample Company

> Fictional AI-native company used to demonstrate this repo end-to-end. Every file under `examples/sample-company/` is filled with realistic-but-invented data.
>
> When you fork this repo, **delete `examples/sample-company/` after reading it**, or keep it as a reference. Don't accidentally treat Helmsman as real.

---

## What Helmsman is (fictional)

Agent reliability platform. Runs continuous evaluations on production AI agents (your Cursor agent, customer-support agent, coding agent). Catches regressions before they hit users. Recommends fixes.

Founded 2024-Q4 by Maya Cheng (ex-Anthropic eval lead) and Daniel Park (ex-Stripe platform infra). Series A closed 2026-02 at $12M led by a16z, with Vercel as strategic.

14 people. SF HQ.

## Product shape
- Open source: `helmsman-cli` (eval runner, 4.2k stars), `helmsman-mcp` (MCP server exposing eval results to agents, 1.1k stars)
- Paid: Helmsman Cloud (managed dashboard, drift alerts, integrated remediation)
- Optional: Helmsman Enterprise (VPC, SSO, dedicated CSM)

## Pricing
- Free: CLI + BYOK evaluation
- Starter: $99/mo (1 project, 100k traces/mo)
- Team: $499/mo (5 projects, 1M traces + $0.40/1k overage)
- Enterprise: custom (typical $50K-150K ACV, includes VPC + SSO + 10M+ trace volume)

## Current strategic phase
Early PMF. Repeatable acquisition through OSS funnel; testing Enterprise upsell pattern.

## Current priorities (2026-05-26)
- [ ] Ship Cursor extension by June 15 (Constitution #5, #6)
- [ ] Re-score top 50 accounts after Claude 4.7 release evaluations (Constitution #1)
- [ ] Track Anthropic's roadmap on native Claude eval — capability obsolescence watch (Constitution #4)
- [ ] Convert 5 OSS-engaged users to Starter this month (Constitution #3)

## How Claude should behave in this Helmsman instance

Same five behaviors as parent `CLAUDE.md`. Two Helmsman-specific notes:

1. **When asked about Helmsman positioning, lead with the technical proof artifact** (the `helmsman-cli` repo with its 4.2k stars + reproducible eval-trace examples). Do not lead with marketing copy.

2. **When asked about competitive positioning vs Braintrust / Langfuse / LangSmith**, refer to `context/competitor-radar.md` Section 1 — those are the three direct competitors, and there's specific honest assessment for each.
