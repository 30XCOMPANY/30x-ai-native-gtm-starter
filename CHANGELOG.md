# Changelog

All notable changes to `30x-ai-native-gtm-starter`.

This project follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] · 2026-05-27 · Scaffold-first refactor

### Why this release exists

v0 was an **opinionated content piece dressed as a tool**. The "Six Constitutions" framework was hard-coded at the root, the research files were the visible center, and forks inherited our specific worldview whether or not they shared it.

v1 commits to being a **scaffold**. The architecture is the IP. Our opinions live in `examples/our-flavor/` where forkers can take or leave them.

### Changed

- **Top-level folder structure** now maps to real GTM org functions:
  - `strategy/` — positioning, ICP, personas, pricing, brand, competitors, capability-radar
  - `content/` — demand gen (strategy, calendar, library, blog/, social/)
  - `pipeline/` — prospects + customers (playbook, signals, accounts, sequences/, customers, objections)
  - `assets/` — branded outputs anchored by `assets/design.md` (visual rules)
  - `skills/`, `workflows/`, `playbooks/`, `sync/` — unchanged in role; cross-refs updated
- **`CLAUDE.md`** rewritten as pure navigation lobby. No longer asserts "Six Constitutions" as canonical.
- **`README.md`** reflects new architecture; describes "Six Constitutions" only as one example flavor.
- **Helmsman sample company** restructured to mirror new scaffold (no longer uses old `context/` folder).
- **`pipeline/playbook.md`** adds AI-native caveat: the 7-stage funnel applies only to Enterprise lane; PLG motion lives in `workflows/oss-funnel.md`.
- All internal cross-references updated (no more broken paths after the move).

### Added

- **`assets/design.md`** — visual brand system (color, type, spacing, motion). Binding on every asset.
- **`assets/deck-style.md`** — PPTX template rules + 6 master slide types.
- **`strategy/brand.md`** — voice + vocabulary + what we don't say.
- **`strategy/pricing.md`** — pricing strategy template.
- **`strategy/capability-radar.md`** — foundation-model obsolescence watch (split from `competitors.md`).
- **`pipeline/playbook.md`** — 7-stage sales process with conversion targets.
- **`pipeline/accounts.md`** — live target account list template (T1/T2/T3).
- **`pipeline/objections.md`** — tested objection responses by archetype.
- **`pipeline/customers.md`** — active customer roster + expansion targets.
- **`content/strategy.md` + `calendar.md` + `library.md`** — full content engine.
- **New skills**:
  - `skills/deck-build/` — reads `assets/design.md` + `deck-style.md` + `strategy/` to produce a deck spec
  - `skills/one-pager-build/`
  - `skills/outbound-sequence/`
  - `skills/objection-handle/`
- **Worked examples** at folder-leaf level:
  - `content/blog/2026-05-27-why-jasper-died.md`
  - `content/social/2026-05-27-jasper-thread.md`
  - `pipeline/sequences/example-mcp-publisher-outreach.md`
  - `assets/decks/example-investor-pitch.md`

### Moved

| Old path | New path |
|---|---|
| `context/profile.md` | `strategy/about.md` |
| `context/positioning.md` | `strategy/positioning.md` |
| `context/icp-definition.md` | `strategy/icp.md` |
| `context/personas/template.md` | `strategy/personas.md` |
| `context/competitor-radar.md` | `strategy/competitors.md` (+ split `strategy/capability-radar.md`) |
| `context/signal-library.md` | `pipeline/signals.md` |
| `research/` | `examples/our-flavor/research/` |
| `examples/sample-company/` | `examples/helmsman/` |
| `examples/helmsman/context/` | `examples/helmsman/strategy/` (mirroring new scaffold) |

### Removed

- The old `context/` top-level folder.
- The framing of "Six Constitutions as canonical." (They're still documented in `examples/our-flavor/research/` as our opinion, not the scaffold's law.)

### Migration guide (for early forks of v0)

If you forked v0 (pre-2026-05-27):

```bash
# 1. Pull the latest main
git fetch origin && git checkout main && git rebase origin/main

# 2. Migrate your filled-in context to the new locations
git mv context/profile.md strategy/about.md
git mv context/icp-definition.md strategy/icp.md
git mv context/positioning.md strategy/positioning.md
git mv context/competitor-radar.md strategy/competitors.md
git mv context/signal-library.md pipeline/signals.md
git mv context/personas/template.md strategy/personas.md

# 3. Update any internal links in your filled files
grep -rln "context/" your-filled-files/
# replace each per the table above

# 4. Delete the now-empty context/ folder
rmdir context/
```

If you forked v0 in the last 14 days and don't have meaningful customization yet: easiest to re-fork from v1.

### Acknowledgments for v1

The scaffold-first thinking was prompted by direct user feedback from creators using the v0 fork. Specifically the question *"如果是脚手架就要有脚手架的觉悟"* — "If it's a scaffold, it needs scaffold-discipline." That insight reshaped the entire repo.

---

## [0.1.0] · 2026-05-26 · Initial release

### Added
- Initial CLAUDE.md, context/, skills/, workflows/, playbooks/, sync/
- research/ with 10 death cases + 12 company GTM teardowns + 22 signal sources
- examples/sample-company/ (Helmsman)
- Six Constitutions framework
- Live GitHub Pages landing at https://30xcompany.github.io/30x-ai-native-gtm-starter/

### Lessons learned in v0

- Mixing scaffold + opinion in one repo confuses both audiences
- "Six Constitutions" hard-coded in CLAUDE.md made the scaffold feel doctrinal
- Forkers said "I wouldn't use this myself" — the most useful feedback we got

These all flowed into v1.
