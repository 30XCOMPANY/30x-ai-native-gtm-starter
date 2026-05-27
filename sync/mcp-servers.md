# sync/mcp-servers.md · MCP Server Configurations

> Specific MCP servers to configure for this repo. Each has its purpose, install instructions, and tool mapping to our signal library.

---

## Official / first-party MCP servers

### 1 · GitHub MCP Server
- **Provider**: GitHub (official)
- **Repo**: [github/github-mcp-server](https://github.com/github/github-mcp-server)
- **Powers signals**: A1 (stars velocity), A2 (new-org repos), A3 (issues/PRs), A4 (dependents), A5 (npm/pip via repo deps)
- **Powers skill**: `oss-pipeline-track` (Aware → Active stage data)
- **Install** (Claude Code):
  ```json
  {
    "mcpServers": {
      "github": {
        "command": "github-mcp-server",
        "args": ["--read-only"],
        "env": {
          "GITHUB_TOKEN": "${env:GITHUB_TOKEN}"
        }
      }
    }
  }
  ```
- **Required scopes**: `public_repo`, `read:org`, `read:user`
- **Rate limits**: 5000 req/hour with auth

### 2 · Slack MCP Server
- **Provider**: community (official forthcoming)
- **Powers**: notification delivery from skills (drift audit, signal alerts)
- **Use case in this repo**: post `outputs/*.md` summaries to a designated Slack channel

### 3 · Linear MCP Server
- **Provider**: Linear (official)
- **Powers**: tracking GTM-related work
- **Use case**: convert `outputs/*.md` recommendations into Linear tasks

### 4 · Notion MCP Server
- **Provider**: Notion (official)
- **Powers**: optional duplication of `context/` content to Notion for non-technical team members
- **Use case**: Maya's content team has Notion; Daniel's eng has the repo. MCP bridges.

### 5 · Sentry MCP Server
- **Provider**: Sentry (official)
- **Use case**: optional — if your product feeds Sentry, error-rate spikes can be a Helmsman-internal signal of customer-facing reliability events

---

## CRM MCP servers (pick one)

### Attio MCP
- **Provider**: Attio (official)
- **Powers**: write outputs of `icp-scoring` directly into Attio pipeline
- **Configuration**: `ATTIO_API_KEY` in env

### HubSpot MCP
- **Provider**: community + HubSpot official forthcoming
- **Use case**: same as Attio for HubSpot users

### Salesforce MCP
- **Provider**: Salesforce (official, beta)
- **Use case**: Enterprise tier customers; heavier but necessary

---

## Inference / data MCP servers

### HuggingFace MCP (community)
- **Provider**: community
- **Powers**: signals B1 (trending models), B2 (Spaces)
- **Fallback**: HF Hub API HTTP fetch

### Anthropic Claude / OpenAI / Google AI
- **Use as judge in eval-related skills** (not for sync, but listed here for completeness)

---

## Sources without MCP (use scripts)

| Source | Script (in `scripts/`) | Schedule |
|---|---|---|
| OpenRouter rankings | `scrape_openrouter.py` | daily |
| Anthropic Skills directory | `scrape_skills_directory.py` | weekly |
| Replicate model listings | `pull_replicate_deploys.py` | weekly |
| Modal public templates | `scrape_modal_examples.py` | weekly |
| Provider pricing diffs | `diff_pricing_pages.py` | daily |
| HN Algolia | `pull_hn_stories.py` | hourly |
| Reddit r/LocalLLaMA | `pull_reddit_mentions.py` | daily |
| arXiv | `pull_arxiv_papers.py` | daily |
| X mentions | `pull_x_mentions.py` (requires X API or third-party) | hourly |

---

## Custom MCP server: your-product (recommended)

If your product has an API, **ship an MCP server for it too**. Two purposes:

1. Internal use — your team's Claude Code can invoke your product directly
2. External distribution — Constitution #6, see `workflows/agent-native-distribution.md`

Example for Helmsman (sample company):
```
helmsman-mcp:
  command: helmsman-mcp
  args: ["--api-key", "${HELMSMAN_API_KEY}"]
  tools:
    - get_eval_status
    - list_recent_traces
    - compare_baselines
    - get_drift_alerts
```

---

## Installation order

1. **First**: GitHub MCP — needed for most signals
2. **Second**: Your CRM MCP (Attio / HubSpot / Salesforce) — needed for icp-scoring outputs
3. **Third**: Slack MCP — for notification delivery
4. **Fourth**: Sources-without-MCP scripts (`sync/scripts/`)
5. **Optional**: Notion, Linear, Sentry per team preference

After installation, run `scripts/init.sh` to validate all connections.

---

## Schema for cached data

Each sync writes to `sync/cache/{source}/{YYYY-MM-DD}.json` in this shape:

```json
{
  "source": "github-stars-velocity",
  "fetched_at": "2026-05-27T08:00:00Z",
  "fetch_window": {
    "start": "2026-05-20T00:00:00Z",
    "end": "2026-05-27T00:00:00Z"
  },
  "data": [...],
  "errors": [],
  "next_fetch_after": "2026-05-28T08:00:00Z"
}
```

Skills read from these caches. They never call live APIs directly.

---

## Why MCP and not raw API

Three reasons:
1. **Standardization** — your team uses the same tool surface for OpenAI, Anthropic, GitHub, Slack, internal product. One mental model.
2. **Distribution** — your custom MCP server can be used by *anyone running an agent*. Free distribution channel.
3. **Future-proofing** — when Anthropic / OpenAI ship native integration with your category, your MCP server is already the agent-callable surface they connect to.

---

## Maintenance

Run `weekly-drift-audit` skill to flag stale syncs. Cache files older than their `next_fetch_after` get re-pulled or flagged.

If a source's MCP server gets deprecated:
1. Fall back to `scripts/` version
2. Open issue on the MCP repo (community maintained)
3. Document the workaround in this file
