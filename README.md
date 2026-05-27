# 30x AI-Native GTM Starter

> A scaffold for AI-native go-to-market. Mirrors how a real GTM org actually works — strategy, content, pipeline, assets, ops — and gives Claude Code a place to live in each of them.

[**🌐 Live preview**](https://30xcompany.github.io/30x-ai-native-gtm-starter/) · [**Examples**](./examples/) · [**MIT license**](./LICENSE)

---

## Why this exists

Generic GTM playbooks were built for B2B SaaS: quarterly product cycles, business buyers, seat-based pricing, stable competitor sets. **None of that holds for AI-native companies.** Foundation models reset the market every six months. Your buyer is an engineer. Your real competitor is the next Claude release.

Most "AI GTM starter" repos are either (a) thin templates with no working architecture or (b) opinionated playbooks dressed up as tools. This one is a true scaffold: empty templates organized like a real GTM org, with the AI-native dimensions added where they matter.

---

## Architecture

The repo mirrors how a working GTM team is organized — by function, not by topic.

```
30x-ai-native-gtm-starter/
│
├── CLAUDE.md             # The lobby. 2-min navigation.
├── README.md             # This file.
│
├── strategy/             # WHO we are. WHO we sell to. WHAT we believe.
│   └── positioning · icp · personas · pricing · brand
│   └── competitors · capability-radar
│
├── content/              # Demand gen
│   └── strategy · calendar · library · blog/ · social/
│
├── pipeline/             # Prospects + customers
│   └── playbook · signals · accounts · sequences/ · customers · objections
│
├── assets/               # Branded outputs
│   └── design.md (visual rules) · deck-style.md · decks/ · one-pagers/
│
├── skills/               # Repeatable Claude actions
│   └── setup · icp-scoring · technical-poc-brief · signal-to-content
│   └── deck-build · one-pager-build · outbound-sequence · objection-handle
│   └── signal-to-integration-pitch · weekly-drift-audit · oss-pipeline-track
│
├── workflows/            # Decision trees for humans
│   └── agent-native-distribution · oss-funnel · model-launch-response · integration-partner-outreach
│
├── playbooks/            # Emergency response
│   └── competitor-ships-equivalent · foundation-model-commoditizes-your-feature
│   └── viral-moment-traffic-surge · capability-obsolescence-emergency
│
├── sync/                 # MCP-first data connectors
│
├── outputs/              # Where Claude saves work
│
└── examples/
    ├── helmsman/         # Fictional AI infra company — fully filled
    └── our-flavor/       # Our specific opinions (six constitutions, ten death cases, twenty-two signal sources)
```

---

## Each folder has a clear entry point

| Folder | Open this first |
|---|---|
| `strategy/` | `strategy/positioning.md` |
| `content/` | `content/strategy.md` |
| `pipeline/` | `pipeline/playbook.md` |
| `assets/` | **`assets/design.md`** — the visual rules that bind every deck, one-pager, illustration |
| `skills/` | Each skill is self-describing — `setup/` is the bootstrap |
| `workflows/` | by scenario (model launch, partner outreach, etc.) |
| `playbooks/` | by event (competitor ships, viral moment, etc.) |
| `sync/` | `sync/README.md` |

---

## Quickstart

```bash
git clone https://github.com/30XCOMPANY/30x-ai-native-gtm-starter my-gtm
cd my-gtm
rm -rf examples/      # remove reference fills so Claude doesn't mix them in
claude
```

Then in Claude:
```
run the setup skill on https://yourcompany.com
```

`skills/setup` auto-populates `strategy/` from your public footprint, then asks five questions that decide everything else.

---

## What's AI-native about this scaffold (vs traditional GTM templates)

Five things added because the AI-native context demands them:

1. **`strategy/icp.md` has three new dimensions** — LLM Maturity Stage, Data Residency × Deployment, Model Spend Trajectory — not just industry/size/role.
2. **`strategy/capability-radar.md`** — separate from competitor radar. Tracks foundation-model releases that could commoditize your wedge. Has 8 early-warning signals.
3. **`pipeline/signals.md`** — 22 AI-native signal sources (GitHub stars velocity, OpenRouter rankings, MCP server publications) — not the SaaS standard (funding, hiring).
4. **`skills/signal-to-integration-pitch`** — integration-led growth is first-class. Vercel, Cursor, Anthropic Skills are distribution channels.
5. **`playbooks/foundation-model-commoditizes-your-feature.md`** — what to do when GPT-N+1 absorbs your category. Most teams have no plan; this gives them one.

See [`examples/our-flavor/research/`](./examples/our-flavor/research/) for the empirical evidence (ten real death cases, twelve company GTM teardowns, signal taxonomy).

---

## Use it three ways

| Posture | For | Time to value |
|---|---|---|
| **As a scaffold** | Your own AI company's GTM ops | 30-min setup + ongoing |
| **As a content quarry** | Use our `examples/our-flavor/research/` as raw material for your own writing | Immediate |
| **As a teaching tool** | Refer clients / mentees here when explaining AI-native GTM | Immediate |

---

## Acknowledgments

- **Maja Voje, Nico Druelle, Karl Rafidimanana** — [`gtm-starter-kit`](https://github.com/KarlRaf/gtm-starter-kit) (April 2026). Structural inspiration. They built the pattern for traditional B2B SaaS GTM. This repo adapts it for AI-native and adds the content / asset / sales-execution layers a real GTM org needs.
- **Kyle Poyar (Growth Unhinged)** — popularized the Claude Skill pattern for GTM analysis.
- **Anthropic** — for MCP, Agent Skills, and the protocol layer that makes agent-native distribution real.

## License

MIT. Use, fork, ship. Attribution appreciated, not required.

---

> Part of the [30x](https://github.com/30XCOMPANY) family of open GTM tooling.
