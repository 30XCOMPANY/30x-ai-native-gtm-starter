---
name: weekly-drift-audit
description: Run weekly. Detects which context/ files are stale, which foundation-model events happened, which competitor moves matter, and drafts updates for human approval. Implements Living ICP's weekly cadence.
---

# Skill · weekly-drift-audit

## What this does

Without active maintenance, every `context/` file rots in 30 days. This skill audits the repo weekly, identifies what changed externally that should update the repo internally, and drafts the update for the user to approve.

## How to invoke

```
run weekly drift audit
```

Run every Monday morning ideally; takes 5 minutes of user time.

## Steps Claude takes

1. **Check repo age**:
   - For each `context/*.md` file, when was it last edited (git log if available, else file mtime)?
   - Flag any file > 14 days stale.

2. **Scan external events from last 7 days**:

   **Foundation-model events**:
   - Any major model release (Anthropic / OpenAI / Google / Meta / Mistral)?
   - Any pricing change at major providers?
   - Any new benchmark in relevant vertical?
   - Any DevDay-class announcement?

   **Competitor events** (from `context/competitor-radar.md` list):
   - Funding announcements
   - Product launches
   - Pricing changes
   - Public departures / acquisitions
   - Notable controversy

   **Integration / agent ecosystem events**:
   - New MCP servers in your category?
   - Cursor / Claude Code / Windsurf integration list changes?
   - Anthropic Agent Skills directory additions in your space?

   **Capability obsolescence early-warning** (`competitor-radar.md` Section 2.3 signals):
   - Did any of the 8 early-warning signals fire this week?

3. **Cross-reference against repo content**:
   - If a model release happened, does our `positioning.md` Rung 5 (obsolescence resistance) still hold?
   - If a competitor cut prices, does our `competitor-radar.md` battlecard need updating?
   - If our LLM Maturity Stage target group shifted (new releases changed their capability), does `icp-definition.md` need an evolution log entry?

4. **Draft updates** for user approval:

```
# Weekly Drift Audit · [Date]

## Files stale (>14 days)
- [file] · last touched [date] · suggested action: [...]

## External events worth tracking
### Foundation models
- [Event 1: e.g., "Claude 4.7 released 2026-MM-DD"]
  - Impact on us: [...]
  - Suggested repo update: [add evolution log entry to icp-definition.md / update competitor-radar.md Section 2.1]

### Competitor moves
- [Competitor X did Y]
  - Impact: [...]
  - Suggested update: [...]

### Agent / Integration ecosystem
- [event]
  - Impact: [...]

## Capability obsolescence signals fired this week
- [signal] — [explanation] — recommended escalation: [follow competitor-radar.md Section 2.4 emergency playbook]

## Drafts ready for approval
### Draft 1: ICP evolution log entry
[full draft text the user can paste-and-save]

### Draft 2: Competitor card update
[draft]

### Draft 3: Positioning Rung 5 update
[draft]

## No-op items (events that happened but don't require repo updates)
- [brief list, for completeness]

## Recommended priority
1. Approve and apply [Draft N] today
2. Schedule [activity] for this week
3. ...
```

5. **Save to** `outputs/YYYY-MM-DD-drift-audit.md`. Optionally Slack-ping a summary if `sync/` is configured.

6. **Wait for user approval** before applying any update. Drift audit drafts; user decides.

## Anti-patterns

- Don't auto-apply drafts. Living ICP requires human in the loop; that's the point.
- Don't flag every change. Distinguish "this might matter" from "this needs action now."
- Don't run if `context/icp-definition.md` was edited yesterday — wait at least 5 days between drift audits or you'll create churn.
- Don't include events outside your stated competitor / ICP scope just because they're trending. Focus.

## Trace to constitution

Constitutions #1 (Living ICP), #4 (Capability Obsolescence Radar). This skill is the operational implementation of "ICP refreshes weekly; obsolescence radar reviewed weekly."
