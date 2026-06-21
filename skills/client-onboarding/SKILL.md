---
name: client-onboarding
description: Discovery calls, client questionnaires, proposals, contracts, pricing, reviewing a contract a client sends to sign, and project kickoff for the user's freelance web design business. Use this skill when the user has a warm prospect ready for a discovery call, needs to send a questionnaire, write a proposal, draft or review a contract, discuss pricing, handle a red flag situation, or run a project kickoff. Trigger for any request involving qualifying a client, preparing for or running a discovery call, writing a proposal or quote, setting up an agreement, reviewing a client's own contract or MSA before signing, onboarding a new project, or transitioning a prospect into a paying client. Do NOT use this skill for cold outreach or finding prospects — that is client-acquisition. Do NOT use it for design, build, or post-launch and maintenance work — those are ux-research onward and post-launch.
---

# Client Onboarding Skill

**Pipeline position: Step 2 of 6**

---

## Session Start Protocol

**Only run this when the user says there is an active project.**

When activated, do the following based on your environment:

**If you are in Claude Code (VS Code terminal):**
Look for `project.md` at `~/Desktop/WebsiteProjects/[client-name]/project.md`. Read it in full. Confirm the ACQUISITION section is present and summarize what you know — business name, owner, contact, channel, scheduled call — so the user can confirm or correct before discovery call prep begins.

If `project.md` does not exist, `client-acquisition` skipped it. Create it at the standard path, prompt the user for the ACQUISITION fields, mark any unknowns as `[not captured]`, then proceed.

**If you are in claude.ai chat:**
Ask the user to open `project.md` in VS Code, select all, and paste it here. Once pasted, confirm what you know and proceed. If no file exists yet, ask the user for the key context fields manually, output a filled-in ACQUISITION block, and tell him to save it to:
`~/Desktop/WebsiteProjects/[client-name]/project.md`

**When complete (both environments):** After the agreement is signed and deposit confirmed paid, append this block to `project.md` — in Claude Code write it directly; in chat output it and tell the user to paste it in:

```markdown
### ONBOARDING
- Project type: [marketing site / small business / landing page / e-commerce / blog / redesign / SaaS]
- Primary conversion goal: [one sentence — call / form / booking / purchase]
- Deposit paid: [yes — $amount / date]
- Contract signed: [yes / date]
- Whose paper: [my agreement / client's contract — if client's, note anything negotiated]
- Timeline: [start date — target delivery date]
- Hard deadline: [date or none]
- Key notes: [anything unusual about scope, client, or constraints]
```

---

This skill picks up where `client-acquisition` leaves off — a warm prospect has agreed to talk. Its job is to understand the client's business deeply, qualify the fit, propose the right scope, get agreement, and set the project up for success before any design work begins.

**What this skill receives from `client-acquisition`:**
- Business name, owner name, contact info
- Which channel they responded on
- What resonated in the outreach
- Any context they shared about their site or needs
- Scheduled discovery call date and time
- Pre-outreach audit notes (what you found on their site/GBP)

**What this skill hands off to `ux-research`:**
- Completed client questionnaire (full or fast-track)
- Discovery call notes
- Signed agreement and paid deposit confirmed
- Project type classification
- Primary conversion goal
- Client's description of their audience and goals in their own words
- Any existing brand assets or content the client provided
- Timeline and any hard deadlines

---

## Pipeline Flow

```
client-acquisition → [prospect agrees to call]
        ↓
STEP 2A — Discovery Call
        ↓
STEP 2B — Send Questionnaire
        ↓
STEP 2C — Write and Send Proposal
        ↓
STEP 2D — Agreement and Deposit
        ↓
STEP 2E — Project Kickoff
        ↓
ux-research → [design begins]
```

---

## Step 2A — The Discovery Call

**Goal:** Understand the business, qualify the fit, and get enough information to write an accurate proposal. This is a conversation, not a sales pitch.

**Duration:** 20–30 minutes. Respect their time.

**Before the call:**
- Review your pre-outreach audit notes from `client-acquisition`
- Have the questionnaire open so you know what to fill in live
- Have your calendar open to confirm next steps immediately
- Have a simple notepad or doc to capture key answers

