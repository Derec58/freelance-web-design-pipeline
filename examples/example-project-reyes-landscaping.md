# Example Project — Reyes Landscaping (Worked Example)

> A **fictional, fully completed** project run through all six stages of the pipeline,
> start to finish. Use it to see what a real `project.md` looks like once every stage
> has filled in its block, plus the key artifact each stage produces.
>
> **Nothing here is real** — Reyes Landscaping, its owner, contact details, and pricing
> are invented for illustration. Code is intentionally left as `enter code here`
> placeholders; this file is about the *shape* of a finished project, not the build itself.

---

## Part 1 — The completed `project.md`

This is the handoff file after the project is delivered and closed. Each stage appended its block as it finished.

```markdown
# Project: Reyes Landscaping
_Started: 2026-06-03 · Status: delivered_

### ACQUISITION
- Business name: Reyes Landscaping
- Owner name: Miguel Reyes
- Contact info: (209) 555-0142 · miguel@reyeslandscaping.example
- Channel: in-person (stopped by during a job in my neighborhood)
- What got the response: I mentioned I couldn't find them on Google when a neighbor asked me for a referral — they realized they were losing word-of-mouth leads
- Context they gave: 8 years in business, no website, all work from referrals and a half-filled Google listing; wants more steady residential clients
- Qualification / fit: GREEN — Need (no site, invisible online), Budget signal (wrapped trucks, 8 yrs established, 40+ Google reviews), Authority (owner), Timeline (wants it before peak summer season)
- Social proof used: showed him the live site I built for a local barber shop on my phone
- Scheduled call: Mon, June 1, 2026, 10:00 AM (phone)

### ONBOARDING
- Project type: small-business marketing site (5 pages: Home, Services, Gallery, About, Contact)
- Primary conversion goal: phone calls and quote-request form submissions
- Deposit paid: yes — $900 (50%) via Zelle, 2026-06-03
- Contract signed: yes — 2026-06-02
- Whose paper: my agreement (standard small-project contract)
- Timeline: 2026-06-03 — 2026-06-24 (≈3 weeks)
- Hard deadline: soft — wants it live before the July 4 weekend
- Key notes: total project $1,800 ($900 deposit / $900 on delivery). Client has ~30 phone photos of past jobs but no logo files. No CMS — client will contact me for content changes.

### RESEARCH
- Mode: B — some research (client questionnaire + 40 Google reviews + 3 competitor sites)
- Personas: "Busy Homeowner Hannah" (35–55, dual-income, wants a reliable pro and her weekends back); "Property Manager Paul" (manages 6 rental units, wants one dependable vendor)
- Anti-personas: "Bargain Bill" — price-only shopper hunting the cheapest one-time mow; site does NOT lead with price or "cheapest in town"
- JTBD statements: "When my yard is overgrown and I'm out of time, I want to quickly find a trustworthy local pro so I can get it handled without vetting five companies."
- Competitive analysis: done — 3 local competitors; two have dated sites, one has none. Gap: none clearly show real project photos or a fast quote path on mobile.
- Confirmed design requirements: mobile-first; click-to-call in the header; short quote form above the fold; gallery of real work; trust signals (years in business, review count, service area); fast load on a phone
- Key insight for design: trust + speed-to-contact win this market, not price — lead with proof of real local work and make calling/quoting one tap away.

### DESIGN
- Visual direction chosen: "Grounded & Natural" — earthy, warm, photo-forward; conveys established + trustworthy
- Color tokens: primary oklch(0.45 0.09 150) deep green · secondary oklch(0.52 0.07 65) warm bark · accent oklch(0.80 0.15 95) golden highlight
- Typography: display Fraunces (warm serif) / body Inter
- Key layout decisions: full-width hero with a real job photo + click-to-call and "Get a Free Quote" CTAs; services as scannable cards; gallery grid of real work; reviews band above the footer
- Wireframes: done — described for all 5 pages; mobile + desktop
- Design system output: tokens, type scale, button/card/form/nav components specced in the Design System Output Block
- Anti-pattern check: passed — no generic hero, real photos (no stock), one clear primary CTA per section

### DEVELOPMENT
- Stack: Vanilla HTML/CSS/JS (no build step)
- Hosting: Netlify (free tier) + domain (~$12/yr, client owns)
- Repo: github.com/Derec58/reyes-landscaping (private)
- Live URL: https://reyeslandscaping.example
- Site delivered: yes — 2026-06-23
- Delivery method: Netlify deploy + GitHub repo handed to client
- Post-launch issues: none — one copy tweak on the About page, fixed same day
- README: included (how to run, deploy, and update content)

### BUSINESS
- Final invoice: paid — $900, 2026-06-24 (Zelle)
- Maintenance plan: accepted — BASIC $75/month (monthly check + minor updates + monthly report)
- Google review: received — 5 stars, quoted on the site with permission
- Referral ask: yes — referred his cousin's auto-detailing shop (new lead in pipeline)
- Case study: written — published at dereckvilla.design/work/reyes-landscaping
```

---

## Part 2 — The artifacts each stage produced

A walk through the same project, showing the key output of each stage.

### 1 · Acquisition — the outreach that worked

In-person, kept short and observation-led:

