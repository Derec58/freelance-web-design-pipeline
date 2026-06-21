---
name: post-launch
description: Post-launch business operations for Dereck's freelance web design practice — final invoicing, payment collection, recurring revenue packages, referral systems, portfolio building, case studies, expense and tax tracking, business tools, conflict resolution, and ongoing client management. Use this skill when Dereck needs to send a final invoice, follow up on payment, set up a maintenance plan, ask for a referral, write a case study, track business expenses, handle a difficult client situation, or manage any aspect of running the business after a project ships. Trigger for any request involving money, invoicing, recurring revenue, referrals, case studies, or post-project work. Do NOT use this skill for finding clients or cold outreach — that is client-acquisition. Do NOT use it for the project work itself — discovery, research, design, or build — those are client-onboarding through web-development.
---

# Post-Launch Skill

**Pipeline position: Step 6 of 6**

---

## Session Start Protocol

**Only run this when Dereck says there is an active project.**

When activated, do the following based on your environment:

**If you are in Claude Code (VS Code terminal):**
Look for `project.md` at `/Users/dereckvillagrana/Desktop/WebsiteProjects/[client-name]/project.md`. Read it in full. Confirm which prior sections are present (ACQUISITION, ONBOARDING, RESEARCH, DESIGN, DEVELOPMENT) and summarize what you know — business name, project type, final invoice amount, delivery status — so Dereck can confirm or correct before closing out.

If `project.md` does not exist, create it at the standard path using the canonical template. Prompt Dereck for missing context and mark unknowns as `[not captured]`.

**If you are in claude.ai chat:**
Ask Dereck to open `project.md` in VS Code, select all, and paste it here. Once pasted, confirm what you know and proceed. If no file exists yet, ask Dereck for the key context — business name, project type, delivery status, final invoice amount — then proceed.

In both environments: proceed to the Post-Delivery Sequence below. Do not ask for information already in project.md.

**When complete (both environments):** After the post-delivery sequence is finished — final invoice sent, maintenance plan offered, referral asked — append this block — in Claude Code write it directly; in chat output it and tell Dereck to paste it in:

```markdown
### BUSINESS
- Final invoice: [sent / paid — $amount / date]
- Maintenance plan: [offered / accepted $X/month / declined]
- Google review: [requested / received]
- Referral ask: [yes / no / referral received from]
- Case study: [written / pending / published at URL]
```

---

This skill activates in two contexts:

1. **Post-delivery** — after web-development hands off a completed site. The project is done, the client has received the work, and now the business side closes out: final invoice, file transfer, maintenance plan offer, referral ask, Google review request, case study.

2. **Ongoing** — any time a business question comes up outside the project pipeline: how to handle a late payment, how to price a new project, how to write a case study, how to set up recurring revenue, what to do when a client goes silent.

**What this skill receives from web-development:**
- Confirmation that the site has been delivered and client has received it
- Live URL or delivery package
- README.md delivered to client
- Project summary (type, scope, outcome)
- Design decisions summary
- Pre-handoff checklist — all items passed
- Final invoice amount (50% remaining balance)
- Any post-launch issues or client feedback

---

## Dereck's Business Info

- Name: Dereck Villagrana
- Location: Manteca, CA
- Email: dereck.villagrana58@gmail.com
- Phone: (408) 759-0778
- Portfolio: dereckvilla.design (in progress — update once live)
- Payment: Zelle to (408) 759-0778 or dereck.villagrana58@gmail.com

---

## Post-Delivery Sequence

Run this after every project delivery. Steps in order.

### 1. Send the Final Invoice

Send immediately upon delivery — before transferring files or making the site live.

```
Subject: Final Invoice — [Business Name] Website

Hi [Name],

The site is ready! [1 sentence describing what was delivered.]

Invoice #[XXX]
Amount due: $[final amount]
Due: within 7 days

Payment via:
  Zelle: (408) 759-0778
  PayPal: dereck.villagrana58@gmail.com

Once payment clears I'll [transfer files / push live / hand over
access] — should be same day.

Dereck
(408) 759-0778
```

Do not transfer files or go live until payment clears. IP transfers upon final payment per the agreement.

### 2. Deliver the Package

Once payment is confirmed, transfer files and send:

```
Hi [Name] — payment received, thank you!

[Your site is now live at [URL] / Here are your project files.]

Your README.md has instructions for everything. Give it a look and
let me know if you spot anything that needs adjusting — the 14-day
warranty starts today so any bugs on my end get fixed at no charge.

Dereck
```

### 3. Offer the Maintenance Plan

Send 24–48 hours after delivery:

```
Hi [Name],

How's the site feeling now that you've had a day with it?

I offer a monthly maintenance plan for clients who want peace of
mind that their site stays working and up to date:

BASIC — $75/month
  Monthly site check, minor content updates (up to 1 hour),
  browser/mobile compatibility check, monthly summary email.

STANDARD — $125/month
  Everything above plus up to 2 hours of content changes/month
  and priority response.

Happy to set it up if it sounds useful — just reply and I'll
send an invoice for the first month.

Dereck
```

Read references/recurring-revenue.md for the full recurring revenue guide — including the monthly maintenance report template that keeps retainer clients renewing.

### 4. Ask for a Google Review

Send 3–5 days after delivery. **Combine this with the referral ask in one message** — two separate emails feels like spam. One well-timed message is more respectful and gets better response rates.

