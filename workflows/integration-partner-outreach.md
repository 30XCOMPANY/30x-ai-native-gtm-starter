# Workflow · Integration Partner Outreach

> How to go from "we should integrate with Vercel / Cursor / Anthropic" to "we shipped the integration and they promoted it." For humans.
>
> Constitution #5 (Integration-Led Growth). Operationalized by `skills/signal-to-integration-pitch`.

---

## The "right" partner shortlist

For most AI-native B2B, your partner shortlist looks like this. Rank by impact / effort:

| Platform | Why partner | Effort to ship | Activation pattern |
|---|---|---|---|
| **Vercel** | Distribution to Next.js + AI SDK community (6M+ devs) | Medium (1-2 weeks) | Listed in Vercel templates + AI SDK partner page |
| **Anthropic** | Distribution via Claude / Skills directory | Low-medium (1 week) | Skills directory listing + MCP server |
| **Cursor / Windsurf** | Distribution to AI coding tool users | Medium (1-2 weeks) | Extension marketplace |
| **Linear** | Distribution to dev teams | Low (3-5 days) | Linear integration listing |
| **Slack** | Distribution to enterprise teams | Low-medium (1 week) | Slack App Directory |
| **Notion** | Distribution to product / ops teams | Medium (1-2 weeks) | Notion Connect API |
| **Cloudflare** | Distribution to edge / AI infra | High (2-3 weeks) | Workers AI partnership |

**Tier 2** (smaller but valuable): n8n, Zapier, Raycast, Arc Browser, Granola, Loom.

---

## Step-by-step partner outreach

### Step 1 · Pick exactly one partner to pursue first

The temptation is to email all of them. **Don't.** Pick one and do it well.

Selection criteria:
- Their user base maps to your ICP at 50%+ overlap
- Their team has a *named* partnerships / DevRel person publicly findable
- They've shipped at least one integration partnership in the last 6 months (active ecosystem)
- You can ship the integration in <2 weeks

### Step 2 · Ship a working prototype FIRST

Do *not* email the partner before you have something working. Vaporware pitches damage your credibility, and the partner's first ask will be "show me."

**Working prototype standard**:
- Their users can actually use it (not just a screenshot)
- Public repo with the integration code
- Live demo URL
- 60-second demo video

### Step 3 · Find the right human at the partner

- Their `/about` page or `/team` page
- Public blog posts about partnerships — see who authored / quoted
- DevRel hires they made in the last 12 months — those people *need* to ship partner stories
- LinkedIn search for "Partnerships" or "Developer Relations" + their company
- Their X / Twitter — who replies to partner questions

**Best target**: someone who has shipped a partner integration in the last 6 months. They're warm to the motion.

### Step 4 · Outreach (NOT cold email)

Multi-pronged, in this priority order:

1. **Public engagement first**: comment thoughtfully on the partner's recent post / blog (no agenda, just substance). Builds familiarity before ask.
2. **Warm intro if possible**: who in your network knows them?
3. **X DM** if they're active (lower friction than email)
4. **Email** as last resort, 3-line max (see `skills/signal-to-integration-pitch` for template)

What to NOT do:
- LinkedIn cold outreach
- Generic "would love to chat about partnership"
- PDF deck attached
- "Calendar link" before establishing interest

### Step 5 · Make their decision easy

When you do connect:
- Send the public integration proposal URL (from `skills/signal-to-integration-pitch`)
- Demo the working integration in 5 minutes
- Show *their users actively using it* (even 10 users counts)
- Quantify the user benefit (with a real example, not projection)
- Tell them what you want — "Listed in your directory" / "Co-marketing for launch" / "Joint customer story"

Their cost should be lower than your cost. You did the engineering; they "merely" promote.

### Step 6 · Co-marketing the launch

Once they say yes:
- Joint blog post (you draft, they review)
- Synchronized X posts at launch (specific time)
- Customer-quote pre-arranged from a shared customer
- Both teams active in replies for 48h after launch
- Webinar / demo within 2 weeks of launch (their audience)

### Step 7 · Compound

The first partnership is the hardest. The second is half as hard (you have a template + a credibility story).

After 3 partnerships:
- You're now "the company that ships partnerships." Inbound partner requests start.
- Reach out to all your existing customers and ask: "what tool do you wish we worked with?" — your customers tell you what to integrate.

---

## Anti-patterns

- **Asking for a partnership before you have customers** — partner will ask "who's using this?" and you'll have no answer
- **Building the integration after they say yes** — they'll lose patience
- **Co-marketing without a real customer story** — partner won't promote vaporware-fronted integrations
- **Spreading effort across 5 partnerships at once** — none will ship at the quality required for the partner to promote
- **Asking for revenue share** in the first partnership — get distribution first, money later

---

## When NOT to pursue a partnership

- Pre-PMF: focus on direct customers first
- The integration would require you to weaken your security model
- The partner's user base is wrong for your ICP (don't chase logos)
- The partner has shipped 100 integrations and treats them all like commodity listings — your effort won't compound
- The partnership requires exclusivity (almost always bad in AI-native)

---

## Measure

- Partner referral attribution (UTM parameters at minimum)
- Conversion rate of partner-acquired users vs direct
- Time-to-paid for partner-acquired users
- Quarterly: which partnerships are net-positive? Cut the ones that aren't.