### Opening Script

```
"Thanks for taking the time — I'll keep this to around 20–25 minutes.

I want to start by learning about your business, because before I
can suggest anything I need to understand who you serve and what
you're trying to accomplish. Then I'll share what I found when I
looked at your current site, and we can figure out together whether
it makes sense to work together. Sound good?"
```

### Discovery Questions (ask conversationally — not rapid-fire)

**Business understanding (8–10 min):**
- "Tell me about the business — how long have you been running it and what do you offer?"
- "Who is your typical customer — who do you love working with?"
- "How do most of your customers find you right now?"
- "What does a good week look like? What's the main thing you want more of?"
- "What's your biggest challenge right now when it comes to getting new customers?"

**Website and goals (5–7 min):**
- "What would you want a website to do for you? What would success look like?"
- "Are there any websites — yours or competitors' — that you like or dislike?"
- "Do you have a logo, brand colors, or photos I could work with, or starting from scratch?"
- "Is there anyone else involved in this decision, or are you the main person I'd be working with?"

**Practical (3–5 min):**
- "Do you have a sense of your budget range? I ask because it helps me scope what's realistic."
- "Is there a date you're working toward?"
- "Would you need to update the content yourself after launch, or are you fine reaching out for changes?"

### Closing the Call

```
"This has been really helpful — I have a clear picture of what
you're looking for. Based on what you've told me, I think a website
could genuinely help you [restate their main goal in their words].

What I'll do is send you a short questionnaire to fill out — it
takes about 10–15 minutes and helps me make sure everything I
design is built around your actual business. Then I'll put together
a proposal with what I'd recommend, roughly what it would cost,
and the timeline. I'll have that to you within 48 hours.

Does that work? And if you have any questions before then, feel
free to call or text me at [your phone]."
```

### What to Listen For

- **Enthusiasm** — do they light up about their business? Passionate clients are better clients.
- **Clarity** — can they describe their customers and goals? Vague = scope creep later.
- **Decision authority** — are they the one who says yes, or do they need to "check with someone"?
- **Budget signals** — reluctance to give any range is a yellow flag, not a dealbreaker.
- **Respect for your time** — did they show up? Did they engage?

Read `references/red-flags.md` for signals that warrant extra caution before proceeding.

---

## Step 2B — The Questionnaire

Send within 2 hours of the discovery call while momentum is high.

**Intro message to send with the questionnaire:**

```
Hi [Name],

Great talking with you earlier. As promised, here's a short
questionnaire — it takes about 10–15 minutes and helps me make
sure the site I design is built around your actual business and
customers.

The more detail you can share, the better the result. Clients who
fill this out fully tend to be happier with the first draft because
I'm not guessing at anything.

[Link to questionnaire or paste below]

I'll have your proposal ready within 48 hours of receiving this.

[Your Name]
[your phone]
```

Read `references/questionnaires.md` for the full 44-question questionnaire and the 14-question fast-track version.

**Which version to send:**
- **Full questionnaire** — always encourage this. Better information = better design = fewer revisions.
- **Fast-track** — offer as an option for simple projects (landing page, 3–4 page small business site) or clients who seem time-pressed. Note that additional check-ins may be needed.

---

## Step 2C — The Proposal

Send within 48 hours of receiving the completed questionnaire. While the conversation is fresh.

**Proposal email template:**

