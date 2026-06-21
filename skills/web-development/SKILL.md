---
name: web-development
description: Senior front-end design partner for web build, code, SEO, accessibility, and delivery. Use this skill when the user needs to write HTML/CSS/JS, choose a tech stack, set up hosting, implement SEO, check accessibility, prepare a handoff package, or deploy a site. Trigger for any request involving code, framework decisions, CMS setup, Netlify/Vercel deployment, page titles, meta descriptions, schema markup, WCAG compliance, or delivering a finished site to a client. Do NOT use this skill for visual design, wireframes, or the design system — that is web-design. Do NOT use it for invoicing, maintenance plans, referrals, or post-launch client work — that is post-launch.
---

# Web Development Skill

**Pipeline position: Step 5 of 6**

---

## Session Start Protocol

**Only run this when the user says there is an active project.**

When activated, do the following based on your environment:

**If you are in Claude Code (VS Code terminal):**
Look for `project.md` at `~/Desktop/WebsiteProjects/[client-name]/project.md`. Read it in full. Confirm that ACQUISITION, ONBOARDING, RESEARCH, and DESIGN sections are present. Summarize what you know — business name, project type, visual direction, color tokens, typography, stack preference, timeline — so the user can confirm or correct before the build begins. If any prior sections are missing, note gaps but do not stop — at minimum you need project type, stack decision, and the design system spec.

If `project.md` does not exist, create it at the standard path using the canonical template. Prompt the user for missing context and mark unknowns as `[not captured]`.

**If you are in claude.ai chat:**
Ask the user to open `project.md` in VS Code, select all, and paste it here. Once pasted, confirm what you know and proceed. If no file exists yet, ask the user for the minimum build context — project type, stack decision, and design system spec — then proceed.

In both environments: do not ask for information already in project.md. Proceed to Step 1 — Stack Decision.

**When complete (both environments):** After the site is delivered and the client confirms receipt, append this block — in Claude Code write it directly; in chat output it and tell the user to paste it in:

```markdown
### DEVELOPMENT
- Stack: [HTML/CSS/JS / Astro / Next.js / etc.]
- Hosting: [Netlify / Vercel / other]
- Repo: [GitHub URL or local]
- Live URL: [URL or "not yet live"]
- Site delivered: [yes / date]
- Delivery method: [ZIP / GitHub / Netlify deploy]
- Post-launch issues: [none / description]
- README: [included / pending]
```

---

This skill picks up after `web-design` is complete — a fully specced design system, wireframes, and approved visual direction are ready. Its job is to turn the design spec into production-ready code, implement SEO, verify accessibility, and deliver a clean handoff package.

**What this skill receives from `web-design`:**
- Problem statement and user journeys
- Sitemap (approved by the user)
- Wireframe descriptions for all MVP pages
- Chosen visual direction
- Confirmed design system spec (tokens + components)
- Design System Output Block
- Figma spec (if requested)
- Pre-delivery anti-pattern check result
- Draft copy (marked `[DRAFT COPY]`)
- Project type, stack preference, CMS decision, hosting plan

**What this skill hands off to `post-launch`:**
- Live URL or delivery package (ZIP / GitHub repo)
- README.md with setup, deploy, and content update instructions
- Project summary (type, scope, outcome)
- Design decisions summary
- Pre-handoff checklist — all items passed
- Invoice trigger: final 50% payment due before files transfer or site goes live

---

## Step 1 — Stack Decision (Always First)

Before writing a single line of code, output the stack recommendation block. Always. No exceptions.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STACK RECOMMENDATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Recommended: [Stack name]

Why this stack for this project:
[1–3 sentences tied to project type, interactivity level,
CMS needs, SEO requirements, timeline, and handoff format]

Alternative considered: [Other stack]
Why not: [1–2 sentences — specific to this project]

Delivery format: [ZIP / GitHub repo / Netlify deploy / Vercel Pro]
Build requirements: [e.g. "None — open index.html in browser"
                   or "Node 18+, npm install, npm run dev"]
Client edits content: [Yes — via [CMS] / No — contact the user]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Read `references/stack-and-delivery.md` for the full decision framework, stack options, CMS recommendations, and hosting guidance.

### Stack Decision Quick Reference

```
Is the site primarily content and information?
(marketing, small business, blog, landing page)
  └── No complex interactivity needed → Vanilla HTML/CSS/JS (default)
      Complex interactivity needed → React + Tailwind
      SEO matters AND complex features → Next.js + Tailwind
      Content-heavy, performance priority → Astro

Is it primarily a web application?
(SaaS dashboard, internal tool, client portal)
  └── React + Tailwind (Vite)
      SEO also needed → Next.js + Tailwind
```

