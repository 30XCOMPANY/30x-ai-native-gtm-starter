# Capability Obsolescence Cases + AI-Native ICP Evidence

> Research compiled May 2026. All cases sourced from public reporting. Use these as anchors when writing your own `context/competitor-radar.md` and `context/icp-definition.md`.

---

## Part 1 · Death Cases (10)

Ten AI products that died, pivoted, or got reverse-acqui-hired between 2022 and 2025 due to foundation-model capability shifts. Each case tags the *trigger event* — these become your radar items.

---

### 1. Jasper AI — GPT-3.5's first public casualty

- **Product**: GPT-3 wrapper for marketing copy. Pre-ChatGPT poster child of the "$1.5B valuation in 18 months" generative-AI gold rush.
- **Trigger**: ChatGPT public launch (2022-11) + GPT-4 (2023-03).
- **Impact**: ARR projection cut from $90M → ~$55M within 9 months. Internal valuation marked down 20%. Layoffs in 2023-07. Both founders (CEO + CTO) resigned 2023-09.
- **Response**: Pivot from SMB / individual creator → mid-market marketing teams. Rebuilt product around "brand voice" features that ChatGPT didn't replicate.
- **Lesson**: When OpenAI gives away your core feature for free in ChatGPT, the UI wrapper layer is a depreciating asset. Jasper mistook *"GPT-3 + prompt templates"* for a moat.
- **Sources**:
  - [The Information — Jasper cuts internal valuation](https://www.theinformation.com/articles/jasper-an-early-generative-ai-winner-cuts-internal-valuation-as-growth-slows)
  - [Maginative — Jasper growth slows](https://www.maginative.com/article/jasper-cuts-internal-valuation-as-ai-growth-slows/)

---

### 2. Chegg — non-AI company killed by ChatGPT consumption

- **Product**: Public-market education-tutoring platform. Not an AI company. Got destroyed *as a customer of human cognition* anyway.
- **Trigger**: ChatGPT (2022-11) + GPT-4 (2023-03).
- **Impact**: 2023-05-02 earnings disclosed "ChatGPT affecting customer acquisition." **Stock dropped 48% in one day**, $1B market cap evaporated. Q2 guidance $175-178M vs analyst $193.6M. Full-year guidance withdrawn. By 2025, market cap ~1/3 of pre-ChatGPT level.
- **Response**: Launched CheggMate with OpenAI partnership. Couldn't compete with "students just use ChatGPT for free."
- **Lesson**: First publicly-traded company to disclose LLM impact in earnings. Capability obsolescence hits *information-intermediary* SaaS, not just AI startups. If your product is a paid wrapper around knowledge that an LLM now hands out free, you are Chegg.
- **Sources**:
  - [CNBC — Chegg drops 40%+](https://www.cnbc.com/2023/05/02/chegg-drops-more-than-40percent-after-saying-chatgpt-is-killing-its-business.html)
  - [Fortune — Chegg shares tumble](https://fortune.com/2023/05/02/chegg-shares-tumble-students-fleeing-chatgpt-a-i/)

---

### 3. Character.AI — $5B valuation, $2.7B reverse acqui-hire

- **Product**: AI companion / role-play. Peak ~20M MAU.
- **Trigger**: Not a single model release — *foundation-model commoditization*. Once GPT-4 / Claude 3 / Gemini 1.5 could all run emotional dialogue, Character's self-trained model advantage disappeared while training costs stayed.
- **Impact**: 2023 valuation $5B. August 2024 Google "reverse acqui-hires" Noam Shazeer + Daniel De Freitas + ~30 core engineers for **$2.7B**. Shazeer takes over Gemini. Company technically still exists but is essentially a shell + licensing deal.
- **Response**: Abandoned foundation-model ambition. Pivoted to model licensing.
- **Lesson**: "Build a foundation model AND a consumer product" is a fatal both-and in the face of hyperscaler subsidization. Character's official line: *"The landscape has shifted, many pretrained models are available."*
- **Sources**:
  - [DeepLearning.AI — Google acquires Character.AI](https://www.deeplearning.ai/the-batch/google-acquires-character-ai-talent-and-tech-in-strategic-move)
  - [AIM — Old employees, new dollars](https://aimmediahouse.com/market-industry/old-employees-new-dollars-googles-2-7-billion-investment-in-character-ais-reverse-acquihire-for-ai-innovation)

---

### 4. Inflection AI — $4B valuation → Microsoft "non-acquisition"

- **Product**: Pi, personal AI assistant by DeepMind co-founder Mustafa Suleyman.
- **Trigger**: GPT-4 (2023-03) + free ChatGPT + Claude — everyone gave away Pi's core experience.
- **Impact**: Raised $1.3B at $4B valuation in 2023-06. By March 2024 Suleyman + chief scientist Karén Simonyan + nearly the entire core team joined Microsoft to run the new Microsoft AI (Copilot) division. Inflection still exists as a B2B API company with a new CEO. Microsoft structured the deal to avoid antitrust review.
- **Response**: Forced pivot from consumer → B2B API licensing.
- **Lesson**: Consumer-AI without distribution (OS, Office, Search) is a death zone. Per Fortune: *"Inflection faces hyperscalers with $100B cash who can subsidize the market for free."*
- **Sources**:
  - [Fortune — Microsoft surprise Inflection deal](https://fortune.com/2024/03/19/microsoft-surprise-deal-inflection-ai-mustafa-suleyman-reid-hoffman-questions/)
  - [Microsoft blog — Suleyman joins Microsoft](https://blogs.microsoft.com/blog/2024/03/19/mustafa-suleyman-deepmind-and-inflection-co-founder-joins-microsoft-to-lead-copilot/)

---

### 5. Adept AI — agent-pioneer crushed by training costs

- **Product**: ACT-1 / ACT-2 — agents that could operate browsers and software.
- **Trigger**: GPT-4 + Claude 3 raised general reasoning beyond Adept's self-trained model's reach, while Adept still had to burn cash training its own foundation model.
- **Impact**: $1B valuation in 2023. June 2024: CEO David Luan + 4 co-founders + core engineers "license + acqui-hired" by Amazon. ~20 people remain with a new CEO. Amazon paid licensing fees back to original investors.
- **Response**: Abandoned general foundation model. Remaining team builds enterprise agents only.
- **Lesson**: "Both train general intelligence AND ship enterprise agents" is unsustainable. Adept's own statement: *training general intelligence while building enterprise agents is dual-burn that doesn't work.*
- **Sources**:
  - [Semafor — Adept investors paid back after Amazon hires team](https://www.semafor.com/article/08/02/2024/investors-in-adept-ai-will-be-paid-back-after-amazon-hires-startups-top-talent)

---

### 6. Stability AI — open-source narrative couldn't carry burn rate

- **Product**: Stable Diffusion open-source image model.
- **Trigger**: DALL-E 3 (2023-10, ChatGPT integration), Midjourney v6, Flux, plus SD3's troubled launch.
- **Impact**: $8M/month burn rate in 2023-10, $4B raise attempted at unrealistic valuation, failed. CEO Emad Mostaque resigned 2024-03 (also caught fabricating academic credentials), saying *"you can't beat centralized AI with more centralized AI."* April 2024 layoffs of ~10% (20 people).
- **Response**: Management replaced, downsized, pivoted toward B2B media licensing.
- **Lesson**: Open source is not a business model — it's a distribution strategy that must be paired with a commercial loop. Stability had no commercial loop.
- **Sources**:
  - [TechCrunch — Stability CEO resigns](https://techcrunch.com/2024/03/22/stability-ai-ceo-resigns-because-youre-not-going-to-beat-centralized-ai-with-more-centralized-ai/)
  - [CNBC — Stability lays off 10%](https://www.cnbc.com/2024/04/18/ai-startup-stability-lays-off-10percent-of-employees-after-ceo-exit.html)

---

### 7. Humane AI Pin — hardware can't beat the phone running the same model

- **Product**: $700 wearable AI pin, OpenAI-backed.
- **Trigger**: ChatGPT iPhone app + GPT-4o. Same underlying model, better device.
- **Impact**: Raised $230M+, peak valuation $700M+. Shipped April 2024 to disastrous reviews (slow, overheating, terrible battery, unreliable). February 2025 sold to HP for **$116M** — less than half the funding raised. **Feb 28 2025 all ~10,000 shipped units remote-bricked.**
- **Response**: None. Acquired and shut down.
- **Lesson**: "AI hardware" = "a better AI interface than your phone," otherwise it doesn't exist. Rabbit R1 suffered parallel fate — heavy returns, payroll trouble.
- **Sources**:
  - [Laptop Mag — Humane AI Pin failed](https://www.laptopmag.com/ai/humane-ai-pin-failed-gadget)
  - [Technowize — Humane shutdown](https://www.technowize.com/the-humane-ai-pin-shutdown-surprises-no-one-hp-walks-away-a-winner/)

---

### 8. Rewind / Limitless — two pivots, then Meta bought the team

- **Product**: Rewind (Mac screen recording + AI search), renamed Limitless 2024, also shipped a Pendant necklace.
- **Trigger**: Local + cloud LLMs commoditized, Apple Intelligence launching, GPT-4o multimodal.
- **Impact**: a16z led at $350M valuation in 2023. April 2024 abandoned Mac app, pivoted to wearable. **December 2025 acquired by Meta** — Rewind app shut down 2025-12-19, Pendant sales halted.
- **Response**: Two pivots → acquisition.
- **Lesson**: When OS vendors absorb the capability, independent apps don't have a survival window. Rewind's "personal memory" value-prop was wholly consumed by Apple Intelligence + Meta Glasses.
- **Sources**:
  - [9to5Mac — Rewind / Limitless / Meta](https://9to5mac.com/2025/12/05/rewind-limitless-meta-acquisition/)

---

### 9. PDF Chat wrapper wave — DevDay 2023 cleared the field overnight

- **Products**: ChatPDF, PDF.ai, AskYourPDF, dozens of "chat with your documents" tools.
- **Trigger**: OpenAI DevDay 2023-11 launched native PDF/file understanding in ChatGPT + Assistants API + GPTs.
- **Impact**: Industry analysis showed dozens of chat-with-doc tools had their paid feature go free overnight. **966 AI startups shut down in 2024, 25.6% more than 2023.** Early-2024 bankruptcies up 60% vs 2023.
- **Response**: Survivors pivoted vertical (legal, medical). Most closed.
- **Lesson**: OpenAI DevDay = wrapper-company judgment day. Foundation-model companies absorb a layer of application every ~6 months.
- **Sources**:
  - [Fast Company — GPT Store threats](https://www.fastcompany.com/90991188/openais-gpt-store-might-not-have-killed-the-company-but-it-could-still-threaten-ai-startups)
  - [DEV — Graveyard of AI startups](https://dev.to/dev_tips/the-graveyard-of-ai-startups-startups-that-forgot-to-build-real-value-5ad9)

---

### 10. Voice AI — GPT-4o Realtime API rewrote the cost curve

- **Trigger**: GPT-4o (2024-05), Realtime API (2024-09), gpt-realtime price cut 2025-08 to $32/$64 per 1M tokens (another -20%).
- **Affected**: Traditional IVR / voice bot companies (PolyAI, Cresta, Replicant), self-trained voice model companies (Hume EVI).
- **Impact**:
  - Hume forced to release EVI 2 at $0.072/min, half of OpenAI's price, just to maintain differentiation
  - PolyAI repositioned around "phone-first managed service + vertical data" as moat, not model capability
- **Lesson**: Voice isn't a model problem — it's a telephony + compliance + data-loop problem. Just being able to do "voice-to-voice" cannot beat OpenAI's price curve.
- **Sources**:
  - [OpenAI — gpt-realtime](https://openai.com/index/introducing-gpt-realtime/)
  - [Hume — EVI 2 vs GPT-4o voice](https://www.hume.ai/blog/evi2-vs-gpt4ovoice)

---

## Cross-case taxonomy: 5 ways AI startups die

| Death pattern | Trigger | Representative cases |
|---|---|---|
| Wrapper eaten by foundation model | DevDay-class release | Jasper, PDF Chat wave, Copy.ai |
| Foundation-model burn-rate crushes you | Hyperscaler subsidization | Inflection, Adept, Character, Stability |
| Hardware loses to the phone | Same model, better device | Humane, Rabbit, Rewind |
| Information intermediary replaced | LLMs answer directly | Chegg, parts of Quora, parts of Stack Overflow |
| OS integration absorbs the standalone app | Apple Intelligence / Copilot | Rewind, "AI email assistant" category |

---

## Part 2 · AI-Native ICP Evidence

Six companies whose public ICP definitions include dimensions that traditional B2B SaaS ICPs do not.

---

### Cursor (Anysphere)

- **Traditional ICP fields**: developer role, company size, industry.
- **AI-native fields added**:
  - **AI coding tool maturity** — Cursor's sales clearly distinguishes "already using Copilot" vs "no AI tools yet."
  - **Codebase size + private deployment requirement** — Pro ($20) vs Enterprise ($40/seat/mo) split on SSO, audit log, on-premise, *"AI data governance"* axes — not seat count.
  - **Agentic preference by company type** — industry data: **startups 75% choose Claude Code** (agentic multi-step), **enterprise 56% choose GitHub Copilot** (procurement + distribution). Cursor's ICP segments on this.
- **Current state**: $2B ARR, 1M paid users, 67% of Fortune 500 deployed.
- **Sources**:
  - [GetPanto — Cursor statistics](https://www.getpanto.ai/blog/cursor-ai-statistics)
  - [IdeaPlan — AI coding market share](https://www.ideaplan.io/blog/ai-coding-assistant-market-share-2026)

---

### Glean

- **Traditional**: 500-2000 employee companies, CIO/CTO/KM Lead.
- **AI-native fields**:
  - **Information-fragmentation severity** (SaaS tool count × knowledge-worker ratio) as qualitative ICP — not industry.
  - **AI experimentation budget readiness** — explicitly targets *"companies with AI budget post-ChatGPT moment."*
  - **Typical land**: $50k-$100k departmental pilot → expand to $500k+. ICP includes whether there's an **AI Center of Excellence champion**.
- **Sources**:
  - [Contrary Research — Glean](https://research.contrary.com/company/glean)

---

### Harvey AI

- **Traditional**: large law firms, GC.
- **AI-native fields**:
  - **"Am Law 100" allowlist as ICP starting point** — not industry/size, a *named-entity allowlist* satisfying privacy + brand trust + compliance budget.
  - **No self-serve, no public pricing** — implies ICP includes "willing to sign 6-figure PoC without free trial."
  - **Azure OpenAI deployment requirement** — ICP includes "accepts Azure data residency."
- **Sources**:
  - [Harvey customers](https://www.harvey.ai/customers)
  - [Microsoft — Harvey Azure case study](https://www.microsoft.com/en/customers/story/19750-harvey-azure-open-ai-service)

---

### LangChain / LangSmith

- **AI-native fields**:
  - **"In production with LLM apps already"** — LangSmith positions as "production observability," implying ICP has passed the *"we want to try LLMs"* stage.
  - **SDK heterogeneity tolerance** — works with OpenAI, Anthropic, Vercel AI SDK, LlamaIndex, custom — implying ICP is a **multi-model router** player, not single-vendor lock.
  - **Agent / RAG pipeline deployed** — ICP is no longer "team size" but "AI workflow complexity."
- **Sources**:
  - [LangSmith observability](https://www.langchain.com/langsmith/observability)

---

### Humanloop / Braintrust / Vellum (LLM-ops cohort)

Highly similar ICP language across this cohort:

- **Eval-driven maturity** — Braintrust explicitly: *"want eval-driven iteration with datasets, scorers."* New ICP axis: whether team already runs LLM evals.
- **Cross-functional collaboration depth** — Humanloop: *"prompt changes need buy-in from engineering, product, and subject matter experts."* ICP includes "product/eng/SME collaboration depth."
- **Deployment shape preference** — Vellum lists SaaS / self-hosted / VPC / fully-private — ICP must have "data residency requirement" field.
- **Sources**:
  - [Vellum — alternatives to Humanloop](https://www.vellum.ai/blog/top-humanloop-alternatives-in-2025)
  - [Latent Space — Braintrust](https://www.latent.space/p/braintrust)

---

### Codeium (privacy-first dev sub-segment)

- **AI-native fields**: explicitly *"privacy-focused developers who need lightweight, open-source workflows."* First filter is **data-privacy tolerance + deployment preference**, not company size or role.
- This is *the same market as Cursor* sliced into a sub-segment using AI-native dimensions.
- **Sources**:
  - [UC Strategies — Copilot vs Cursor vs Codeium](https://ucstrategies.com/news/copilot-vs-cursor-vs-codeium-which-ai-coding-assistant-actually-wins-in-2026/)

---

## Living ICP — evidence it's not just a meme

1. **Operating cadence in the wild**: GTM playbooks now prescribe *"weekly refresh accounts based on most recent buying signals + monthly reply-rate review + quarterly ICP definition revisit"* (martal.ca, IndexBox, devcommx). Multiple sources agree on the cadence.
2. **Foundation-model release rhythm forces drift**: OpenAI / Anthropic / Google ship major model/price updates every 4-6 months (GPT-4 → 4 Turbo → 4o → o1 → o3; Claude 2 → 3 → 3.5 → Opus 4 → 4.5 → 4.7). **Each release reshuffles which customers just gained capability to run a given workflow** — ICP must follow.
3. **Failure-case reverse evidence**: Jasper anchored ICP on *"uses GPT-3 + prompt templates for marketing copy"* — ICP evaporated 1 week after GPT-3.5. Inflection anchored on *"consumers wanting an AI friend"* — ICP consumed by free ChatGPT.
- **Sources**:
  - [Martal — Living ICP cadence](https://martal.ca/gtm-strategy-lb/)
  - [GTM Strategist — 2026 State of AI GTM](https://knowledge.gtmstrategist.com/p/the-2026-state-of-ai-for-gtm-workflows)

---

## The three ICP dimensions traditional SaaS doesn't have

Use these directly when filling `context/icp-definition.md`.

### 1. LLM Maturity Stage
- *No LLM API yet* → *Trying ChatGPT Plus internally* → *Prototyping with OpenAI API* → *Running production LLM apps* → *Multi-model router* → *Fine-tuning + RAG in production*
- Implicit in Cursor, LangSmith, Humanloop, Glean ICPs.

### 2. Data Residency × Deployment Mode
- *Public API OK* → *Azure-OpenAI only* → *VPC required* → *On-prem required* → *Air-gapped*
- Harvey forced to Azure, Codeium positions on privacy, Vellum lists 4 deployment modes. **This single field can determine whether a deal closes.**

### 3. Model Spend Trajectory
- Monthly LLM API spend ($0 / $1k / $10k / $100k+) + 6-month growth rate.
- Forward-looking indicator. A company at $50k/mo with 30%/mo growth is the *core* ICP for LLM-ops / eval / observability / multi-model-router tools.
- **Traditional SaaS has no analog** — "annual software budget" doesn't capture this because LLM spend is token-elastic.

---

## Five capability-obsolescence early-warning signals

Order roughly matches signal strength:

1. **Your core feature runs natively in ChatGPT / Claude / Copilot default UI.** (Strongest signal — PDF chat, Jasper, Copy.ai.)
2. **OpenAI / Anthropic DevDay agenda is public** — any keyword overlap with your product is a 7-day warning. DevDay 2023 killed a whole category in one evening.
3. **Foundation-model benchmark jumps in your vertical.** GPT-4 on bar exam, Claude 3.5 on code, etc. Usually a 6-month window before commercial impact.
4. **Customer churn reason shifts** from *"price"* to *"we just use ChatGPT for that now."* (Chegg's earnings language.)
5. **Your prompt-engineering moat evaporates with new model versions** (old version needed 100-line prompts, new version one-shots it). Your IP is depreciating.
6. **Customers ask "what model do you use? Can you swap to Claude?"** They've matured into treating you as a router. Your product value is being compressed.
7. **Hyperscaler announces "free / unlimited"** — Microsoft 365 Copilot inclusion killed standalone AI email tools.
8. **OS vendor absorbs your capability** (Apple Intelligence, Windows Copilot+ PC) — Rewind's cause of death.

---

## The single biggest ICP mistake AI-native companies make

**Defining ICP as "companies that use LLMs" rather than "companies at a specific LLM maturity stage × data posture × spend trajectory."**

Looks like:
- *"Mid-market SaaS, 10-50 engineers, wants AI capability"* → essentially undefined. 90% of this pool just uses ChatGPT Team and is fine.
- The ICP subset that actually closes: *"already running LLM in prod, ≥$5k/mo spend, has ≥1 AI engineer, has hit hallucination pain, evaluating eval/observability."* Maybe 5% of the original pool, but **50%+ close rate**.

Second-biggest mistake: cutting ICP on traditional SaaS axes (industry × size × role) instead of AI-native axes (maturity × posture × spend). Pipeline looks huge (millions of "mid-market CTOs"), conversion is near-zero — because traditional axes are nearly uncorrelated with AI purchase decisions.
