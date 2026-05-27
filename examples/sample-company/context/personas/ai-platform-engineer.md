# Persona · AI Platform Engineer at Series A-C AI-Native Startup

> Primary persona for Helmsman. Filled out 2026-04-08.

## Identity

- **Persona name**: "Maya's old self at Anthropic" — internal nickname Maya gave the persona because it's literally her past self.
- **Common titles**: AI Platform Engineer, Senior AI Engineer, ML Platform Engineer, Head of AI Infrastructure, Founding AI Engineer
- **Where you find them**: GitHub (active in repos like vercel/ai, langchain-ai/langchain, anthropics/anthropic-sdk-python), X (technical AI Twitter), Discord (Anthropic Discord, Vercel AI SDK Discord, MLOps Community), conferences (AI Engineer Summit, AI Engineer Foundation events)
- **Tools they live in**: Cursor or Claude Code as primary editor + Linear for tickets + Slack for company + Vercel for deploys (often) + Modal or Replicate or Together for inference + Notion for docs

## Their world

- **LLM provider(s)**: typically multi-model. Primary Anthropic Claude (~60%), OpenAI GPT (~30%), at least one open model on Together / Fireworks / Replicate
- **Inference infra**: split — uses providers (Together / Fireworks) for batch, hosted APIs for production-critical
- **Eval / observability**: rolled their own (most common); some Braintrust / Langfuse; LangSmith if LangChain user
- **Coding assistant**: Cursor (majority), Claude Code (growing), GitHub Copilot (declining)
- **Orchestration**: Vercel AI SDK (modern), LangChain (legacy), home-grown agent loop (sophisticated teams)
- **LLM Maturity Stage**: 3 or 4
- **Monthly LLM spend**: $5k-50k for their team (their employer's spend is higher)
- **What they read**: Latent Space, Simon Willison's blog, Hamel Husain's blog, occasional Substack from ex-OpenAI / ex-Anthropic engineers
- **Who they follow on X**: Karpathy, Swyx, Simon Willison, Logan Kilpatrick, Hamel Husain, Eugene Yan, Maya Cheng (us), Daniel Park (us), Greg Brockman, dario amodei, anjney midha

## Success metrics they own

- [x] Production agent quality (regression-free)
- [x] Time-to-detect-and-fix when something breaks
- [x] LLM cost efficiency (multi-model selection)
- [x] Latency / throughput of AI features
- [ ] Compliance — they care but don't own
- [ ] Sales effectiveness — they don't own

## Buying process

- **Initial trigger**: discovers tools via X thread, Hacker News, conference talk, or DevRel content. Almost never via cold email.
- **Evaluation pattern**:
  1. They try the OSS CLI (no signup, ~10 minutes)
  2. They reproduce on their staging traces (~1 hour)
  3. They evangelize to 1-2 teammates
  4. They get manager approval (varies — could be $99 credit card to procurement-gated)
  5. They onboard team to Cloud
- **Decision authority**:
  - [x] Can sign up to $500/mo individually (Maya tier)
  - [ ] Team manager signs up to $1k/mo → typical for Helmsman Team
  - [x] Department head / VP signs up to $5k/mo → Enterprise entry
- **Time to decision**: 5 days (Starter) → 6 weeks (Team) → 3-6 months (Enterprise)
- **Top 3 objections they raise**:
  1. "Can we self-host? We don't want our traces in your cloud" → answer: VPC option for Enterprise; OSS CLI for trace-locality
  2. "What happens when Anthropic ships native eval?" → answer: see `positioning.md` Rung 5 prepared response
  3. "Pricing seems steep for per-trace overage" → answer: predictable Starter / Team caps + Enterprise volume pricing

## Attention triggers

**What works**:
- [x] Concrete code sample they can run in 60 seconds
- [x] Benchmark vs their current tool (with reproduction script in GitHub)
- [x] Maya's ex-Anthropic credential — strong signal of credibility
- [x] Open-source repo with recent commits + visible roadmap
- [x] Specific named-customer evidence in their vertical (Lovable, Modal)
- [x] DM from Maya personally (works only at Series A-B stage)

**What doesn't work**:
- [ ] Generic "AI observability" copy — too vague
- [ ] LinkedIn cold message
- [ ] PDF whitepaper / contact-gated content
- [ ] Long video without code in it
- [ ] Webinar invites

## Outbound hooks (signal-tied for this persona)

```
### Signal: B6 (MCP server published)
Hook: "Saw your MCP server. Curious how you're handling agent-initiated quality regression — that's our wheelhouse. 15 min coffee?"

### Signal: B4 (Claude 4.7 released)
Hook: "Claude 4.7 dropped 4 hours ago. Your eval baselines from 4.6 are now stale. We can re-baseline in 90 minutes — want to see?"

### Signal: D1 (HN front page)
Hook: "Just saw your post hit HN frontpage. Traffic surge typically reveals 2-3 agent regression types. Free 30-day eval setup if you want insurance?"

### Signal: A1 (their repo viral)
Hook: "Watched {repo} hit 1k stars this week. Production reliability becomes a different problem at that scale — we'd love to hear how you're approaching it. Quick chat?"
```

## Anti-patterns for this persona

- Mass sequence (3+ touches, same message): blocked + unsubscribed
- Asking for calendar before showing product: blocked
- Forwarded "executive summary" PDF: blocked
- "How are you doing with AI?" opener: ignored
- Generic "let's connect on LinkedIn" outreach: ignored

## Reference examples

- **Closed customer (anonymized)**: "Engineer A" at Atlas Robotics. Discovered us via Maya's blog post on regression detection; tried CLI within 24h of post; converted to Starter in 5 days; expanded to Team after 6 weeks; champion for Enterprise upgrade at 4 months.
- **Champion who didn't close**: "Engineer B" at Vector Compute. Loved the product but his manager picked Braintrust because Braintrust had shipped framework integration 2 weeks earlier. Lesson: integration depth + timing matters more than positioning quality.
- **Persona influencer (public)**: Hamel Husain (independent AI eng, ex-GitHub) — his writing on evals defines how this persona thinks. We citation-reference him in our content.
