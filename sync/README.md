# sync/ · Live Data Connectors

> This folder is where external data flows *into* the repo. The signal library, ICP scoring, drift audit, and OSS pipeline tracking all depend on data appearing here on a schedule.
>
> **Design principle**: MCP-first. Where an MCP server exists for a data source, prefer it. Fall back to scripts only when MCP doesn't cover the API.

---

## Why MCP-first?

Maja's `gtm-starter-kit` uses Python scripts for sync. That works, but in 2026 the better pattern is MCP servers:

1. **Composable** — any MCP-compatible client (Claude Code, Cursor, Cline, ChatGPT, Gemini) can use the same servers
2. **Maintained** — most providers now ship official MCP servers; less code for us to maintain
3. **Auditable** — every tool invocation is logged in the MCP protocol layer
4. **Constitution-aligned** — this is Constitution #6 applied to ourselves

Use scripts only for sources where MCP doesn't yet exist (some scraping cases, custom APIs).

---

## Architecture

```
External Source → MCP Server (or script) → /sync/cache/ → Skills read from cache
```

- **MCP servers** run as background processes or on-demand
- **Scripts** run on cron (see `schedule.md`)
- **Cache** holds the most recent pull with a timestamp
- **Skills** read from cache, not from live sources — keeps skills fast and offline-able

---

## What needs syncing

Mapped from `context/signal-library.md`:

| Source | Mechanism | Used by | Frequency |
|---|---|---|---|
| GitHub API (stars, issues, repos) | [official MCP](https://github.com/github/github-mcp-server) | signal-library A1-A4, oss-pipeline-track | daily |
| HuggingFace Hub | community MCP or HTTP fetch | signal-library B1-B2 | daily |
| OpenRouter rankings | scrape (no MCP) | signal-library B3 | daily |
| Foundation-model release RSS | HTTP fetch | signal-library B4 | hourly |
| Anthropic Skills / MCP registry | scrape (no MCP) | signal-library B6 | weekly |
| Replicate / Modal public deploys | API calls (no MCP) | signal-library C1 | weekly |
| Provider pricing diffs | HTTP fetch + diff | signal-library C3 | daily |
| HN Algolia | HTTP fetch (no auth) | signal-library D1 | hourly |
| Product Hunt GraphQL | official API + token | signal-library D2 | daily |
| Reddit OAuth | official API | signal-library D3 | daily |
| arXiv | HTTP fetch (no auth) | signal-library D4 | daily |
| X (Twitter) | paid X API or scraper | signal-library D7 | hourly |
| Slack (post outputs) | [official MCP](https://github.com/slack/slack-mcp-server) | output delivery | event |
| CRM (Attio / Salesforce / HubSpot) | official MCP (varies) | icp-scoring writes | daily |

---

## What's in this folder

- `README.md` (this file) — architecture overview
- `mcp-servers.md` — detailed MCP server configurations with tool mapping
- `scripts/` — fallback Python / TypeScript scripts for sources without MCP
- `cache/` — local cache directory, gitignored
- `.env.example` — required credentials template
- `schedule.md` — what runs when

---

## Quickstart

1. Copy `.env.example` to `.env` and fill in credentials
2. Configure your Claude Code with the MCP servers (see `mcp-servers.md`)
3. Run `scripts/init.sh` to populate initial cache
4. Configure schedule via cron / GitHub Actions / Modal scheduled functions (your choice)

## Security

- **Never commit secrets**. Every credential goes in `.env`, which is gitignored.
- **Use scoped tokens**. Read-only when possible.
- **Audit MCP server permissions**. Some MCP servers request more access than needed; review before installing.
- **Don't send customer / prospect PII to third-party LLMs** in this sync layer. Cache locally; let skills decide what to send.