```
Hi [Name],

Two quick things now that the site is live:

First — would you be willing to leave a Google review? Even a
sentence or two makes a real difference for other local businesses
finding me.

Here's the direct link: [Google Business Profile review link]

Second — if you know any other business owners who might need a
website or a refresh, I'd really appreciate an introduction. A
simple "you should talk to Dereck" goes a long way.

Thanks either way — it was a great project to work on.

Dereck
(408) 759-0778
```

### 5. Ask for Referrals

Handled in the combined message above (step 4). If the client didn't respond to that message and you want to follow up on referrals specifically, wait at least 2 weeks before sending a standalone ask.

### 6. Add to Portfolio List

After every project, document:
- Business name and type
- Project type and key features
- Outcome or result if measurable
- Screenshots taken
- Client quote or review saved

Read references/portfolio-and-growth.md for the case study template.

---

## Invoicing and Payment

**Tools:**
- Wave (free) — invoicing, payment tracking, accounting. Recommended start.
- Bonsai (~$17/month) — contracts + invoices in one place. Upgrade when volume warrants.
- Zelle — free, instant, best for most clients
- PayPal — 3.49% + $0.49 fee; widely trusted
- Cash/check — always issue a written invoice; all income is taxable

**Late payment escalation:**

Day 7 (friendly):
```
"Hi [Name] — just a friendly reminder that invoice #[X] for $[amount]
was due [date]. Let me know if you have any questions."
```

Day 14 (firm):
```
"Invoice #[X] is now 14 days past due. A late fee of $[amount] has
been added per our agreement. Please arrange payment within 48 hours."
```

Day 21 (final demand):
```
"This is formal notice that $[amount] is owed under our agreement
dated [date]. Payment required within 7 days or I'll file in small
claims court."
```

Small claims court in California handles up to $12,500. Filing fee: $30–$75. No lawyer needed.

**Tracking expenses and taxes:**

You're a 1099 contractor, so every legitimate business expense lowers your taxable income — log them as you go, not in April. Common deductions for this work: software subscriptions (Figma, Adobe, hosting, domains, Claude), equipment (computer, camera, peripherals), the home-office portion of rent/utilities, mileage to client meetings (track at the current IRS rate), and a share of phone and internet. Wave tracks income and expenses in one place — snap a photo of each receipt as you pay. Set aside roughly 25–30% of profit for taxes, and look into quarterly estimated payments to avoid an underpayment penalty. This is general guidance, not tax advice — a one-time session with a tax pro who knows self-employment usually pays for itself. Full detail in references/invoicing-and-payment.md.

---

## Recurring Revenue

Read references/recurring-revenue.md for full pricing, scripts, and setup for:
- Monthly maintenance plans ($75–$250/month) — offer after every project
- Hosting reselling ($25–$35/month)
- Content updates retainer ($100–$200/month)
- SEO retainer ($150–$300/month — only when comfortable with SEO basics)

The math: 10 clients at $75/month = $750/month guaranteed before finding any new work. This eliminates feast-or-famine.

**Note:** The seed for the maintenance plan is planted at proposal time in `client-onboarding` — one sentence in the proposal makes the post-delivery offer feel expected rather than like an upsell. If it wasn't mentioned during onboarding, lead the pitch with "I mentioned this at the start..." anyway — clients rarely remember.

---

## Portfolio and Case Studies

Read references/portfolio-and-growth.md for the full strategy, case study template, Claude prompt, image capture tools, first 3 projects strategy, referral system, business tools, and pricing evolution.

---

## When Things Go Wrong

**Client goes silent mid-project:**
Wait 7 days, then follow up. After another 7 days with no response, pause the project and send a note that work is on hold with a potential $150 restart fee after 30 days.

**Client hates the first design:**
Ask for specific feedback. Reference approved wireframes and direction. If they want a fundamentally different direction, that is a change order, not a free redo.

**Scope creep request:**
```
"Happy to add that — it's outside our original scope so I'll send
a quick change order with the cost before I start."
```
Never say "I can't." Always say "I can — here's what it costs."

**Client disputes a charge:**
Pull the signed agreement, invoices, and delivery confirmation. Submit as evidence to the payment platform immediately — they have 7–10 day windows.

**You made a mistake:**
Own it quickly. Fix within 24 hours if critical. Apologize once. Move forward. No refunds for small bugs that get fixed promptly.

---

## Business Tools

- Invoicing: Wave → Bonsai when volume grows
- Contracts: Email for small projects; Bonsai/HelloSign for larger
- Project management: Notion — one page per active client
- File management: Google Drive — one folder per client
- Time tracking: Toggl Track — know if projects are actually profitable
- Communication: One channel per client, agreed upfront

Professional email: Gmail works now. When you have a portfolio domain, upgrade to dereck@[yourdomain].com via Google Workspace ($6/month) or Zoho Mail (free).

Pricing progression:
- Now: starting rates from client-onboarding
- After 3–5 case studies: raise floors 30–50%
- After 10+ projects: revisit based on market demand

---

## Reference Files

| File | Read when... |
|---|---|
| references/recurring-revenue.md | Setting up maintenance plans, hosting reselling, content retainers, SEO retainers |
| references/portfolio-and-growth.md | Case studies, image capture, portfolio hosting, first 3 projects, referral system, business tools, pricing evolution |
| references/invoicing-and-payment.md | Invoice templates, payment tracking, late payment handling |
