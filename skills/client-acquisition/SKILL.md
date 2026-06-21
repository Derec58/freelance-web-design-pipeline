---
name: client-acquisition
description: Cold outreach, prospect research, lead qualification, and lead generation for Dereck's freelance web design business. Use this skill when Dereck wants to find potential clients, research a prospect before reaching out, write a cold email or DM, prepare for a cold call, plan an in-person visit, follow up with a non-responding lead, qualify whether a prospect is worth pursuing, or handle objections during outreach. Trigger for any request involving finding clients, writing outreach messages, researching a business before contacting them, qualifying a lead, or preparing outreach scripts for any channel. Do NOT use this skill once a prospect has agreed to a discovery call — that is client-onboarding. Do NOT use it for work with existing or signed clients — that is post-launch.
---

# Client Acquisition Skill

**Pipeline position: Step 1 of 6**

---

## Session Start Protocol

**Only run this when Dereck says there is an active project.**

This is the first skill in the pipeline, so there is no prior `project.md` to read. When Dereck confirms a prospect has agreed to a call and the project is moving forward, do the following:

**If you're in Claude Code (VS Code terminal):**

Ask Dereck for the client name, then create the project folder and `project.md` at:
`/Users/dereckvillagrana/Desktop/WebsiteProjects/[client-name]/project.md`

Fill in the ACQUISITION section from what Dereck has shared. Prompt for any fields not yet mentioned:

```markdown
# Project: [Business Name]
Last updated: [date]

### ACQUISITION
- Business name:
- Owner name:
- Contact info:
- Channel: [email / DM / cold call / in-person / referral]
- What got the response: [what you said or sent that worked]
- Context they gave: [anything about their site or needs]
- Qualification / fit: [green / yellow — Need, Budget signal, Authority, Timeline notes]
- Social proof used: [which example you referenced, if any]
- Scheduled call: [date and time]
```

Show Dereck the completed block, confirm it looks right, and tell him the next step is `client-onboarding`.

**If you're in claude.ai chat:**

Ask Dereck to share what he knows about the prospect — business name, owner, how they responded, what was said, when the call is scheduled. Fill in the ACQUISITION block above from what he shares, output it cleanly, and tell him to copy it into a new file at:
`/Users/dereckvillagrana/Desktop/WebsiteProjects/[client-name]/project.md`

He can create that file manually in VS Code or via terminal: `mkdir -p ~/Desktop/WebsiteProjects/[client-name] && touch ~/Desktop/WebsiteProjects/[client-name]/project.md`

---

This is the first step of the freelance pipeline. Its job is to identify the right prospects, research them before reaching out, and make first contact across any channel. This skill ends when a prospect agrees to a discovery call or meeting.

**What this skill receives:** Nothing — this is where every new project begins.

**What this skill hands off to `client-onboarding`:** A warm prospect who has agreed to talk. Before moving on, document:
- Business name, owner name, contact info
- Which channel they responded on
- What resonated in the outreach — what you said that got a response
- Any context they gave about their current site or needs
- Qualification read — green or yellow, and why (so onboarding knows how strong this lead is)
- Which social-proof example you referenced, if any
- Scheduled call time and date
- Pre-outreach audit notes (what you found on their site/GBP)

---

## Who You Are

Dereck Villagrana — solo freelance web designer based in Manteca, CA. You design and build custom websites for local businesses and small companies in the Central Valley (Manteca, Stockton, Tracy, Modesto) and Bay Area (San Jose and surrounding areas).

**Contact:**
- Email: dereck.villagrana58@gmail.com
- Phone: (408) 759-0778
- Portfolio: dereckvilla.design (in progress — update scripts once live)

---

## Core Value Propositions

Use the most relevant one per prospect. Never lead with all of them — pick the one that fits their situation.

| Situation | Lead with |
|---|---|
| They have a bad/broken site | "That's probably costing you customers" |
| They have no site | "You're invisible to people searching on Google" |
| They're on Wix/Squarespace | "No monthly platform fees — you own the code" |
| They want local search visibility | "Built to rank on Google for [city] + [service]" |
| They're skeptical of remote designers | "I'm local — I can meet you in person" |

**The local advantage** — be explicit about this. You can visit their business, photograph their real work, and meet face to face. Remote designers structurally cannot do this. Lead with it when competing against cheaper online options.

---

## Using Social Proof

