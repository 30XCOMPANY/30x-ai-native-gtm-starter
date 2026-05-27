# pipeline/ · Prospects, sequences, customers

> Where the sales motion lives. Targets, signals, outbound, customers — all the work between "we have an ICP" and "they paid".

## Files in this folder

| File / folder | What it is | Cadence |
|---|---|---|
| [`playbook.md`](./playbook.md) | How we sell — stages, ownership, conversion targets | Quarterly |
| [`signals.md`](./signals.md) | Signal library (what we watch + decay) | Weekly review |
| [`accounts.md`](./accounts.md) | Live target account list | **Weekly** rebuild |
| [`sequences/`](./sequences/) | Multi-touch outbound sequences | Monthly tune |
| [`customers.md`](./customers.md) | Active customers + health | Monthly |
| [`objections.md`](./objections.md) | Common objections + tested responses | When pattern emerges |

## How Claude helps here

| What you need | Skill to run |
|---|---|
| Score a batch of accounts against your ICP | `skills/icp-scoring` |
| Deep technical research on one prospect | `skills/technical-poc-brief` |
| Generate a multi-touch outbound sequence | `skills/outbound-sequence` |
| Answer a tough objection | `skills/objection-handle` |
| Pitch an integration partner | `skills/signal-to-integration-pitch` |
| Track OSS → paid funnel conversion | `skills/oss-pipeline-track` |

## Workflow (weekly)

```
Monday      run weekly-drift-audit → refresh signals + capability-radar
Monday      score new accounts from this week's signals
Tue–Thu     outbound to T1 accounts; technical-poc-brief for hot ones
Friday      log results, update accounts.md, queue next week's content
```

## Anti-patterns

- Don't outbound without a fired signal. Cold-to-cold = ignored.
- Don't outbound at scale without a tested sequence. Iterate on 10 before sending to 100.
- Don't keep dead accounts on the list. Cull weekly.

---

> **[PROTOCOL]**: Sequence templates that produce <5% reply rate after 30 sends get killed, not refined. The accounts file is the source of truth for the live pipeline.
