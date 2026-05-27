# pipeline/accounts.md · Live target accounts

> The list. Weekly-rebuilt. T1 are this week's outbound. T2 nurture. T3 watch.

---

## T1 · Outbound this week

| Account | URL | Score | Champion | Signal fired | Next action | Owner |
|---|---|---|---|---|---|---|
| _e.g. Atlas Robotics_ | atlasrobotics.ai | 9/10 | Engineer B (@handle) | A1 GH velocity | Maya DM Aaron Wed | Maya |

## T2 · Nurture (signal not fresh, but ICP-fit)

| Account | URL | Score | Last signal | Date | Next watch |
|---|---|---|---|---|---|

## T3 · Watch (waiting on stronger signal)

| Account | URL | Why interesting | Watching for |
|---|---|---|---|

## Disqualified (this quarter)

> Keep for learning. Don't re-target without ICP change.

| Account | Reason | Date |
|---|---|---|

---

## How to populate this file

```
# Tuesday morning, before pipeline review:
run icp-scoring on the accounts that triggered signals last week
```

Output goes to `outputs/YYYY-MM-DD-scoring-{batch}.md`, then T1 entries get copied here.

## Anti-patterns

- Don't keep T1 entries past 14 days. Either they engaged, or they're T2.
- Don't pad T1 to look busy. 5–10 strong T1s > 50 weak ones.
- Don't pre-judge T3 — quarterly re-score, they become T1 with the right signal.

---

> **[PROTOCOL]**: When a T1 account closes (won or lost), append to `pipeline/customers.md` (won) or `Disqualified` (lost with reason). Don't just delete the row.
