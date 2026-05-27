# strategy/capability-radar.md · Foundation-model obsolescence radar

> Your real competitor isn't another startup. It's the next Claude / GPT / Gemini release. This file is where you track that.

---

## Models we track

| Model family | Latest version | Released | Next expected | Capability that could affect us |
|---|---|---|---|---|
| Claude (Anthropic) | _e.g. 4.7_ | YYYY-MM | Q_/YYYY | _e.g. long-context, tool use, native eval_ |
| GPT (OpenAI) | _e.g. 5.5_ | YYYY-MM | Q_/YYYY | _what threatens us_ |
| Gemini (Google) | _e.g. 3.0_ | YYYY-MM | Q_/YYYY | _what threatens us_ |
| Llama (Meta) | _e.g. 4_ | YYYY-MM | Q_/YYYY | _what threatens us_ |
| Others (Mistral / DeepSeek / Qwen / etc) | various | various | — | _watch list_ |

---

## Self-assessment · Five death patterns

For each, mark exposure (Low / Med / High):

| Pattern | Trigger | Our exposure |
|---|---|---|
| Wrapper eaten by foundation model | DevDay-class announcement | _L / M / H_ |
| Burn-rate crushes you (you train your own model) | Hyperscaler subsidization | _L / M / H_ |
| Hardware loses to phone | Same model in user's pocket | _L / M / H_ |
| Information intermediary replaced | LLM answers directly | _L / M / H_ |
| OS / platform integration absorbs you | Apple Intelligence / Copilot+ | _L / M / H_ |

Reference cases: see [`examples/our-flavor/examples/our-flavor/research/01-capability-obsolescence-and-icp.md`](../examples/our-flavor/examples/our-flavor/research/01-capability-obsolescence-and-icp.md).

---

## Active early-warning signals

Check these weekly:

- [ ] Our core feature runs in ChatGPT / Claude / Copilot native UI
- [ ] OpenAI / Anthropic DevDay agenda mentions our keyword
- [ ] Foundation-model benchmark jumps in our vertical (>10%)
- [ ] Customer churn reason shifts to "we just use [model] for that now"
- [ ] Our prompt-engineering moat evaporates with new model versions
- [ ] Customers ask "what model do you use? Can you swap?"
- [ ] Hyperscaler announces free / unlimited for our category
- [ ] OS vendor's roadmap mentions our capability

When any fires, jump to [`playbooks/capability-obsolescence-emergency.md`](../playbooks/capability-obsolescence-emergency.md).

---

## Watch log

> Append-only. One entry per noteworthy event.

```
### YYYY-MM-DD · [event]
- What: [release / announcement / benchmark / leak]
- Impact on us: [Low / Med / High]
- Action taken: [link to outputs/...]
```

---

> **[PROTOCOL]**: Run `skills/weekly-drift-audit` Mondays to refresh this file. The radar going stale is itself an obsolescence signal.
