# Workflow · Agent-Native Distribution

> Implements Constitution #6 (Agent-Native Distribution). For humans — decision tree for shipping into Claude / ChatGPT / Cursor / Gemini agent ecosystems.
>
> Evidence: see `research/02-gtm-motions-by-company.md` Insight 3.

---

## Why this matters in 2026

By H2 2025, 10,000+ public MCP servers shipped. ChatGPT, Cursor, Gemini, Copilot all integrate. Anthropic's Agent Skills directory includes Atlassian, Canva, Cloudflare, Figma, Notion, Ramp, Sentry — these are now the "platforms" your future customers discover products through.

**If you don't have an MCP server / Agent Skill / OpenAI Apps SDK integration in 2026, you're invisible to the fastest-growing distribution channel.**

This workflow is how to not be invisible.

---

## Step 1 · Identify your "agent-callable surface"

Not every product can or should be agent-callable. Diagnose first.

**Strong agent-callable candidates**:
- Read-only data services (search, retrieve, summarize)
- Tightly-scoped writes (create-a-doc, send-a-message, schedule-a-meeting)
- Discrete computations (evaluate, classify, transform)
- Multi-step workflows with clear input/output (run-this-pipeline)

**Weak candidates**:
- Heavy UI products (full applications, dashboards)
- Long-running ambiguous workflows
- Products where the *interface* is the value (creative tools)

**Decision**: which 1-3 product capabilities have the clearest *single-call* shape?

---

## Step 2 · Pick your initial surfaces (don't do all at once)

In priority order, depending on your ICP:

| Surface | When to ship first | Effort |
|---|---|---|
| **Anthropic MCP server** | If your ICP uses Claude / Cursor / Claude Code | 1-2 days for a basic server, 1-2 weeks for production |
| **Anthropic Agent Skill** (anthropic/skills repo) | If your product helps with a specific task Claude users do | 2-4 hours; piggybacks on existing MCP or API |
| **Cursor extension** | If your ICP includes coding-tool users | 1 week |
| **OpenAI Apps SDK** | If your ICP overlaps ChatGPT enterprise | 2-3 weeks |
| **Vercel AI SDK partner integration** | If your ICP uses Vercel / Next.js | 1-2 weeks |
| **n8n / Zapier integration** | If your ICP includes non-AI-native automation users | 1-2 weeks |

**Recommended sequence for most AI-native B2B**: MCP server → Skills directory → Cursor extension → Vercel AI SDK.

---

## Step 3 · Ship the MCP server first

It's the lowest-cost, highest-leverage surface.

**Minimum-viable MCP server**:
- 2-5 tools that map to your most-called API endpoints
- Clear tool descriptions (the LLM reads these to decide when to invoke)
- Authentication via the client's API key (not your service's)
- Open-source the server code (Cline-style trust narrative)
- Listed on `modelcontextprotocol.io/servers` and `anthropic/skills` repo

**Anti-patterns**:
- Trying to expose your entire API. Pick the 3-5 most-called methods.
- Requiring users to write their own API key into config. Provide OAuth or token-flow.
- Closed-source server code. Defeats the trust win.

**Reference example** (Helmsman's `helmsman-mcp`):
```
Tools exposed:
- get_eval_status(agent_id, baseline) — return regression score
- list_recent_traces(agent_id, since) — list traces with eval scores
- compare_baselines(agent_id, baseline_a, baseline_b) — diff two baselines

Each tool description includes:
- 1 sentence what it does
- Example invocation
- Returns shape (typed)
```

---

## Step 4 · Make discoverable

Shipping the server is necessary but not sufficient. Distribution layer:

1. **Listings**:
   - [`anthropic/skills`](https://github.com/anthropics/skills) PR
   - [`modelcontextprotocol.io/servers`](https://modelcontextprotocol.io/servers) submission
   - [Cline marketplace](https://docs.cline.bot/mcp-servers) listing
   - [smithery.ai](https://smithery.ai) listing
   - Cursor MCP directory submission

2. **Landing page changes**:
   - "Use in Claude / Cursor / ChatGPT" CTA above the fold — same prominence as "Sign up"
   - Quickstart that includes the MCP install command alongside the SDK install
   - Demo video showing your product invoked from inside Claude / Cursor

3. **Content**:
   - Blog post: "How to use [your product] inside Claude Code"
   - X post from founder with screen-recording of agent invoking your tool
   - Reach out to Hamel Husain / Swyx / Simon Willison if your MCP server is genuinely interesting

---

## Step 5 · Measure differently

Agent-initiated sessions behave differently from human-initiated. Track them separately.

**Metrics to track**:
- **Agent-initiated session count** (weekly, by source — Claude / Cursor / ChatGPT / Other)
- **Agent → human conversion** — did the user later log into your direct product?
- **Retention** by acquisition channel — agent-acquired users retain differently
- **NPS** — agent-acquired users sometimes have lower satisfaction (they're "using" you without knowing your brand)

**Anti-pattern**: lumping agent + human sessions in one funnel. They have different shape and value.

---

## Step 6 · Iterate

Monthly review:
- Which tools in your MCP server got invoked most? Add more depth there.
- Which tools never got invoked? Either delete or fix the description.
- What did agents *try* to invoke that doesn't exist? That's your roadmap.
- Are users dropping from agent → website? That's a brand opportunity.

---

## When this workflow does NOT apply

- Pre-PMF products: ship to humans first, then ship to agents.
- Hardware / heavy-UI products: agent-callable layer may be minimal; focus on traditional integrations.
- Regulated industries (healthcare, defense): wait until compliance allows external agent access to your data.

For everyone else: **start the MCP server this quarter**. The compounding distribution effect starts after ~3 months of being in the ecosystem.