Nothing converts a skeptical local owner like proof you've done this for someone like them. Once you have even one completed site, every script below gets stronger.

- **In outreach:** add a single line — "I recently built [similar local business] a new site, and now [specific result, e.g. 'they show up on the first page for plumber + Manteca']." One sentence. Specifics beat adjectives.
- **On a call or in person:** pull the live site up on your phone. A real, working example you built locally beats any portfolio page or pitch.
- **Your portfolio:** point to dereckvilla.design once it's live. Until you have local case studies, lead with your strongest existing work and be honest that it's recent.
- **Anti-pattern:** never oversell or invent results. One true, specific example beats three vague claims — and a local owner will find out if you stretched the truth.

**Your current examples — keep this list current as you ship work:**
- [Add each completed or representative project: business, what you built, the result]

This list is the raw material for the case studies you'll build in `post-launch`.

---

## Who to Target

**Ideal prospect profile:**
- Small local business, owner-operated
- Has no website OR has an outdated/broken/mobile-unfriendly one
- Active and has customers (not a startup with no revenue)
- Relies on local customers finding them online

**Highest conversion likelihood:**
- Plumbers, electricians, HVAC, roofers
- Landscapers, gardeners, lawn care
- Tile installers, flooring, painters, contractors
- Auto repair, body shops
- Cleaning services
- Restaurants, food trucks, bakeries

**Good targets (slightly longer sales cycle):**
- Salons, barbers, nail techs
- Photographers, personal trainers, gyms
- Pet groomers, childcare, tutoring
- Local retail shops

**Strong prospect signals:**
- Active Google Business Profile but no website (or dead URL)
- Active Instagram/Facebook but no professional site
- Has reviews but site is Wix from 2015
- Competitors have better websites
- Business clearly busy and established (3+ years, good reviews)

---

## How to Find Prospects

### The Pre-Outreach Audit (always do this first)

Before contacting anyone, spend 5 minutes on their current situation. This is what makes your message specific and credible instead of generic.

**Check:**
1. Do they have a website? (Google their business name)
2. Does it load on mobile? (Resize your browser or use Chrome DevTools)
3. Does it load fast? (pagespeed.web.dev — paste their URL)
4. Do they rank for [service] + [city]? (Search it yourself)
5. Is their Google Business Profile complete?
6. Note 2–3 specific issues — these become your opening line

**Make a note:** Business name, owner name (from GBP or website), website URL or "none," 2–3 specific observations, best contact channel.

### Where to Find Prospects
- **Google Maps:** Search "[trade] near Manteca CA" or "[trade] near San Jose CA" — filter by no website or poor website
- **Yelp:** Same search — many list on Yelp but have no site
- **Instagram:** Local hashtags — #mantecabusiness #centralvalleybusiness #sanjosesmallbusiness #stocktonbusiness #traceybusiness
- **Facebook:** Local business groups (Central Valley Business Network, etc.)
- **Drive around:** Service vehicles, storefronts, yard signs in Manteca, Tracy, Stockton, Modesto
- **Chamber of Commerce directories:** Manteca, Tracy, Stockton, San Jose
- **Nextdoor:** Business section
- **LinkedIn:** Local business search

### Volume Reality Check
To land 1 client, expect to contact roughly:
- 20–40 cold emails
- 15–25 cold calls
- 10–20 DMs
- 5–10 in-person visits

These improve significantly after your first 2–3 case studies are built.

---

## Cold Outreach Scripts

Read `references/outreach-scripts.md` for all channel scripts in full. Summary rules:

- **Lead with the observation, not the pitch** — "I noticed X" beats "I build websites"
- **Short** — 3–5 sentences max for first contact
- **One CTA** — ask for a 15-minute call, nothing more
- **No fake urgency** — never say "limited spots available" unless true
- **Personalize** — the specific observation is everything
- **Cold email law (CAN-SPAM):** use a truthful subject line, identify yourself as a real person, and give an easy opt-out (a simple "reply and tell me to stop and I won't reach out again" is enough). You already avoid fake urgency — this keeps you clean if you ever scale up volume.

For pushback during or after outreach — price, "my nephew can do it," "I get business from word of mouth," and the rest — see `references/objection-playbook.md`.

### Quick Reference — Opening Lines by Situation

**They have a site with mobile issues:**
> "I came across [Business Name] while looking at [service] businesses in [city] — great reviews. I noticed your site doesn't load well on mobile. For a business with your reputation, that's probably costing you customers who find you on their phone and leave."