```
Subject: Website Proposal — [Business Name]

Hi [Name],

Great talking with you [day]. Based on our conversation and your
questionnaire, here's what I'm proposing:

PROJECT OVERVIEW
[1–2 sentences: what you're building and why it fits their goals]

SCOPE
Pages: [list each page]
Key features: [contact form, gallery, booking integration, etc.]
Includes: Mobile-responsive design, SEO setup, accessibility,
          copy guidance, and [X] rounds of revisions.
Not included: [be specific — ongoing maintenance, copywriting,
              photography, future pages — prevents scope creep]

INVESTMENT
[Project total] — 50% deposit ($[amount]) to begin,
50% ($[amount]) on delivery before launch.

TIMELINE
Start: [date, contingent on deposit + questionnaire received]
Milestone 1: Wireframes and design direction — [X] weeks
Milestone 2: Design review and approval — [X] weeks
Milestone 3: Development, testing, and launch — [X] weeks
Total: approximately [X] weeks from deposit to live site

WHAT I NEED FROM YOU TO BEGIN
- Completed questionnaire (if not already done)
- Brand assets: logo file (SVG or PNG), colors, fonts if you have them
- Any photos you want to use
- 50% deposit

NEXT STEPS
If this looks right, reply to confirm and I'll send over a simple
one-page agreement and deposit invoice. We can be started within
[X] days.

If you have questions or want to adjust scope, happy to talk —
just reply or call me at [your phone].

[Your Name]
[your email]
```

### Make It a Document for Bigger Jobs

The email template above is right for most local projects. For [a higher-cost metro] clients, projects over ~$1,500, or anyone more formal, send the proposal as a polished PDF instead — it reads as more professional and is harder to skim past. Use the `pdf` or `docx` skill to generate it: same content, laid out cleanly with your name, a simple header, and scope / investment / timeline as clear sections. The agreement in Step 2D can be sent the same way.

### Write Like You, Not Like AI

Your proposals win on sounding like a real local person who actually looked at their business — not a generated template. If you draft with AI, strip the tells before sending. Avoid: *leverage, delve, robust, seamless, elevate, unlock, tapestry, navigate (as a metaphor), foster, holistic, "in today's fast-paced world," "look no further," "dive in," game-changer, synergy.* Cut empty hype and run-ons. Read it out loud — if you wouldn't say it to the owner across a counter, rewrite it plainer.

### Pricing Reference

Adjust based on complexity, client budget signals, and how much research/content work is involved.

| Project type | Scope | Starting range | Typical stack | Ongoing client cost |
|---|---|---|---|---|
| Simple small business site | 3–5 pages, contact form, no CMS | $500–$900 | Vanilla HTML/CSS/JS | ~$12/year (domain only) |
| Standard small business site | 5–8 pages, gallery, CMS setup | $900–$1,800 | Vanilla + Decap CMS | ~$12/year (domain only) |
| E-commerce (small catalog) | Up to 20 products, Snipcart/Shopify | $1,200–$2,500 | Shopify or Snipcart | $29–$299/month (Shopify plan) |
| Landing page | 1 page, conversion-focused | $300–$600 | Vanilla HTML/CSS/JS | ~$12/year (domain only) |
| Blog / content site | With CMS setup | $900–$1,800 | Astro or Vanilla + Decap | ~$12/year (domain only) |
| Redesign / refresh | See note below | Same ranges as new build | Audit first — see note | Same as equivalent new build |

**Redesign note:** Always audit the existing codebase before scoping. If the existing site is on Wix, Squarespace, or a template builder, treat it as a new build — you're not inheriting the code, you're replacing it. If it's on a custom stack, assess whether the code is worth extending or faster to rebuild. Never commit to a redesign price before seeing what you're working with.

**[a higher-cost metro] clients:** Add 20–35% — higher budgets but also higher expectations for responsiveness and polish.

**Portfolio discount:** Early in your career, it is acceptable to offer a reduced rate in exchange for full creative control, a detailed case study, and a Google review. Define scope tightly and get it in writing.

**Raise prices after:** Every 3–5 completed projects with documented case studies. Increase floors by 30–50%. After 10+ projects, revisit based on market feedback.

**Plant the seed on maintenance:** During the proposal, one sentence is enough — "I also offer a monthly maintenance plan after launch if you want someone to keep the site updated and running." Don't sell it now, just make it expected. Full details live in `post-launch`.

---

## Step 2D — Agreement and Deposit

Never start work without both. No exceptions.

### What the Agreement Must Cover

Send a simple one-page written agreement — not a lawyer-drafted contract, but something in writing covering:

