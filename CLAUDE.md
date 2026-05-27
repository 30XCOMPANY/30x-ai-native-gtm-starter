# 30x AI-Native GTM Starter

> A scaffold for AI-native go-to-market. Mirrors how a real GTM org actually works — strategy, content, pipeline, assets, ops — and gives Claude Code a place to live in each of them.

This file is the lobby. Skim in 2 minutes, then navigate to the folder you need.

---

## What this repo is

A **structural scaffold** for an AI-native company's GTM operation. Not opinions, not a manifesto — just the folders and entry points a serious GTM team needs, shaped for the fact that:

- Your product changes every week
- Your buyer is an engineer
- Your real competitor might be the next foundation model release

Fork it. Fill in the templates. Let Claude Code drive the repeatable work.

---

## How a real GTM org maps to this scaffold

| What you do | Where it lives | First file to open |
|---|---|---|
| Define who you are + who you sell to | [`strategy/`](./strategy) | [`strategy/positioning.md`](./strategy/positioning.md) |
| Find + qualify + pursue prospects | [`pipeline/`](./pipeline) | [`pipeline/README.md`](./pipeline/README.md) |
| Produce content + demand gen | [`content/`](./content) | [`content/README.md`](./content/README.md) |
| Build decks, one-pagers, brand assets | [`assets/`](./assets) | [`assets/design.md`](./assets/design.md) |
| Run repeatable Claude actions | [`skills/`](./skills) | each skill is self-describing |
| Decide what to do when X happens | [`workflows/`](./workflows) | by scenario |
| Respond to category-level crises | [`playbooks/`](./playbooks) | by event |
| Connect external data into Claude | [`sync/`](./sync) | [`sync/README.md`](./sync/README.md) |
| Where Claude saves work | [`outputs/`](./outputs) | date-prefixed files |

---

## How Claude should behave in this repo

1. **Always read `strategy/` before answering positioning, ICP, or competitor questions.** The user's truth lives there.
2. **Read the relevant folder's README before producing a deliverable** — each folder explains the rules of its domain.
3. **Write outputs to `outputs/YYYY-MM-DD-{slug}.md`.** Don't dump them into the user's chat — archive them.
4. **Respect the brand voice in `strategy/brand.md`.** No marketing adjectives. No emoji unless the brand allows.
5. **Cite sources for any factual claim** about market, competitor, or model release.
6. **Don't invent context** — if a strategy file is empty, ask the user to fill it before producing work.

---

## Quickstart

```bash
git clone https://github.com/30XCOMPANY/30x-ai-native-gtm-starter my-gtm
cd my-gtm
rm -rf examples/      # remove reference fills so Claude doesn't mix them in
claude
```

Then say:
```
run the setup skill on https://yourcompany.com
```

`skills/setup/` auto-populates `strategy/` from your public footprint, then asks the five questions that decide everything else.

---

## Look-before-you-fork

- [`examples/helmsman/`](./examples/helmsman) — fictional AI eval-infra startup, every file filled. Read this in 20 minutes to understand the workflow end-to-end.
- [`examples/our-flavor/`](./examples/our-flavor) — our own opinionated take on AI-native GTM (six constitutions, ten real death cases, twenty-two signal sources). Use as inspiration, not as gospel.

---

## What this repo is NOT

- **Not a playbook.** It doesn't tell you what to believe about GTM. It gives you the shape to hold whatever you decide.
- **Not a daily UI.** You won't sit in this repo all day. You'll open it when you need to do GTM work that Claude can help with.
- **Not opinionated software.** The folders are functional, not philosophical. Our specific opinions live in `examples/our-flavor/`.

---

## License + acknowledgments

MIT. Use, fork, ship. Attribution appreciated, not required.

Structurally inspired by [`gtm-starter-kit`](https://github.com/KarlRaf/gtm-starter-kit) by Maja Voje, Nico Druelle, Karl Rafidimanana (April 2026). They built the pattern. This repo adapts the pattern for AI-native and adds the asset / content / sales-execution layers a real GTM org needs.