**They have no website:**
> "I was searching for [service] in [city] and found your Google listing — solid reviews. But I noticed you don't have a website. Most people searching on their phone expect to find a site before calling."

**They don't rank on Google:**
> "I searched '[service] in [city]' and your business didn't come up — even though your reviews suggest you should be near the top. That's worth fixing."

**Bay Area / professional tone:**
> "I came across [Business Name] while researching [industry] businesses in [city]. Your work looks excellent. I wanted to flag that your website [specific observation] — in a competitive market like [city], that quietly costs you inquiries."

---

## Follow-Up Sequences

**After no response to first outreach:**

Follow up exactly once, 4–5 days later. Keep it shorter than the original.

**Email follow-up:**
```
Subject: Re: [original subject]

Hi [Name] — just making sure this didn't get buried.
Happy to share what I found if you're open to a quick look.

Dereck
(408) 759-0778
```

**After two contacts with no response:** Move on. Archive and revisit in 3–6 months.

**Phone:** Leave max 2 voicemails. If no callback, switch to email or in-person.

---

## When They Respond

**They say yes to a call:**
Book it immediately — have your calendar open before you reach out. Confirm the time, send a brief calendar invite or text confirmation. Then hand off to `client-onboarding`.

**They ask what it costs:**
> "It really depends on what you need — every project is different. That's why I'd love a quick 15-minute call first, just to understand your business. Then I can give you a realistic sense of what makes sense."

**They say they already have a website:**
> "Totally understand. Out of curiosity — are you happy with how it's performing? A lot of businesses I talk to have a site but it's not bringing in new customers. If you're all set, no worries — but I'd love to take a quick look and share what I find."

**They say not interested:**
> "No problem — I appreciate you taking the call. If you ever want a second opinion on your web presence, feel free to reach out."
Hang up or close the message. Never push.

---

## Qualifying the Lead

A discovery call is real time and energy. Before you book one, run a 30-second gut-check. You're not interrogating the prospect — you're reading signals from the conversation and your pre-outreach audit. This is BANT, in freelancer terms:

- **Need** — Is there a real problem? No site, broken site, invisible on Google. You've usually confirmed this in your audit. This is your strongest signal.
- **Budget** — Any sign they can pay? Established 3+ years, visibly busy, good reviews, already spends on marketing (wrapped trucks, ads, signage, paid listings). You're not asking their budget — you're inferring whether one plausibly exists.
- **Authority** — Are you talking to the owner or decision-maker? Owner-operated is your ICP for a reason. If you're talking to an employee, your goal is to get to the owner.
- **Timeline** — Any trigger? New location, rebrand, busy season approaching, a competitor that just launched a site. No urgency is fine — it just means a longer cycle, not a dead lead.

**Green light** — Need and Authority confirmed, plus at least one budget signal. Book the call.

**Yellow** — Real need but no budget signals yet, or you're not talking to the owner. Still worth a short call; keep your expectations and prep light.

**Red flags — politely disqualify or move to the bottom of the list:**
- Wants it free, "for exposure," or on a revenue-share
- Leads with "my nephew can do it" and clearly just wants free advice
- Not the decision-maker and won't connect you to one
- Unrealistic scope for the money ("a full online store for $200")
- Rude or disrespectful on first contact — how someone treats you before paying is how they'll treat you after

Note your read (green/yellow and why) in the `project.md` ACQUISITION block so `client-onboarding` knows how strong the lead is walking into the call. For the scripts that handle each red-flag objection without burning the bridge, see `references/objection-playbook.md`.

---

## Pipeline Handoff Checklist

Before moving to `client-onboarding`, confirm you have:

- [ ] Business name and type
- [ ] Owner's name
- [ ] Contact info (phone, email, or social handle)
- [ ] How they responded and on which channel
- [ ] What specific issue you mentioned that resonated
- [ ] Any context they shared about their current site or needs
- [ ] Your qualification read (green/yellow and why)
- [ ] Scheduled discovery call date and time
- [ ] Your pre-outreach audit notes (what you found on their site/GBP)

Hand all of this to `client-onboarding` as the starting context for the discovery call.

---

## Reference Files

| File | Read when... |
|---|---|
| `references/outreach-scripts.md` | Writing any outreach message — full scripts for all 5 channels |
| `references/objection-playbook.md` | A prospect pushes back, hesitates, or raises a concern on any channel |
