# sync/schedule.md · What Runs When

> Reference for scheduling the sync jobs. Use cron, GitHub Actions, Modal scheduled functions, Cloudflare Workers cron, or whatever fits your stack. The pattern matters more than the runtime.

---

## Recommended schedule

```
# Hourly (high-velocity signals)
0 * * * *    pull-hn-stories
0 * * * *    pull-foundation-model-rss
30 * * * *   pull-x-mentions  (if X API budget allows)

# Daily, morning
0 8 * * *    github-mcp::pull-stars-velocity
0 8 * * *    huggingface-mcp::pull-trending
30 8 * * *   scrape-openrouter-rankings
0 9 * * *    diff-pricing-pages
0 10 * * *   pull-reddit-mentions
0 11 * * *   pull-arxiv-papers
0 12 * * *   pull-product-hunt-top

# Daily, evening
0 18 * * *   icp-scoring::nightly-refresh
0 19 * * *   crm-sync::push-outputs

# Weekly, Monday morning
0 7 * * 1    skill::weekly-drift-audit
0 7 * * 1    pull-replicate-models
0 7 * * 1    pull-modal-examples
0 7 * * 1    scrape-anthropic-skills-directory
0 7 * * 1    scrape-mcp-server-registry

# Weekly, Friday morning (signal performance audit)
0 7 * * 5    signal-library::performance-audit

# On-event triggers (not scheduled)
- New foundation-model release detected → trigger model-launch-response workflow
- HN frontpage AI story >300pts → trigger viral-moment alert
- Customer Slack channel mention of capability obsolescence → manual review
```

---

## Time-zone note

Times above are UTC unless specified. For US-team-friendly:
- Daily morning batch: 8am PT = 16:00 UTC
- Weekly Monday batch: 7am PT Monday = 15:00 UTC Monday

---

## What each cycle produces

### Hourly cycles
- `sync/cache/hn-stories/YYYY-MM-DD-HH.json`
- `sync/cache/foundation-model-rss/YYYY-MM-DD-HH.json`
- `sync/cache/x-mentions/YYYY-MM-DD-HH.json`

### Daily cycles
- `sync/cache/github-stars/YYYY-MM-DD.json`
- `sync/cache/hf-trending/YYYY-MM-DD.json`
- `sync/cache/openrouter-rankings/YYYY-MM-DD.json`
- `sync/cache/pricing-diffs/YYYY-MM-DD.json`
- `sync/cache/reddit-mentions/YYYY-MM-DD.json`
- `sync/cache/arxiv-papers/YYYY-MM-DD.json`
- `sync/cache/product-hunt/YYYY-MM-DD.json`

### Weekly cycles
- `outputs/YYYY-MM-DD-drift-audit.md` (from weekly-drift-audit skill)
- `sync/cache/replicate-models/YYYY-WW.json`
- `sync/cache/modal-examples/YYYY-WW.json`
- `sync/cache/anthropic-skills/YYYY-WW.json`
- `sync/cache/mcp-server-registry/YYYY-WW.json`

---

## Failure handling

When a sync job fails:
1. Retry with exponential backoff (3 attempts)
2. On final failure, write `sync/cache/{source}/error-YYYY-MM-DD-HH.json`
3. Notify configured channel (Slack by default)
4. `weekly-drift-audit` includes a Failed Syncs section

### Common failures
- **GitHub rate limit** → use authenticated token with higher limits
- **X API quota exhausted** → fall back to Nitter scraping or skip until next month
- **Scraping target changed HTML structure** → update parser; this is the most common failure mode

---

## Cost estimation

For Helmsman-sized usage (sample company), monthly sync costs:

| Source | Cost |
|---|---|
| GitHub API | free |
| OpenRouter scraping | free (your own compute) |
| Anthropic / OpenAI / Google blogs (RSS) | free |
| HN Algolia | free |
| Reddit | free |
| arXiv | free |
| Product Hunt | free |
| X Basic API | $100 / month |
| HuggingFace | free |
| Provider pricing diffs | free |
| Replicate / Modal API | free |
| **Subtotal** | **~$100 / month** |

Add: cloud cost for cron runners (~$5/month on Modal or Cloudflare Workers).

**Total sync cost: ~$105 / month for a 1-2 person GTM team using this repo.**

For comparison: a Clay account starts at $349/month.
