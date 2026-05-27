# 30x AI-Native GTM Starter

> The Claude Code repo for go-to-market when your product changes weekly, your buyer is an engineer, and your next competitor might be the next model release.

---

## Why this exists

Generic GTM playbooks were built for B2B SaaS:
- Quarterly product cycles
- Business buyers
- LinkedIn outbound
- Seat-based pricing
- Competitors who don't ship 10x improvements overnight

**None of that holds for AI-native companies.** Foundation models reshuffle the market every 4-6 months. Your moats can evaporate in a single DevDay. Your buyers won't read your whitepaper but will read your GitHub commit graph.

This repo is the GTM operating system rebuilt around that reality. Clone it. Fill in `context/` once. Run GTM tasks from a single prompt in Claude Code.

---

## What you get

```
30x-ai-native-gtm-starter/
├── CLAUDE.md                       · 2-min lobby + Six Constitutions
├── research/                       · 950 lines of empirical evidence
│   ├── 01-capability-obsolescence-and-icp.md    · 10 real death cases
│   ├── 02-gtm-motions-by-company.md             · 12 company teardowns
│   └── 03-signals-and-pricing.md                · 22 signal sources + 12 pricing decodes
├── context/                        · institutional knowledge that grows weekly
│   ├── profile.md
│   ├── icp-definition.md           · Living ICP + 3 AI-native dimensions
│   ├── signal-library.md           · 22 AI-native signals + decay + combinations
│   ├── positioning.md              · Technical Credibility Ladder (5 rungs)
│   ├── competitor-radar.md         · Two-layer radar + 5 death patterns
│   └── personas/template.md
├── skills/                         · 7 SKILL.md repeatable actions
│   ├── setup
│   ├── technical-poc-brief
│   ├── signal-to-content
│   ├── signal-to-integration-pitch
│   ├── icp-scoring
│   ├── weekly-drift-audit
│   └── oss-pipeline-track
├── workflows/                      · decision trees for humans
│   ├── oss-funnel.md
│   ├── agent-native-distribution.md
│   ├── model-launch-response.md
│   └── integration-partner-outreach.md
├── playbooks/                      · emergency response scripts
│   ├── competitor-ships-equivalent.md
│   ├── foundation-model-commoditizes-your-feature.md
│   ├── viral-moment-traffic-surge.md
│   └── capability-obsolescence-emergency.md
├── sync/                           · MCP-first live data connectors
├── outputs/                        · every produced artifact, archived
└── examples/sample-company/        · Helmsman: a fully-filled fictional AI company
```

---

## The Six Constitutions

Every file in this repo derives from one of these six mental models. Every one is backed by empirical evidence in `research/` — none of this is a hot take.

1. **Living ICP** — your ICP drifts because foundation models drift. Weekly revision with evolution log.
2. **Technical Credibility Ladder** — replace value pillars with 5 rungs of proof a technical buyer can verify in 5 minutes.
3. **Community → Customer Funnel** — GitHub star → Discord active → trial → paid → enterprise. Measurable.
4. **Capability Obsolescence Radar** — your real competitor isn't Notion, it's GPT-6.
5. **Integration-Led Growth** — marketing doesn't compound, integrations do. Every platform you ship into is a new growth curve.
6. **Agent-Native Distribution** — 2026's must-do. If your product isn't callable by Claude / ChatGPT / Cursor agents, you're invisible to the fastest-growing distribution channel.

Full details in [CLAUDE.md](./CLAUDE.md).

---

## Quickstart

```bash
git clone https://github.com/[your-org]/30x-ai-native-gtm-starter my-gtm
cd my-gtm
claude
# then: "run the setup skill on https://yourcompany.com"
```

Claude reads `CLAUDE.md`, runs `skills/setup`, and populates `context/` from your public footprint. Refine over coffee. Ship outbound by lunch.

**To explore before forking**: read `examples/sample-company/` — a fictional AI infra company (Helmsman) with every file filled in. You'll understand the entire repo in 30 minutes.

---

## Why this exists in addition to [gtm-starter-kit](https://github.com/KarlRaf/gtm-starter-kit)

