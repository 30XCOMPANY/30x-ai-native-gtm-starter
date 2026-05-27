---
name: oss-pipeline-track
description: Track the AI-native Community → Customer funnel. Measures conversion through GitHub star → Discord active → trial → paid → enterprise stages. Identifies stuck cohorts and named-conversion candidates.
---

# Skill · oss-pipeline-track

## What this does

For companies with open-source presence (most AI-native), the customer funnel runs through OSS. Traditional CRM doesn't model this. This skill builds and maintains an OSS-funnel view that complements your CRM.

## How to invoke

```
run oss pipeline track
```

Run weekly or after major events (release, viral moment, conference).

## Steps Claude takes

1. **Define your funnel stages** (read from `context/profile.md` or first-run config):
   - **Aware**: GitHub stargazer
   - **Active**: Discord member with messages in last 30 days OR cloned repo (via traffic API)
   - **Engaged**: contributed issue / PR / discussion comment
   - **Trial**: signed up for managed product (if applicable)
   - **Paid**: paid customer
   - **Enterprise**: enterprise contract

2. **Pull current counts** for each stage:
   - GitHub stars (cumulative + last 7 days new): GitHub API
   - Discord members + active 30d: Discord API or scrape
   - Issue / PR / Discussion authors (deduplicated, last 90d)
   - Trial signups (from product database if connected via `sync/`)
   - Paid customers
   - Enterprise contracts

3. **Compute conversion rates**:
   - Aware → Active %
   - Active → Engaged %
   - Engaged → Trial %
   - Trial → Paid %
   - Paid → Enterprise %

4. **Identify bottlenecks**:
   - Which stage has the worst conversion vs industry benchmarks?
   - Has any stage's conversion dropped >20% vs last quarter?
   - Are there *named users* stuck at each stage who should be moved up?

5. **Generate named-action list**:

   - **Engaged who haven't tried trial**: list specific GitHub usernames who've filed issues but never signed up. Outreach with personal context ("Saw your issue on X, thought you'd want to try the managed version which handles this automatically.")
   - **Trial who didn't convert**: specific email signups who didn't activate / paid. Diagnose: missing feature? Wrong ICP? Pricing? Use `signal-to-content` or direct outreach.
   - **Paid customer who looks ready for Enterprise**: usage metrics, team-size growth signals. Schedule expansion conversation.

6. **Output report**:

```
# OSS Pipeline · [Date]

## Funnel snapshot
| Stage | Current | Δ 7d | Δ 90d |
|---|---|---|---|
| Aware (stars) | N | +N | +N |
| Active (Discord+) | N | ... | ... |
| Engaged (contributors) | N | ... | ... |
| Trial | N | ... | ... |
| Paid | N | ... | ... |
| Enterprise | N | ... | ... |

## Conversion rates
- Aware → Active: X% (vs benchmark Y%)
- Active → Engaged: X% (...)
- (...)

## Bottleneck this quarter
[stage] — current X%, was Y% three months ago. Hypothesis: [...]

## Named action list
### Engaged → Trial (target 5/week)
- [@username] · filed issue about [topic] · suggested action: [...]
- (...)

### Trial → Paid (target 3/week)
- [user.email@redacted] · signed up [date], didn't activate · suggested action: [...]

### Paid → Enterprise (target 1/month)
- [Account] · usage indicates team of N · suggested action: schedule expansion call
```

7. **Save** to `outputs/YYYY-MM-DD-oss-funnel.md`.

## Anti-patterns

- Don't mass-DM engaged GitHub users. Pick 3-5 per week with genuine context. AI-native devs treat mass DMs as spam.
- Don't ignore the "Aware → Active" stage as just vanity. A consistent star-but-not-Discord ratio means your community surface is wrong.
- Don't conflate trial signups from organic OSS with trial signups from paid acquisition. They convert differently; track separately.

## Trace to constitution

Constitution #3 (Community → Customer Funnel) — measurable, named, with explicit stage-to-stage conversion targets.