### Hosting Quick Reference

| Situation | Recommended host | Cost to client |
|---|---|---|
| Vanilla HTML/CSS/JS site | Netlify (free tier — allows commercial use) | ~$12/year (domain only) |
| React / Next.js app | Vercel Pro (required for commercial use) | $20/month + ~$12/year domain |
| E-commerce (Shopify) | Shopify hosting (included in plan) | $29–$299/month |
| Static site + Decap CMS | Netlify (free) | ~$12/year domain |

**The client pitch on hosting:**
> "Your only ongoing cost is your domain — about $12 a year. Hosting on Netlify is free for a site like yours. Compare that to Wix at $16–$45 every month, and with Wix you don't even own the code."

### Tooling Note — App / React Projects Only

For most small-business sites (vanilla HTML/CSS/JS), the manual pre-handoff checklist is enough. But when a project is React/Next.js or a genuine web app, two external skills are worth pulling in:
- **`webapp-testing`** (official Playwright skill) — end-to-end testing before delivery: forms, navigation, critical flows.
- **`shadcn/ui`** skill — accessible, well-structured React component patterns so you're not hand-rolling every primitive.

Don't reach for these on a 5-page static site — they're overhead that only pays off on interactive builds.

---

## Step 2 — CMS Decision

Determine whether the client needs a CMS based on the questionnaire answer: "Will you need to update content yourself?"

| Scenario | Recommended CMS |
|---|---|
| Client never edits, simple site | None — static HTML, client contacts the user for changes |
| Client edits infrequently, simple site | Decap CMS (free, Git-based, works with Netlify) |
| Content-heavy, editorial team | Sanity or Contentful |
| Blog-first, newsletter important | Ghost |
| E-commerce | Shopify |
| E-commerce, small catalog on static site | Snipcart |
| Digital products only | Gumroad or Lemon Squeezy |

---

## Step 3 — Code Standards

### HTML Structure
Always use semantic HTML5. Never use `<div>` for structural elements.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[Page-specific title] — [Business Name]</title>
  <meta name="description" content="[Unique description, 120–155 chars]">
  <link rel="canonical" href="[full page URL]">
  <!-- Open Graph -->
  <meta property="og:title" content="[title]">
  <meta property="og:description" content="[description]">
  <meta property="og:image" content="[image URL]">
  <meta property="og:url" content="[page URL]">
  <!-- Icons (see Step 7 for how to generate the set) -->
  <link rel="icon" href="/favicon.ico" sizes="any">
  <link rel="icon" href="/icon.svg" type="image/svg+xml">
  <link rel="apple-touch-icon" href="/apple-touch-icon.png">
  <link rel="manifest" href="/site.webmanifest">
  <!-- Fonts: preconnect first, then load -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link rel="stylesheet" href="css/styles.css">
</head>
<body>
  <a href="#main-content" class="skip-link">Skip to main content</a>
  <header>
    <nav aria-label="Main navigation">...</nav>
  </header>
  <main id="main-content">
    <section>...</section>
  </main>
  <footer>...</footer>
  <script src="js/main.js" defer></script>
</body>
</html>
```

### CSS Architecture (Vanilla Projects)
```
css/
├── reset.css       ← normalize browser defaults
├── tokens.css      ← all CSS custom properties (design tokens)
├── typography.css  ← font loading, type scale, heading styles
├── components.css  ← buttons, cards, forms, nav, footer
└── styles.css      ← layout, sections, page-specific; imports all above
```

### CSS Tokens (from design system spec)
Always implement the design system as CSS custom properties. Pull values from the Design System Output Block.

```css
:root {
  /* Colors */
  --color-primary:      [hex];
  --color-primary-dark: [hex];
  --color-secondary:    [hex];
  --color-accent:       [hex];
  --color-bg:           [hex];
  --color-surface:      [hex];
  --color-text:         [hex];
  --color-text-muted:   [hex];
  --color-border:       [hex];
  --color-success:      #16A34A;
  --color-warning:      #D97706;
  --color-error:        #DC2626;

  /* Typography */
  --font-display: '[Display font]', serif;
  --font-body:    '[Body font]', sans-serif;

  /* Spacing */
  --space-1: 4px;   --space-2: 8px;   --space-3: 12px;
  --space-4: 16px;  --space-6: 24px;  --space-8: 32px;
  --space-12: 48px; --space-16: 64px; --space-24: 96px;
  --space-32: 128px;

  /* Radius */
  --radius-sm: 4px; --radius-md: 8px;
  --radius-lg: 16px; --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 1px 3px rgba(0,0,0,0.08);
  --shadow-md: 0 4px 12px rgba(0,0,0,0.10);
  --shadow-lg: 0 8px 24px rgba(0,0,0,0.12);

  /* Motion */
  --duration-fast: 150ms;
  --duration-base: 200ms;
  --duration-slow: 300ms;
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);

  /* Layout */
  --max-width: 1280px;
  --container-pad: clamp(16px, 5vw, 64px);
}