Maja Voje, Nico Druelle, and Karl Rafidimanana shipped `gtm-starter-kit` in April 2026. It's the pattern this repo structurally inherits — `CLAUDE.md` lobby, `context/` institutional knowledge, `skills/` repeatable actions, `workflows/` for humans.

But `gtm-starter-kit` assumes traditional B2B SaaS:
- Static ICP refreshed quarterly
- Sales-led primary motion
- Generic competitor battlecards
- 2 Python scripts as the sync layer
- No notion of capability obsolescence or agent-callable distribution

For an AI-native company, those defaults break. **This repo rebuilds the philosophy for AI-native** while keeping the same directory pattern so the two are compatible for anyone who's used Maja's.

If you're a traditional B2B SaaS company, **use Maja's kit**. If you're AI-native, use this one.

---

## What "AI-native" means here

You qualify if 2+ of these are true:
- Product capability depends on a foundation model (OpenAI / Anthropic / Google / open) as a load-bearing component
- Your competitive moat could shift with a foundation-model release
- Your buyers include engineers or AI-curious PMs (not just business decision-makers)
- Your primary GTM motion is some flavor of PLG / community / open source / integration (not sales-led)
- Your pricing isn't pure per-seat (uses tokens, credits, GPU-hours, or hybrid)

If you check none of those, you're not AI-native; use a traditional GTM kit.

---

## How to use this repo

### Daily / weekly cadence

| Frequency | What | Time |
|---|---|---|
| Daily | Check signal alerts (skills run on schedule via sync/) | 5 min |
| Weekly | `weekly-drift-audit` skill | 15 min |
| Weekly | Update CLAUDE.md Current Priorities | 5 min |
| Weekly | Score new outbound batch (`icp-scoring`) | 30 min |
| Monthly | Refresh `signal-library.md` performance audit | 30 min |
| Quarterly | Full ICP revisit with evolution log entry | 1 hour |

**Total operating cost**: ~3-5 hours / week for a 1-2 person GTM team. Worth it once it compounds.

### Constitution-locked work

Every claim in this repo traces to one of the six constitutions. If you're contributing a new file, skill, or workflow, **state which constitution it serves**. If it serves none, it doesn't belong here.

### Don't run before you fill out `context/`

`skills/` are useless without filled-in `context/`. The `setup` skill helps with auto-fill, but you must still answer the 5 questions it asks. Skipping these = the rest of the repo doesn't work.

---

## Acknowledgments

- **Maja Voje, Nico Druelle, Karl Rafidimanana** — [`gtm-starter-kit`](https://github.com/KarlRaf/gtm-starter-kit) (April 2026). Structural inspiration. We follow your directory pattern; we rebuild the philosophy for AI-native.
- **Kyle Poyar (Growth Unhinged)** — popularized the Claude Skill pattern for GTM.
- **Anthropic** — for MCP, Agent Skills, and the broader agentic-protocol ecosystem that makes Constitution #6 viable.
- **Every founder whose case study appears in `research/`** — Anton (Lovable), Eric Simons (Bolt), Aman Sanger (Cursor), Maya Cheng *(fictional, ex-Anthropic)*, and the real people behind the real death cases (Jasper, Inflection, Adept, Character, Stability, Humane). Your wins and losses are the empirical base of this work.

## Contributing

Issues and PRs welcome at [your-repo-url]. Particularly looking for:
- New death-case entries for `research/01-capability-obsolescence-and-icp.md` (this list will grow with each model release)
- New signal sources for `context/signal-library.md` as the AI ecosystem evolves
- Sample-company variations for verticals not yet covered (Helmsman covers agent eval; we'd love samples for AI coding, AI search, AI voice, AI hardware, etc.)
- MCP server implementations for the sources in `sync/mcp-servers.md` that don't yet have one

When contributing:
- Trace every claim to evidence (cite a URL when possible)
- Trace every change to one of the six constitutions
- Update the `[PROTOCOL]` block in any file you touch

## License

MIT. See [LICENSE](./LICENSE). Use, fork, ship. Attribution appreciated, not required.

---

> Built by [your name]. Maintained as part of the [30x](https://github.com/[your-org]/30x) family of GTM tooling.