1. **Scope** — exact pages, features, and what is explicitly NOT included
2. **Payment terms** — 50% deposit to begin, 50% on delivery; late fee after 14 days
3. **Revision rounds** — number included (recommend 2) and what counts as a revision vs new request
4. **Timeline** — milestone dates and what happens if client delays
5. **IP ownership** — transfers to client only upon receipt of final payment
6. **Kill fee** — if client cancels mid-project, they owe for work completed + 25% of remaining balance
7. **Change order process** — how additional work outside scope is handled and billed
8. **Client responsibilities** — what they provide and by when; work pauses after 14 days of no response

Read `references/contract-clauses.md` for exact language for each clause.

### If the Client Sends You Their Own Contract

Most local clients won't have one — your agreement is the default. But more established clients, agencies, and [a higher-cost metro] companies sometimes send their own contractor agreement, MSA, or SOW to sign. Don't sign it as-is. Read it from your side first and watch for the clauses that quietly work against a freelancer — IP that transfers before you're paid, open-ended revisions, net-60 payment, no kill fee, broad indemnification, non-competes, and clauses that bar you from showing the work in your portfolio (which your case studies depend on).

Read `references/reviewing-a-client-contract.md` for the full list of traps, plain-English explanations of why each matters, what to ask for instead, and when a deal is big or unusual enough to warrant an actual lawyer. This is practical guidance, not legal advice.

### Collecting the Deposit

**Recommended payment methods:**
- **Zelle** — free, instant, best for most clients. Send to [your phone] or [your email]
- **PayPal** — widely trusted, 3.49% + $0.49 fee on business payments; absorb or pass through
- **Venmo** — fine for smaller amounts; has a business option
- **Wave** — send a professional invoice with a pay button; client pays by card or bank transfer

**Invoice must include:** your name and contact, client name, invoice number, date, itemized description, total, payment method instructions, and due date (net 7 for deposits).

**Do not begin work until the deposit clears.** If a client delays sending the deposit for more than 7 days after agreeing, follow up once. If they delay again, the spot is no longer held.

---

## Step 2E — Project Kickoff Checklist

Run through this before handing off to `ux-research`. Everything on this list should be confirmed before research and design begins.

### Information
- [ ] Client questionnaire fully completed (full or fast-track)
- [ ] Discovery call notes documented
- [ ] Project type classified (marketing site / small business / SaaS / e-commerce / landing page / blog / redesign)
- [ ] Primary conversion goal confirmed (call / form / booking / purchase)
- [ ] Target audience described in the client's own words
- [ ] Timeline and hard deadlines noted

### Assets
- [ ] Logo file received (SVG or PNG — not a JPG screenshot)
- [ ] Brand colors noted (hex codes or "none yet")
- [ ] Fonts noted (or "none — your choice")
- [ ] Photos received or stock photo plan agreed
- [ ] Existing content received (or "needs to be written" noted in scope)

### Technical
- [ ] Domain name situation confirmed (have one / need one / which registrar)
- [ ] Hosting situation confirmed (Netlify free / Vercel Pro / existing host)
- [ ] CMS needed confirmed (yes/no/which)
- [ ] Third-party integrations identified (booking tools, CRM, payment processor)
- [ ] Google Business Profile situation noted (for local SEO)

### Admin
- [ ] Signed agreement received (email confirmation counts)
- [ ] 50% deposit confirmed and cleared
- [ ] Communication channel agreed (email / text — pick one and stick to it)
- [ ] Milestone dates documented and shared with client

### Hand Off to ux-research
Once the above is complete, pass the following to `ux-research` as starting context:
- Completed questionnaire answers
- Discovery call notes
- Project type and primary conversion goal
- Any existing research, brand assets, or content
- Client's description of their audience and goals in their own words
- Timeline

---

## Reference Files

| File | Read when... |
|---|---|
| `references/questionnaires.md` | Sending the questionnaire — full 44-question and fast-track 14-question versions with example answers |
| `references/contract-clauses.md` | Writing your own agreement — exact clause language for each clause |
| `references/reviewing-a-client-contract.md` | A client sends you their own contract, MSA, or SOW to sign — traps to flag and what to ask for |
| `references/red-flags.md` | Client shows warning signs during discovery — how to respond |