/* Always include reduced motion */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Responsive Breakpoints
```css
/* Mobile first — base styles apply to all sizes */
/* Tablet */
@media (min-width: 768px) { }
/* Desktop */
@media (min-width: 1280px) { }
/* Large desktop (optional) */
@media (min-width: 1440px) { }
```

### Images
```html
<!-- Above fold / hero — do NOT lazy load -->
<img src="assets/images/hero.webp"
     alt="[Descriptive alt text]"
     width="1200" height="600"
     fetchpriority="high">

<!-- Below fold — always lazy load -->
<img src="assets/images/service.webp"
     alt="[Descriptive alt text]"
     width="800" height="500"
     loading="lazy">

<!-- With WebP + JPEG fallback -->
<picture>
  <source srcset="assets/images/hero.webp" type="image/webp">
  <img src="assets/images/hero.jpg" alt="[alt]" width="1200" height="600">
</picture>
```

### Cursor on Clickable Elements
```css
/* Always include — a common missed item */
button, a, [role="button"], label[for], summary {
  cursor: pointer;
}
```

### Icons
Always use SVG icons — never emojis as UI elements. Recommended sets: Heroicons, Lucide, Phosphor (all free).

```html
<!-- Icon button — always aria-label on the button, aria-hidden on the SVG -->
<button aria-label="Close navigation">
  <svg aria-hidden="true" focusable="false" width="24" height="24">...</svg>
</button>
```

---

## Step 4 — SEO Implementation

Read `references/seo-basics.md` for the full SEO reference. Implement these on every project.

### Per-Page Requirements

**Page title** — unique, under 60 characters:
```
[Service] in [City] | [Business Name]
```

**Meta description** — unique, 120–155 characters:
```
[What they do] in [location]. [Key benefit]. [CTA].
```

**H1** — one per page, includes primary keyword:
```html
<h1>Sacramento Plumber | Rodriguez Plumbing</h1>
```

**Heading hierarchy** — never skip levels, never use headings for styling.

**Images** — WebP format, descriptive filenames, alt text, width/height attributes.

### Local SEO (Small Business Sites)

**Footer NAP:**
```html
<footer>
  <address>
    <strong>[Business Name]</strong><br>
    [Address], [City], CA [ZIP]<br>
    <a href="tel:+1[number]">[formatted number]</a>
  </address>
</footer>
```

**LocalBusiness Schema (homepage):**
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "[Plumber / Restaurant / Photographer / etc.]",
  "name": "[Business Name]",
  "url": "[site URL]",
  "telephone": "[+1...]",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[address]",
    "addressLocality": "[city]",
    "addressRegion": "CA",
    "postalCode": "[zip]"
  },
  "areaServed": ["[city1]", "[city2]"],
  "openingHours": ["Mo-Fr 08:00-18:00"]
}
</script>
```

**Sitemap and robots.txt:**
```
# robots.txt
User-agent: *
Allow: /
Sitemap: https://[domain]/sitemap.xml
```

### Answer Engine Optimization (AEO)

Increasingly, local customers find businesses through AI answers (ChatGPT, Perplexity, Google AI Overviews), not just blue links — and AEO builds on the SEO above rather than replacing it. The high-leverage moves for a small-business site: lead each section with a direct one-sentence answer, add a real FAQ section (with `FAQPage` schema) built from actual customer questions, keep heading hierarchy strictly sequential (H1 → H2 → H3), state services / areas served / hours as plain extractable facts, and keep the content fresh. Read `references/seo-basics.md` → Answer Engine Optimization for the full checklist.

---

## Step 5 — Accessibility Implementation

Read `references/accessibility.md` for the complete WCAG 2.2 AA reference. Non-negotiables on every project:

- Skip to main content link (first focusable element)
- Visible focus states — never `outline: none` without a replacement
- All interactive elements keyboard accessible
- All images have alt text (informative) or `alt=""` (decorative)
- All form fields have associated `<label>` elements
- Minimum 4.5:1 contrast for body text, 3:1 for large text and UI components
- Minimum 44×44px touch targets on mobile
- `prefers-reduced-motion` respected
- `aria-current="page"` on active nav item
- `lang` attribute on `<html>`

```css
/* Focus state — always visible, always on-brand */
:focus-visible {
  outline: 2px solid var(--color-primary);
  outline-offset: 2px;
  border-radius: var(--radius-sm);
}

