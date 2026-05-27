# Playbook · Viral Moment Traffic Surge

> When HN frontpage / Karpathy retweet / Product Hunt #1 / Bolt-style demo virality fires, you have a 48-hour window. This playbook makes it productive instead of overwhelming.

---

## What triggers this playbook

- HN frontpage (>300 points)
- Major KOL retweet / mention (Karpathy, Swyx, Simon Willison, Hamel Husain, Logan Kilpatrick, Andrew Ng, etc.)
- Product Hunt #1 of the day
- A founder's tweet about your product crossing 10k+ impressions
- An open-source repo of yours getting picked up in TLDR AI / Ben's Bites / The Rundown

---

## Hour 0 — first 60 minutes

1. **Verify the source and trajectory**:
   - Where's the traffic from?
   - Is it sustained or already cresting?
   - Are people staying or bouncing in 5 seconds?

2. **Check infrastructure**:
   - Is your landing page up?
   - Is signup working?
   - Are your servers handling load?
   - Are you ratelimiting yourself by accident?

3. **Notify the team in real-time**:
   - Slack #firealarm or equivalent
   - Founders awake
   - On-call infrastructure engineer alerted
   - DevRel monitoring channels

---

## Hour 1-6 — engagement

### On the original post / thread

- **Reply within 30 minutes** to top comments / questions. Use the founder account.
- **Don't sell**. Answer technical questions, acknowledge criticism, share context.
- **Pin a useful comment** with relevant links (docs, GitHub, "what's coming next") — this is your unobtrusive funnel.
- **Track who's engaging** for follow-up (high-signal commenters become candidate customers).

### On secondary channels

- Discord / Slack community has a "👀 we're trending" pinned message
- Twitter has a relevant founder post acknowledging traffic + adding context (not "thanks for the love")
- Email subscribers get a same-day note ("we got picked up, here's our take") if your list is engaged

---

## Hour 6-24 — capture

### Make the surge persistent

- **Pin the original post** on your X / founder accounts
- **Add a banner to landing page** referencing the moment ("As seen on HN ___ this week" — only if it's still recent)
- **Update the README** if it was the repo that went viral; add the top-comment FAQ

### Convert silently

- Your trial signups should be self-serve and frictionless. Now is NOT the time to add fields.
- Your "ask for the sale" should be downstream — let the surge users land, explore, succeed, then talk later.
- **Don't email everyone who signed up in the surge**. Mass blast kills the moment.

---

## Day 1-7 — quality follow-up

### Identify high-signal users from the surge

- Filter signup list for:
  - Email domain at your ICP-match company
  - GitHub username present + has recent AI-related repos
  - Engaged in product (logged in more than once in week 1)

- For each high-signal user:
  - Personal email from founder, NOT template
  - Specific reference to their context (their company, their project)
  - Offer: 15-minute call OR direct technical help in Discord/Slack
  - **Max 5 of these per week.** More dilutes quality.

### Content compound

- Within 7 days, ship 1 piece of follow-up content (blog, video, comparison) that builds on the surge topic
- Use the engagement data: top questions from the original thread → outline for the content
- This converts surge interest into evergreen funnel material

---

## Anti-patterns during viral moments

- **Auto-DM new signups**: kills the moment, marks you as spam
- **Adding lead-gen forms to landing**: you'll capture fewer trials and look needy
- **Pivoting messaging based on what one viral post said**: don't redirect strategy from a single signal
- **Burning out your team responding to every comment**: distribute the load; don't reply to drive-by criticisms
- **Promising features in reply threads**: you're stuck with them when the surge ends
- **Sales-y replies**: AI-native audiences smell this and downgrade you

---

## Day 7-30 — bank the trust

The actual value of a viral moment is the post-surge trust, not the surge itself.

- **3-week retention of surge cohort** is your real success metric — not signups in the first 24h
- **First 5 paid customers** from the surge become your reference cases
- **Top 3 surge-thread engagers** are candidates for advisor / champion roles
- **One detailed retrospective post** at week 4 — "What we learned shipping this in front of 50K people" — converts the moment into ongoing brand

---

## Infrastructure pre-prep checklist

Don't do this *during* a surge. Do it now so a surge can't break you.

- [ ] Landing page handles 100x traffic without going down
- [ ] Signup flow has no rate limits that kick in at viral volumes
- [ ] CDN cache is configured for static assets
- [ ] Database has read replicas if needed
- [ ] On-call rotation is defined; who responds at 3am PT
- [ ] Tweet-template-for-traffic-burst is pre-drafted
- [ ] Discord moderation bot is configured to handle floods
- [ ] Status page is current
- [ ] Email autoresponder doesn't sound like a robot

---

## Reference cases

- **Modal cold-start HN post** (2024 example): #2 on HN. Modal published methodology, founder replied for 6 hours straight, traffic spike compounded into 1000+ signups over 72h. Conversion: 4% to paid within 30 days.
- **Bolt.new viral demos** (2024-2025): user-generated screen-recordings on X compounded. Bolt did *nothing* original — they made every demo trivially shareable, and the network multiplied.
- **Lovable founder posts**: each ARR milestone tweet acts as a mini-viral moment; the consistent format compounds reach.

See `examples/our-flavor/research/02-gtm-motions-by-company.md` for source URLs.
