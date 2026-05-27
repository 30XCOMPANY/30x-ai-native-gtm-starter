---
name: technical-poc-brief
description: Given a prospect domain, produces a technical-buyer-shaped account brief. Replaces traditional "account research" with a brief organized around the Technical Credibility Ladder — what proof the prospect's engineers need to climb each rung.
---

# Skill · technical-poc-brief

## What this does

Traditional account research = "company size, funding, recent news." Useless to a technical buyer.

This skill produces what an *engineer* at the prospect would actually use: their tech stack, their AI maturity, their public commit / launch history, their compliance posture, their existing-tool fatigue points. Output ready for a 15-minute first call.

## How to invoke

```
run technical-poc-brief on https://prospect.com
```

## Steps Claude takes

1. **Read** `strategy/about.md`, `strategy/icp.md`, `strategy/positioning.md` for our identity.
2. **Profile the prospect across 6 axes**:

   - **Stack inference**:
     - GitHub org public repos (languages, dependencies, recent commits)
     - npm / pip / DockerHub publishings
     - Frontend tech (BuiltWith / Wappalyzer-style inference from headers)
     - LLM provider hints (job postings mentioning Anthropic / OpenAI / specific model names)

   - **LLM Maturity Stage estimate** (from `icp-definition.md` Section 1.1):
     - Stage 0-2 → Education-phase, deprioritize unless our wedge is education
     - Stage 3-4 → Primary target if our ICP matches
     - Stage 5 → Either premium customer or sophisticated competitor

   - **Data Residency / Deployment posture**:
     - Industry signals (FinTech / Healthcare / Defense → likely VPC+)
     - Public security page (SOC2, HIPAA, FedRAMP badges)
     - Geographic constraints (EU operations → GDPR data residency)

   - **Current AI tooling**:
     - What they've publicly said they use (blog posts, conference talks)
     - Inferable from dependents graph if our category has public packages

   - **Pain points (public)**:
     - GitHub Issues on competitors' repos where this prospect's domain appears
     - Public complaints / requests on Twitter / X
     - Job postings indicating gaps ("Looking for X engineer to build Y")

   - **People to know**:
     - Founders / executive technical leaders (X handles, GitHub usernames)
     - Likely champion role (search team page + LinkedIn)
     - Public technical writers / DevRel from their team

3. **Score against ICP** (gates from `icp-definition.md` Section 6).

4. **Output a brief** with the following structure:

```
# [Prospect] · Technical POC Brief
## Snapshot
[1 paragraph: who they are, what they ship, why they fit ICP]

## ICP score: [N/10]
Hard qualifiers: [pass/fail]
Soft qualifiers points: [X]
Disqualifiers: [any?]

## Stack inference
[concise enumeration with sources]

## LLM Maturity assessment
Stage: [N]
Evidence: [bullets]

## Data Residency posture
[posture] + evidence

## Tooling currently in use
- AI coding: [tool]
- Inference: [provider]
- Eval/obs: [tool]
- (etc.)

## Probable pain points
1. [pain] — evidence: [source]
2. ...

## Stakeholders
- Founder/CEO: [name, X handle]
- Likely champion: [role, evidence]
- Decision-maker: [role]

## Rung diagnosis: what proof they need first
Their entry rung is [N] because [reason]. To advance them, demonstrate:
- [specific proof artifact]
- [specific proof artifact]

## First-touch angle
[1-2 sentence pitch tied to their specific signal/pain/role — NOT generic]

## Risk flags
- [any anti-ICP triggers]
- [any capability obsolescence flags — does our positioning hold against the model they're betting on?]
```

5. **Save** to `outputs/YYYY-MM-DD-poc-{prospect}.md`.

## Anti-patterns

- Don't invent stack inferences. If unclear, say "unclear from public sources."
- Don't lead the brief with "Here's why they need our product." Start with **what they look like**, not **why they should buy**.
- Don't include personal social media of non-public-facing engineers.

## Where this fits
Maps directly to positioning rungs — the brief tells the seller *which rung* the buyer is on and *what proof* moves them to the next.
