# content/ · Demand gen through content

> Where blog posts, X threads, LinkedIn posts, and podcast prep get drafted, archived, and tracked.

## Files in this folder

| File / folder | What it is | Cadence |
|---|---|---|
| [`strategy.md`](./strategy.md) | What we publish, where, how often, why | Quarterly |
| [`calendar.md`](./calendar.md) | What's planned for the next 4–8 weeks | Weekly |
| [`library.md`](./library.md) | Everything we've published, with metrics | Append-only |
| [`blog/`](./blog/) | Long-form drafts (one .md per post) | As written |
| [`social/`](./social/) | X threads, LinkedIn posts, 小红书 posts | As written |

## How Claude helps here

| What you need | Skill to run |
|---|---|
| Turn a signal (release, milestone, KOL mention) → X thread | `skills/signal-to-content` |
| Turn a research insight → blog post draft | `skills/signal-to-content` (mode: blog) |
| Repurpose a blog post into a thread + LinkedIn + 小红书 | `skills/signal-to-content` (mode: repurpose) |

## Workflow

1. Check `pipeline/signals.md` for what fired this week
2. Pick one signal → spawn one piece of content via `skills/signal-to-content`
3. Save draft to `content/blog/YYYY-MM-DD-{slug}.md` or `content/social/YYYY-MM-DD-{slug}.md`
4. Polish, ship, log in `library.md`

## Anti-patterns

- Don't publish without a signal anchor. "Generic thought leadership" = no read.
- Don't auto-post from drafts. Human reads + ships.
- Don't repurpose mechanically. Each platform's voice is different (see `strategy/brand.md`).

---

> **[PROTOCOL]**: Brand voice in `strategy/brand.md` is binding. Skills that produce copy must obey it.