> "Hey Miguel — I'm Dereck, I do websites for local businesses here in town. A neighbor was actually asking me for a landscaper referral the other day and I couldn't find you online to point them to you. You've clearly got the work and the reviews — a simple site would catch the people word-of-mouth is already sending your way. Could I show you a couple of examples and what it'd look like? Takes 15 minutes."

→ Qualified as **GREEN** and booked a call. (See `client-acquisition` → `objection-playbook.md` for handling the "I get all my business from word of mouth" reply.)

### 2 · Onboarding — proposal summary (with cost)

| Item | Detail |
|---|---|
| Project | 5-page small-business marketing site |
| Goal | Phone calls + quote-request form |
| Pages | Home, Services, Gallery, About, Contact |
| **Investment** | **$1,800 total** — $900 deposit to start, $900 on delivery |
| Timeline | ~3 weeks (live before July 4 weekend) |
| Ongoing | Domain ~$12/yr (client owns); hosting free on Netlify; optional maintenance from $75/mo |
| Not included | Logo design, copywriting beyond light edits, e-commerce |

Contract: standard small-project agreement (50/50, 2 revision rounds, IP transfers on final payment, 14-day workmanship warranty). Deposit cleared → kickoff.

### 3 · Research — what to build and why

- **Personas:** Busy Homeowner Hannah (primary), Property Manager Paul (secondary)
- **Anti-persona:** Bargain Bill — don't design for the cheapest-mow shopper
- **JTBD:** *"When my yard is overgrown and I'm out of time, I want a trustworthy local pro fast, without vetting five companies."*
- **Competitive gap:** nobody locally shows real job photos + a one-tap quote on mobile
- **→ Design requirements:** mobile-first · header click-to-call · quote form above the fold · real-work gallery · trust band (8 yrs, 40+ reviews, service area)

### 4 · Design — visual direction & system

- **Direction:** "Grounded & Natural" — warm, photo-forward, established
- **Color (OKLCH):** deep green `oklch(0.45 0.09 150)` · warm bark `oklch(0.52 0.07 65)` · golden accent `oklch(0.80 0.15 95)`
- **Type:** Fraunces (display) / Inter (body)
- **Components:** hero with photo + dual CTA, service cards, gallery grid, review band, sticky mobile call bar
- **Anti-pattern check:** passed — real photos only, one primary CTA per section, no generic template hero

### 5 · Development — build & ship

**Stack:** Vanilla HTML/CSS/JS · **Host:** Netlify · **CMS:** none (client contacts for changes)

**File structure:**
```
reyes-landscaping/
├── index.html
├── services.html
├── gallery.html
├── about.html
├── contact.html
├── css/ (reset, tokens, typography, components, styles)
├── js/ (main.js)
├── assets/ (images/, icons/)
├── favicon.ico · icon.svg · apple-touch-icon.png · site.webmanifest · og-image.png
├── robots.txt · sitemap.xml
└── README.md
```

**Markup (example — `index.html` `<head>`):**
```html
<!-- enter code here: semantic HTML5 head with title, meta description,
     canonical, Open Graph tags, favicon/icon links, font preconnect,
     and LocalBusiness + FAQPage schema -->
```

**Styles (example — `css/tokens.css`):**
```css
/* enter code here: :root design tokens — OKLCH colors, type scale,
   spacing, radii, shadows, motion (from the Design System Output Block) */
```

**Behavior (example — `js/main.js`):**
```js
// enter code here: mobile nav toggle, quote-form validation +
// success/error states, smooth scroll
```

**SEO + AEO:** unique titles/meta per page · one H1 each · `LocalBusiness` schema on Home · FAQ section with `FAQPage` schema (built from Miguel's real customer questions) · NAP consistent with the Google Business Profile.
**Performance:** WebP images, lazy-loaded below the fold · PageSpeed mobile 90+.
**Accessibility:** WCAG 2.2 AA — focus states, 44px touch targets, labelled form fields.
**Security:** form honeypot, no secrets in client code, HTTPS enforced.

→ Delivered via Netlify + repo handoff with a README. (See `web-development` pre-handoff checklist.)

### 6 · Post-launch — get paid & grow

- **Final invoice:** $900 sent on delivery; site went live once it cleared (2026-06-24).
- **Maintenance:** offered 24–48h after launch → **BASIC $75/mo accepted** (monthly check + minor updates + monthly report).
- **Review + referral** (one combined message, 3–5 days post-launch): 5-star Google review received and quoted on the site; referred his cousin's **auto-detailing shop** — now a fresh lead back at the top of the pipeline.
- **Case study:** written and published to the portfolio — which becomes social proof for the next `client-acquisition` outreach.

**Sample monthly maintenance report (Month 1):**
```
Subject: Reyes Landscaping — Site Report, July 2026

Hi Miguel — quick monthly check-in. Everything's running well.

SITE HEALTH: uptime 100% · PageSpeed mobile 92 · backups current · SSL valid
WHAT I DID: added 4 new project photos to the gallery; updated summer hours
RECOMMENDATION: 3 new 5-star reviews came in — want me to feature one on the homepage next month?

You're all set — reply any time. — Dereck
```

---

### The loop closed

One delivered project produced: **$1,800** up front, **$75/month** recurring, a **5-star review**, a **referral lead**, and a **published case study** — which feeds the next round of outreach. That's the pipeline working end to end.
