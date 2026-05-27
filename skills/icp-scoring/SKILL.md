---
name: icp-scoring
description: Score one account or a batch against the Living ICP. Uses both AI-native dimensions (Maturity, Data Residency, Spend Trajectory) and traditional filters. Outputs tier assignment + first-action recommendation per account.
---

# Skill · icp-scoring

## What this does

Given a list of accounts (domains), produces a tier-ranked output with disqualifier flags and per-account first-action. Different from traditional ICP scoring because the gates are AI-native (Maturity Stage, Data Residency, Spend Trajectory) — see `context/icp-definition.md` Section 6.

## How to invoke

```
score these accounts: [list of domains]
```

Or:

```
score the accounts in [outputs/file.md]
```

## Steps Claude takes

1. **Read** `context/icp-definition.md` Sections 1, 2, 3, 6 (qualifier framework + anti-ICP).

2. **For each account**, run gates in this order:

   **Gate 1 · Hard qualifiers** (any fail → disqualify):
   - LLM Maturity Stage in target range?
   - Data Residency posture compatible?
   - Decision authority for AI tooling exists in target role?

   **Gate 2 · Disqualifiers** (any hit → reject):
   - Anti-ICP pattern triggered?
   - Customer's primary moat is being a competitor's wrapper?
   - Customer asks "swap the model" in first conversation?

   **Gate 3 · Soft scoring** (sum points):
   - Industry in target list: +2
   - Champion identified (specific name): +2
   - Model spend trajectory growing 30%+: +3
   - Already uses a competitor we displace well: +2
   - Already uses a complementary tool we integrate with: +1
   - Has shipped public MCP server / Agent Skill (Constitution #6): +2
   - Founder publicly active on AI-native topics: +1

3. **Assign tier**:

   | Tier | Criteria | Action |
   |---|---|---|
   | T1 | Hard qualifiers pass + soft score ≥ 8 | Outbound this week |
   | T2 | Hard qualifiers pass + soft score 4-7 | Add to nurture; wait for signal trigger |
   | T3 | Hard qualifiers pass + soft score 1-3 | Watch list; quarterly re-review |
   | DQ | Any disqualifier or hard qualifier fail | Reject. Document reason. |

4. **For T1 accounts**, also produce:
   - **Probable rung** (where they are on Technical Credibility Ladder from `positioning.md`)
   - **First-touch angle** specific to their signals
   - **Stakeholder to target** with rationale

5. **Save output** to `outputs/YYYY-MM-DD-scoring-{batch-name}.md` with this structure:

```
# Account Scoring · [Batch name] · [Date]

## T1 (action this week) — [N accounts]
### [Account domain] · score [N]
- Stage: [N], DR posture: [X], Spend trajectory: [Y]
- Champion: [name + role + source]
- Rung: [N], first-touch angle: [...]
- Run technical-poc-brief? [yes/no]

## T2 (nurture) — [N accounts]
[lighter format]

## T3 (watch) — [N accounts]
[domain + reason only]

## Disqualified — [N accounts]
[domain + reason — kept for learning loop]

## Patterns surfaced this batch
- [trend observation]
- [hidden disqualifier emerging — feed back to icp-definition.md anti-ICP if recurring]
```

## Anti-patterns

- Don't score on company size alone. Traditional axis; weak in AI-native.
- Don't over-trust soft qualifiers. Hard qualifiers and disqualifiers are the gates; soft scoring is just ordering.
- Don't reject T2 / T3 — they're future T1s. Re-score quarterly.
- Don't run scoring without first ensuring `context/icp-definition.md` was updated within the last 30 days. Stale ICP → useless scoring.

## Trace to constitution

Constitution #1 (Living ICP). This skill is how the ICP file becomes operational — the file alone is just a doc; the file × this skill = a working filter on the entire pipeline.
