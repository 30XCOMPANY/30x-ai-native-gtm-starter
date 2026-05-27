---
name: signal-to-integration-pitch
description: Turn a fired signal into an integration-partnership pitch. For platform companies (Vercel, Cursor, Claude, Cloudflare, Linear, Slack, Notion) — pitch them to ship your tool inside their distribution. implementation of integration-led growth + agent-native distribution.
---

# Skill · signal-to-integration-pitch

## What this does

Integration is the growth lever that compounds. Agent-native distribution is the 2026 must-do. This skill builds the pitch artifact that gets you on a platform's integration shortlist.

Different from `signal-to-content` (which is broadcast); this is direct, asymmetric, B2B partnership outreach.

## How to invoke

```
signal-to-integration-pitch: pitch [platform] to integrate us, triggered by [signal]
```

Examples:
- `signal-to-integration-pitch: pitch Vercel, triggered by their AI Gateway pricing announcement`
- `signal-to-integration-pitch: pitch Cursor, triggered by their MCP marketplace launch`
- `signal-to-integration-pitch: pitch Anthropic, triggered by their Agent Skills directory expansion`

## Steps Claude takes

1. **Read** `strategy/about.md`, `strategy/positioning.md` Rung 3 (Integration Depth proof points).

2. **Profile the platform**:
   - What's their **current integration model**? (App marketplace? MCP servers? Built-in connectors? SDK ecosystem?)
   - **What integrations did they ship in the last 90 days**? (Signals their bar and their gaps.)
   - **Who at the platform is responsible for ecosystem / DevRel / partnerships**? (Public roles, X handles, blog authors.)
   - **What was their last public roadmap signal** about integrations? (Conference talk, blog post, podcast appearance.)

3. **Build the asymmetric value proposition**:
   - What does **your tool give the platform's users** that the platform itself can't / won't build? (Be specific. "More features" fails.)
   - What does **the platform give you** beyond mere distribution? (Better than just "more users." Could be: pre-qualified audience, technical credibility transfer, OS-level data access, payments rail.)
   - What does the platform's **competition** lose if you ship here? (Useful asymmetric framing.)

4. **Draft the pitch artifact** — NOT an email yet. A **public-facing integration spec page**:

```
# [Your tool] for [Platform] · Integration Proposal

## What this is
[1 sentence: "X for users of Y who want Z."]

## Why now
[Cite the triggering signal — platform's recent move, their stated direction, their visible gap]

## What users get
- [Specific capability inside the platform, with example]
- [Specific outcome a user could not achieve without this integration]
- [Specific data / context the platform user already has that we'd unlock]

## What [Platform] gets
- [User-retention story — why people stay on platform longer because of us]
- [Data / engagement story]
- [Brand / category-leadership story if applicable]

## Technical shape
- Integration type: [MCP server / app marketplace listing / SDK / native]
- Implementation time: [days, with caveats]
- Maintenance commitment: [SLA we offer]
- Reference: [link to working prototype in our repo OR Vercel template OR live demo]

## Why us, not [obvious competitor]
[2-3 sentences. Asymmetric. Not "we're better"; be specific about which axis.]

## Proposed next step
- 30 min call with [their integration lead] in [Week of date]
- Or async review of [link to prototype]
```

5. **Then draft the outreach email** (3-line version):

```
Subject: [Specific signal observation] + integration proposal

[Their name] —

[1 sentence: observation about their recent move that proves you're paying attention, not spamming]

[1 sentence: the specific user outcome your integration enables on their platform — quantified if possible]

[1 sentence: link to the public-facing proposal + clear ask]

[your name + role]
```

6. **Save both artifacts** to `outputs/YYYY-MM-DD-integration-{platform}.md` with email at top, proposal below.

7. **Pre-flight checklist** before send:
   - [ ] Have you actually shipped the prototype, or are you pitching vaporware? (Vaporware integration pitches kill credibility — Devin lesson.)
   - [ ] Is the proposed integration easier for the platform to *say yes* than *say no*? (Their effort < your effort = right asymmetry.)
   - [ ] Do you have a clear user already wanting this integration you can quote?
   - [ ] Have you tracked who at the platform has talked publicly about your category — that's your warm path.

## Anti-patterns

- Don't pitch as a feature. Pitch as a category-extension of their platform.
- Don't ask for a co-marketing splash. Ask for technical-listing first; co-marketing follows working integration.
- Don't compare yourself to other partners in your pitch. Don't even mention them.
- Don't send the proposal as a PDF attachment. Public URL. Always.

## Where this fits
integration-led growth and agent-native distribution. Every integration is a new growth curve; every agent-callable surface is a new discovery channel.
