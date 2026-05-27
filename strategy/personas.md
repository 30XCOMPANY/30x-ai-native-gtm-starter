# context/personas/[name].md · Persona Template

> One file per buyer persona. Copy this template, fill in, save as e.g. `ai-infra-engineer.md`, `head-of-ai-product.md`, `cto-stage-3-icp.md`.
>
> AI-native personas look different from traditional B2B personas — the "demographic" sections matter less, the "what tools they live in" sections matter more.

---

## Identity

- **Persona name**: e.g., "Lead AI Engineer at Series A-C AI-native startup"
- **Common titles**: [list 3-5 actual job titles]
- **Where you find them**: [GitHub / X / Discord / specific subreddits / specific events / podcasts]
- **Tools they live in**: [VSCode + Cursor / Claude Code / Linear / Slack / Vercel / Modal / etc. — concrete]

---

## Their world (AI-native specific)

- **Tools currently used** (be specific):
  - LLM provider(s): [OpenAI / Anthropic / multi-model? which models?]
  - Inference infra: [self-host / Together / Fireworks / Modal / Replicate?]
  - Eval / observability: [LangSmith / Braintrust / Humanloop / home-grown / none?]
  - Coding assistant: [Cursor / Windsurf / Copilot / Cline / Claude Code?]
  - Orchestration: [LangChain / LlamaIndex / Vercel AI SDK / home-grown?]
- **LLM Maturity Stage** (from `icp-definition.md` 1.1): [stage]
- **Monthly LLM spend approximation**: [if known]
- **What they read**: [TLDR AI / Latent Space / specific newsletters / specific podcasts]
- **Who they follow on Twitter / X**: [specific list — Karpathy / Swyx / Simon Willison / Logan Kilpatrick / etc.]

---

## Success metrics they own

What this person is measured on internally. Determines what your pitch must address.

- [ ] LLM cost reduction
- [ ] Latency improvement
- [ ] Quality / accuracy of LLM outputs
- [ ] Time-to-ship for new AI features
- [ ] Compliance / data governance
- [ ] Other: [fill]

---

## Buying process

Critical for AI-native: most decisions are *bottom-up* (engineer evaluates, then evangelizes up).

- **Initial trigger**: how they discover new tools (HN / Twitter / colleague / Cursor extension / MCP server appearance / etc.)
- **Evaluation pattern**: [solo try → demo to team → champion to manager → procurement] or variant
- **Decision authority**:
  - [ ] Can sign up to $X individually
  - [ ] Team manager signs up to $Y
  - [ ] Department head / VP signs up to $Z
  - [ ] Procurement above $Z
- **Time to decision**: typical [days / weeks / months]
- **Top 3 objections** they raise:
  1.
  2.
  3.

---

## Attention triggers

What grabs their attention vs. what gets ignored.

**What works**:
- [ ] Specific code snippet that runs in <60 seconds (Rung 2 from `positioning.md`)
- [ ] Benchmark vs a tool they already use
- [ ] "Built by [former employer / known engineer]" credentials
- [ ] Open-source repo with recent commits
- [ ] Specific named-customer evidence in their vertical
- [ ] Direct DM from founder (works only at this persona's stage)

**What doesn't work** (waste of breath):
- [ ] Generic "AI-powered" / "transform your workflow" copy
- [ ] Whitepaper download gates
- [ ] Long video without code samples
- [ ] LinkedIn cold outreach (this persona ignores LinkedIn)
- [ ] Vendor-managed analyst report

---

## Outbound hooks (signal-tied)

For each signal in `signal-library.md` that applies to this persona, what does the outbound say?

```
### Signal: [A1 GitHub Stars Velocity]
Hook: "Saw {their_repo} jump 400 stars this week. We help teams in your shape handle the [evaluation / billing / observability] surge that follows. 15 min?"

### Signal: [B4 Foundation-Model Release Window]
Hook: "Claude 4.7 ships in 48h, your eval baselines need to re-run. We can ship that for you in one afternoon."

### Signal: [B6 MCP Server Publication]
Hook: "Saw your MCP server for {capability}. Curious how you're tracking agent-initiated vs human-initiated sessions. Coffee?"
```

---

## Anti-patterns for this persona

What gets you blocked / unsubscribed instantly:

- Multi-touch sequence with no new info each touch
- Forwarded "executive briefing" PDFs
- Requesting their calendar before showing them anything
- Generic "increase productivity" framing
- Asking them to fill out a form longer than 2 fields

---

## Reference: real examples of this persona

> Update monthly. Anonymize as needed.

- **Closed customer**: [pseudonym + their company stage]
- **Champion who didn't close**: [pseudonym + why didn't close]
- **Persona influencer**: [public person who exemplifies this persona — Karpathy, Swyx, etc.]

---

> **[PROTOCOL]**: When this persona's tools-they-live-in changes (e.g., they all switched from Cursor to Claude Code), also update `context/signal-library.md` — the signals you need to track might shift, and `skills/signal-to-content/` outbound templates need rewriting.