/* Skip link */
.skip-link {
  position: absolute;
  top: -100%;
  left: 0;
  background: var(--color-primary);
  color: var(--color-text-inverse);
  padding: 8px 16px;
  z-index: 9999;
  text-decoration: none;
}
.skip-link:focus { top: 0; }
```

---

## Step 6 — Performance Checklist

Before delivery, verify:

- [ ] All images are WebP format and appropriately sized
- [ ] Hero/above-fold image has `fetchpriority="high"` — NOT `loading="lazy"`
- [ ] All below-fold images have `loading="lazy"`
- [ ] All `<img>` tags have `width` and `height` attributes (prevents CLS)
- [ ] Fonts loaded with `font-display: swap` and `preconnect`
- [ ] JS loaded with `defer` attribute
- [ ] No render-blocking CSS in `<head>` beyond critical styles
- [ ] PageSpeed Insights mobile score 80+ confirmed
- [ ] Core Web Vitals: LCP < 2.5s, CLS < 0.1

---

## Step 7 — File Structure and Project Setup

### Vanilla HTML/CSS/JS
```
project-name/
├── index.html
├── about.html
├── services.html
├── contact.html
├── css/
│   ├── reset.css
│   ├── tokens.css
│   ├── typography.css
│   ├── components.css
│   └── styles.css
├── js/
│   └── main.js
├── assets/
│   ├── images/       ← WebP format, descriptive names
│   ├── fonts/        ← self-hosted if needed
│   └── icons/        ← SVG UI icons
├── favicon.ico       ← multi-size .ico
├── icon.svg          ← modern SVG favicon
├── apple-touch-icon.png  ← 180×180
├── site.webmanifest  ← PWA manifest + icon references
├── og-image.png      ← 1200×630 social share image
├── robots.txt
├── sitemap.xml
└── README.md
```

### Standard .gitignore
```
node_modules/
.env
.env.local
.DS_Store
dist/
.next/
```

### Site Icons & Social Images

Every site ships with a complete icon and social-image set — not just a single `favicon.ico`. Missing these is one of the most common "looks unfinished" tells (a blank tab icon, an ugly grey box when the link is shared). Generate, at minimum:

- **`favicon.ico`** — multi-size (16/32/48) for legacy browsers
- **`icon.svg`** — crisp scalable favicon for modern browsers
- **`apple-touch-icon.png`** — 180×180, for iOS home-screen saves
- **`site.webmanifest`** — references a 192×192 and 512×512 PNG for Android/PWA
- **`og-image.png`** — 1200×630 social share image (referenced by the `og:image` tag), so links look intentional when shared on iMessage, Facebook, WhatsApp, LinkedIn

Source the favicon set from the brand mark or a simple monogram; the OG image should carry the business name, a one-line value prop, and a real photo or the logo on-brand. The `web-asset-generator` skill produces this whole set from a single source image — use it rather than hand-exporting each size. Confirm all icon links resolve (no 404s) as part of the pre-handoff checklist.

---

## Step 8 — Deployment

### Netlify (recommended for vanilla HTML/CSS/JS)
```bash
# Option 1: Drag and drop
# Go to app.netlify.com/drop — drag the project folder

# Option 2: CLI
npm install -g netlify-cli
netlify deploy --prod

# Option 3: Connect GitHub repo for auto-deploys on push
```

**Netlify form handling (no backend needed):**
```html
<form name="contact" netlify>
  <input type="hidden" name="form-name" value="contact">
  <!-- form fields -->
</form>
```

### Vercel (React / Next.js — Pro plan required for client sites)
```bash
npm install -g vercel
vercel --prod
# Or connect GitHub repo in Vercel dashboard
```

**Custom domain (both platforms):**
1. Purchase domain at Namecheap (~$12/year for .com)
2. In Netlify/Vercel dashboard → Add domain → Follow DNS instructions
3. SSL/HTTPS is automatic (Let's Encrypt)

---

## Step 9 — Handoff Package

Every delivery includes these minimum components. Read `references/stack-and-delivery.md` for the full README template and design decisions summary format.

**What goes in the delivery package:**
- All source files (HTML, CSS, JS, assets) — no `node_modules`, no `.env`
- `README.md` — setup, how to run locally, how to deploy, how to update content
- Design decisions summary — color tokens, typography, spacing, component notes
- Any CMS configuration files
- `sitemap.xml` and `robots.txt`
- Optimized image assets

**Pre-handoff final checks:**

Code quality:
- [ ] HTML validates (validator.w3.org)
- [ ] No console errors in browser DevTools
- [ ] No broken internal links
- [ ] All forms submit correctly with success/error states
- [ ] No placeholder copy remaining — all `[DRAFT COPY]` replaced
- [ ] Favicon/icon set complete and all icon links resolve (no 404s); OG image renders in a share preview

SEO:
- [ ] Unique page title on every page (under 60 chars)
- [ ] Unique meta description on every page (120–155 chars)
- [ ] One H1 per page with primary keyword
- [ ] All images have alt text and are WebP
- [ ] LocalBusiness schema on homepage (small business sites)
- [ ] sitemap.xml generated
- [ ] PageSpeed mobile score 80+

Accessibility:
- [ ] Full WCAG 2.2 AA checklist passed (read `references/accessibility.md`)
- [ ] Keyboard navigation tested end-to-end
- [ ] Focus states visible on all interactive elements
- [ ] Touch targets 44×44px minimum on mobile

Responsive:
- [ ] Tested at 360px, 768px, 1280px minimum
- [ ] No horizontal scroll at any breakpoint
- [ ] No content hidden on mobile that matters for conversion

Security:
- [ ] No API keys, tokens, or credentials in client-side code or the repo (check committed history too)
- [ ] `.env` and secrets are gitignored and not in the delivery package
- [ ] HTTPS enforced (automatic on Netlify/Vercel) — no mixed-content warnings
- [ ] Contact/lead forms have spam protection (Netlify Forms honeypot, or a hidden honeypot field + simple validation)
- [ ] All `target="_blank"` links use `rel="noopener noreferrer"`
- [ ] For npm/framework projects: `npm audit` run, no unresolved high/critical vulnerabilities
- [ ] No sensitive data logged to the console; no debug endpoints left exposed

Delivery:
- [ ] README.md complete and accurate
- [ ] Design decisions documented
- [ ] No node_modules, .env, or .DS_Store in package
- [ ] Client login credentials documented (if CMS/hosting account involved)
- [ ] Final invoice sent — files/live site withheld until payment confirmed

---

## Pipeline Handoff to `post-launch`

Once the site is delivered and the client confirms receipt:

- [ ] Final invoice sent (50% remaining balance)
- [ ] Files/live URL withheld until payment clears
- [ ] Delivery confirmation received from client
- [ ] Offer maintenance plan, hosting management, and/or SEO retainer
- [ ] Request Google review
- [ ] Ask for referrals
- [ ] Add project to portfolio list for case study

Hand off to `post-launch` for: post-launch services, referral follow-up, invoicing, and recurring revenue setup.

---

## Build Vocabulary (Impeccable Commands)

These are the Impeccable commands relevant to the build phase. Use them as shorthand — say "run a `/harden` pass on the checkout form" and Claude will know exactly what to do. Full command set lives in `web-design/SKILL.md`; these are the 9 that apply here.

| Command | When to use it |
|---|---|
| `/audit` | Before any major refactor or pre-launch — technical quality check across a11y, performance, responsive, WCAG |
| `/normalize` | After integrating components from multiple sources or when inconsistencies have crept into the codebase |
| `/typeset` | When font choices, sizing, or hierarchy don't match the design spec — removes AI defaults like Inter-on-Inter |
| `/arrange` | When spacing, grid, or visual rhythm is off — fixes layout issues that slipped through from spec to build |
| `/harden` | Before handoff — add error states, edge cases, empty states, text overflow handling, i18n groundwork |
| `/optimize` | Performance pass — images, lazy loading, JS bundle size, render-blocking resources, Core Web Vitals |
| `/extract` | When repeated patterns should become components — clean up before handing over to client or future dev |
| `/adapt` | Responsive pass — verify layouts hold at 360px / 768px / 1280px, fix anything that breaks |
| `/polish` | Final pass before going live — the last set of eyes before delivery |

**Standard pre-launch sequence:**
```
/audit → /harden → /optimize → /adapt → /polish
```

---

## Reference Files

| File | Read when... |
|---|---|
| `references/stack-and-delivery.md` | Framework decisions, CMS options, hosting, README template, handoff checklist |
| `references/seo-basics.md` | Page titles, headings, image SEO, local SEO, schema markup, Core Web Vitals |
| `references/accessibility.md` | WCAG 2.2 AA — component checklists, ARIA patterns, keyboard navigation |
