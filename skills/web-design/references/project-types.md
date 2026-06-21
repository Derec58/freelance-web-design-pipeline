# Project Types Reference

This file defines deep workflow detail for each supported project type — page patterns, IA recommendations, component priorities, CMS recommendations, stack recommendations, and delivery notes. Read this file during Step 3 (Develop) when the project type has been identified and you need to apply the right pattern.

Always classify the project type at the start of every engagement and state it explicitly. If multiple types apply, combine the relevant sections and note the combination.

---

## Table of Contents
1. [Marketing / Branding Sites](#1-marketing--branding-sites)
2. [Small Business Sites](#2-small-business-sites)
3. [SaaS Dashboards and Web Apps](#3-saas-dashboards-and-web-apps)
4. [E-commerce](#4-e-commerce)
5. [Landing Pages (Standalone)](#5-landing-pages-standalone)
6. [Blogs and Content Sites](#6-blogs-and-content-sites)
7. [CMS Recommendations by Project Type](#7-cms-recommendations-by-project-type)
8. [Stack Recommendations by Project Type](#8-stack-recommendations-by-project-type)
9. [Delivery Format by Project Type](#9-delivery-format-by-project-type)

---

## 1. Marketing / Branding Sites

### What it is
A multi-page site that represents a business, agency, studio, or brand. Primary goal is awareness, trust-building, and conversion to a contact or inquiry. Not a transactional site — no cart, no login.

### Typical pages
```
Primary Nav:
  1. Home
  2. About
  3. Services (or Work, or What We Do)
  4. Pricing (if applicable)
  5. Blog / Resources (if applicable)
  6. Contact

Secondary / Footer:
  - Case Studies
  - FAQ
  - Privacy Policy
  - Terms

Utility:
  - 404
  - Thank You (post-form)
```

### Homepage section order (recommended)
1. Nav (sticky)
2. Hero — H1 + subheading + primary CTA + optional secondary CTA
3. Social proof bar — logos, client names, or a single strong stat
4. Services / What we do — 3–4 key offerings with brief descriptions
5. Featured work or case study — one strong example with outcome
6. About teaser — 2–3 sentences + photo or team image + link to full About
7. Testimonials — 2–3 strong quotes with name, role, and photo
8. Secondary CTA section — bold call to action, different background
9. Footer — nav links, contact info, social, legal

### Key design priorities
- **Above the fold**: H1 must immediately communicate what the business does and for whom. No taglines that require interpretation.
- **Trust signals**: Testimonials, client logos, case studies, awards, or years in business. At least one visible before the first scroll.
- **One primary conversion**: Everything points toward one action — contact, book a call, request a quote.
- **Brand expression**: This is the highest-polish site type. Typography, color, and spatial composition should be opinionated and distinctive.

### Common IA mistakes to avoid
- Too many top-level nav items (over 7)
- Services page that lists features instead of outcomes
- About page that talks about the company instead of the client's benefit
- No thank-you page after form submission (kills tracking and feels abrupt)

### Component priorities
1. Hero (full-bleed or split layout)
2. Service / feature cards (with hierarchy — not three identical items)
3. Case study or work showcase (grid or featured single)
4. Testimonial component (carousel or static grid)
5. Contact form (name, email, message, submit)
6. Footer (full — nav links, contact, social, legal)

---

## 2. Small Business Sites

### What it is
A local or regional business that provides a service or sells a physical product through a physical location. The site's job is to build enough trust for the visitor to call, book, or walk in. Audience is often non-technical and using mobile.

Covers: plumbers, electricians, landscapers, photographers, contractors, tile installers, restaurants, salons, auto shops, gyms, daycares, art studios, independent retailers, and any other trade or local service.

### Typical pages
```
Primary Nav:
  1. Home
  2. Services (or Menu, or Gallery, depending on business)
  3. About
  4. Contact / Book

Secondary / Footer:
  - FAQ
  - Service area (if relevant)
  - Privacy Policy

Utility:
  - 404
  - Thank You
```

### Homepage section order (recommended)
1. Nav — phone number prominently visible on desktop, click-to-call on mobile
2. Hero — what the business does, where, primary CTA (call or book)
3. Services summary — 3–5 services with brief descriptions, link to full services page
4. Trust signals — years in business, number of jobs completed, license/insurance badge, certifications
5. Photo gallery or portfolio — real photos of work, not stock
6. Testimonials — 3–5 reviews, ideally pulled from Google or Yelp with star ratings
7. About — brief, human, with a real photo of the owner or team
8. Service area map or list (if relevant)
9. Final CTA — phone number, contact form, or booking link
10. Footer — address, phone, hours, social links

### Key design priorities
- **Speed to trust**: A visitor decides in seconds whether this business is legitimate. Real photos, real reviews, and clear contact info are more important than visual polish.
- **Phone number always visible**: On mobile, the primary CTA is almost always a tap-to-call button. It should be in the nav, the hero, and the footer.
- **Real photos over stock**: Stock photos immediately signal inauthenticity to local service audiences. Push the client for real photos — even phone photos are better than stock.
- **Mobile-first absolutely**: A large proportion of local business searches happen on mobile. Every layout decision starts with mobile.
- **Local signals**: Mention the city/region in the H1 or hero subheading. "Serving Sacramento and the greater Central Valley" is more trustworthy than a generic national-sounding site.

### Common mistakes to avoid
- Stock photography of smiling people in hard hats or cleaning supplies
- Hero that talks about the brand instead of solving the visitor's problem
- No phone number above the fold on mobile
- Contact form as the only conversion option (many local customers prefer to call)
- Over-designed sites that feel too corporate for a neighborhood business

### Component priorities
1. Hero with tap-to-call CTA (mobile) and click-to-call number (desktop)
2. Service cards (simple, scannable, outcome-focused)
3. Trust badge row (years in business, license, guarantee)
4. Photo gallery / portfolio grid
5. Testimonials with star ratings
6. Contact form (short — name, phone, message is often enough)
7. Google Maps embed (if physical location matters)
8. Footer with full contact info and hours

### Industry-specific notes

**Photography / creative services:**
- Portfolio grid is the hero — put the work front and center
- Minimal nav and copy — let the images speak
- Contact form with project type and timeline fields

**Restaurants / food:**
- Menu must be easy to find — ideally a PDF or inline HTML (not a third-party link that breaks)
- Hours and location above the fold
- Online ordering link if available — make it the primary CTA
- Real food photography is essential

**Trades (plumbing, electrical, construction, tile):**
- Emergency availability (24/7) if applicable — should be prominent
- License and insurance prominently displayed
- Before/after photos if available — extremely effective trust builders
- Service area map or list

**Wellness / salon / spa:**
- Booking link as primary CTA (not just a contact form)
- Pricing visible or "starting from" pricing — hidden pricing increases friction
- Team photos and bios — personal connection matters in this category

---

## 3. SaaS Dashboards and Web Apps

### What it is
A web application that users log into to accomplish tasks. Can be a SaaS product (multi-tenant, subscription), an internal tool, or a client-facing portal. Design priority shifts from persuasion to usability — the user is already committed, they need to accomplish their goal efficiently.

### Typical page/view structure
```
Authenticated app:
  - Login / Signup / Forgot password
  - Dashboard (home view — key metrics, recent activity)
  - Primary feature views (core task flows)
  - Settings
  - Notifications
  - Help / Documentation link

Marketing site (separate from app):
  - Home
  - Features
  - Pricing
  - About
  - Blog
  - Login (link to app)
  - Signup CTA
```

### Dashboard layout patterns
**Sidebar nav + main content (most common)**
- Sidebar: 240–280px, fixed, icon + label nav items
- Main: scrollable content area, max-width 1200px
- Header: breadcrumb or page title, user avatar, notifications

**Top nav + content (simpler apps)**
- Horizontal nav for 5–7 sections
- Content below, full width with container max-width
- Better for apps with fewer sections

**Card-based dashboard (metrics-first)**
- KPI cards row at top
- Charts and data tables below
- Sidebar or top nav depending on complexity

### Key design priorities
- **Information density**: Dashboard users are power users. Show more, not less. Use compact spacing (--space-2 to --space-4 for table rows).
- **Keyboard accessibility**: SaaS users use keyboards heavily. Every action must be keyboard-accessible. Shortcuts are a bonus.
- **State visibility**: Loading, empty, error, and success states are as important as the default state. Never leave a user wondering if something worked.
- **Consistency is critical**: In an app, inconsistency is a bug, not a style choice. Every component must behave identically across views.
- **Navigation clarity**: User must always know where they are and how to get to any major section in 1–2 clicks.

### Empty states
Every data view needs an empty state — what does the user see before they have any data?
- Friendly illustration or icon (optional)
- Clear explanation of what will appear here
- A direct action to create the first item: "Create your first project →"
Never show a blank white space as an empty state.

### Component priorities
1. Sidebar or top navigation with active states
2. Data tables (sortable, filterable, with pagination or infinite scroll)
3. KPI / metric cards
4. Charts (line, bar, pie — specify which type fits which data)
5. Forms for creating/editing records
6. Modal dialogs for confirmations and focused tasks
7. Toast notifications for async feedback
8. Empty states for all data views
9. Loading skeletons (not spinners) for data-heavy views

### Auth flow requirements
- Login: email + password, forgot password link, show/hide password toggle
- Signup: minimal fields — email + password, or SSO options
- Forgot password: email field, clear confirmation message
- All auth forms: keyboard navigable, error messages specific, no form clear on error

---

## 4. E-commerce

### What it is
A site where users browse, select, and purchase products. Can be physical goods, digital products, or services with online payment. Design priority is reducing friction in the path from discovery to purchase.

### Typical page structure
```
Primary Nav:
  - Home
  - Shop (or product category names)
  - About
  - Contact / Support

Key pages:
  - Product listing / category page (PLP)
  - Product detail page (PDP)
  - Cart
  - Checkout (multi-step or single page)
  - Order confirmation / Thank you
  - Account (order history, saved addresses)
  - Returns / FAQ
```

### Product listing page (PLP) — section order
1. Category header (name, optional description, product count)
2. Filter and sort controls (persistent on scroll for desktop)
3. Product grid (3–4 columns desktop, 2 columns tablet, 1–2 columns mobile)
4. Pagination or load more
5. Footer

### Product detail page (PDP) — section order
1. Breadcrumb (Home > Category > Product Name)
2. Product images (gallery left, details right on desktop — stacked on mobile)
3. Product name (H1), price, rating summary
4. Variant selectors (size, color, etc.)
5. Add to cart CTA (sticky on mobile)
6. Product description
7. Reviews section
8. Related products

### Checkout flow
- **Minimize steps**: Ideal is 3 steps — Contact → Shipping → Payment. One-page checkout if technically feasible.
- **Guest checkout**: Always offer. Requiring account creation is one of the top cart abandonment causes.
- **Progress indicator**: Users need to know how many steps remain.
- **Order summary**: Always visible or easily accessible during checkout.
- **Trust signals**: Security badge, accepted payment icons, return policy summary — all visible on checkout pages.

### Key design priorities
- **Product photography**: Images are the product on an e-commerce site. Spec at least one clean white-background image per product plus lifestyle context shots.
- **Filter and sort**: Critical for any catalog over 20 products. Filters by price, category, size, color, rating — whatever is relevant.
- **Mobile cart and checkout**: Most purchases are initiated on mobile. The add-to-cart and checkout flow must be flawless at 360px.
- **Trust and returns**: A clear, visible return policy reduces purchase anxiety significantly.
- **Speed**: E-commerce sites live and die by load speed. Image optimization and minimal JS are essential.

### Component priorities
1. Product card (image, name, price, rating, quick-add to cart)
2. Product image gallery (zoom, multiple angles)
3. Variant selector (size, color — with clear out-of-stock indication)
4. Add to cart button (with immediate feedback — cart count updates)
5. Cart drawer or page (editable quantities, remove items, subtotal)
6. Checkout form (contact, shipping, payment — with validation)
7. Filter panel (sidebar desktop, modal/drawer mobile)
8. Review component (star rating, review text, reviewer name)
9. Related products grid

---

## 5. Landing Pages (Standalone)

### What it is
A single-purpose page with one conversion goal. No persistent site navigation — the user arrived from an ad, email, or link and the page's only job is to convert them. Everything on the page serves that one goal.

### When to use
- Paid ad campaigns (Google Ads, Meta Ads)
- Email campaign destinations
- Product launches
- Event registrations
- Lead magnet downloads
- Free trial signups

### Page structure — conversion-optimized order
1. Nav bar — logo only, no links (no exits). Optional: primary CTA in top right.
2. Hero — H1 (clear value prop), subheading (expands on H1), primary CTA, optional supporting image
3. Social proof — logos, a strong stat, or 1–2 short testimonials
4. Problem statement — articulate the pain the user feels
5. Solution / features — how the product solves the problem (3–5 points)
6. How it works — optional simple 3-step process
7. Testimonials — 2–4 strong quotes with photo, name, and role
8. Objection handling — FAQ addressing top concerns
9. Final CTA section — repeat the offer, primary CTA, urgency element if genuine
10. Footer — minimal. Privacy policy, legal, unsubscribe (for email campaigns).

### Key design priorities
- **One CTA, repeated**: The same primary action should appear 3–4 times down the page (hero, mid-page, final section). Never introduce a second competing action.
- **Remove all exits**: No nav links to other pages. No social media links. Every link that isn't the CTA is a potential lost conversion.
- **Match the ad**: If the user clicked an ad with a specific headline or offer, the landing page H1 must match or directly continue that message. Mismatch = immediate bounce.
- **Above the fold matters most**: The H1, subheading, and CTA must be compelling enough to keep the user scrolling. Test ruthlessly.
- **Urgency and scarcity**: Only use if genuine. False urgency (fake countdown timers) damages trust permanently.

### Landing page patterns
- **Hero-centric**: Strong visual, bold headline, single CTA. Best for brand-led campaigns.
- **Conversion-optimized**: Form above the fold, minimal copy, immediate value exchange. Best for lead gen.
- **Social proof-led**: Lead with testimonials, ratings, or user count. Best for products with strong proof.
- **Storytelling**: Scrolling narrative that builds from problem to solution. Best for complex or high-consideration products.

### Component priorities
1. Hero (H1, subheading, CTA, supporting image or video thumbnail)
2. Social proof bar (logos or stat)
3. Feature/benefit list (3–5 items with icons)
4. Testimonials (2–4 with photo and attribution)
5. FAQ accordion (3–6 questions addressing objections)
6. Final CTA section (offer restatement + button)
7. Form (if lead gen — minimal fields, name + email standard)

---

## 6. Blogs and Content Sites

### What it is
A site where the primary value is written or multimedia content. Can be attached to a marketing site (company blog) or standalone (independent publication, personal brand, news site). Design priority is readability, discoverability, and return visits.

### Typical page structure
```
Primary Nav:
  - Home
  - Topics / Categories
  - About
  - Newsletter (if applicable)
  - Search

Key pages:
  - Homepage (featured + recent articles)
  - Category / topic listing
  - Article / post detail
  - Author page
  - Search results
  - Newsletter signup
  - Archive
```

### Homepage section order
1. Nav with search
2. Featured article (large hero treatment — one article, strong image, headline, excerpt)
3. Recent articles grid (3-column desktop, 2-column tablet, 1-column mobile)
4. Category or topic navigation (horizontal scroll on mobile)
5. Newsletter signup (inline section — not a popup)
6. More articles or "Editor's picks"
7. Footer

### Article page layout
1. Breadcrumb (Home > Category > Article title)
2. Article header (H1, author, date, read time, category tag)
3. Hero image (full-width or contained, with caption)
4. Article body (max-width 72ch, --leading-relaxed, generous paragraph spacing)
5. Pull quotes (for long-form — break up dense text visually)
6. In-article CTA (newsletter signup or related content — appears mid-article or at end)
7. Author bio block
8. Related articles (3 cards)
9. Comments (if applicable)

### Key design priorities
- **Readability is everything**: Line length 60–75 characters. Generous line height (1.65+). Sufficient paragraph spacing. No distractions in the reading column.
- **Scannability**: Strong H2 subheadings every 150–200 words. Pull quotes for key points. Bullet lists for multi-item content.
- **Discoverability**: Related articles, category navigation, and search must be prominent. The goal is multiple page views per visit.
- **Newsletter capture**: The email list is the most valuable asset for a content site. At least one non-intrusive signup opportunity per page.
- **SEO structure**: Semantic heading hierarchy (one H1 per page, logical H2/H3 structure), image alt text, descriptive URLs, meta descriptions.

### Component priorities
1. Article card (image, category tag, headline, excerpt, author, date, read time)
2. Article body typography (drop cap optional, pull quotes, blockquotes, code blocks if technical)
3. Category tag / filter navigation
4. Newsletter signup (inline form — not modal)
5. Author bio (photo, name, short bio, social links)
6. Related articles grid
7. Search (header search bar or dedicated search page)
8. Table of contents (for long-form articles over 1500 words)

---

## 7. CMS Recommendations by Project Type

Always ask during discovery: "Will the client need to edit content after handoff?" If yes, recommend a CMS. If no, vanilla HTML or a static build is acceptable.

| Project Type | Client edits? | Recommended CMS | Why |
|---|---|---|---|
| Small business site | Sometimes | **Decap CMS** (free, Git-based) or **Forestry/Tina CMS** | Simple UI, no hosting cost, works with static sites |
| Small business site | Rarely | None — static HTML | Simpler to build and hand off, client calls for changes |
| Marketing / branding site | Often | **Contentful** (mid-size) or **Sanity** (flexible) | Structured content, good developer experience |
| Marketing / branding site | Sometimes | **Decap CMS** or **Netlify CMS** | Free, Git-based, easy for non-technical clients |
| Blog / content site | Always | **Sanity** or **Contentful** | Built for editorial workflows, strong structured content |
| Blog / content site | Simple needs | **Ghost** | Purpose-built for blogs, great editor, built-in newsletter |
| E-commerce | Always | **Shopify** | Best-in-class e-commerce CMS, hosting included, huge ecosystem |
| E-commerce (small catalog) | Sometimes | **Snipcart** + static site | Add cart to any HTML site, no platform lock-in |
| E-commerce (digital products) | Always | **Gumroad** or **Lemon Squeezy** | Purpose-built for digital product sales |
| SaaS / web app | N/A | No CMS — app manages its own data | Content is dynamic, managed by the application |
| Landing page | Rarely | None — static HTML | No content management needed for single-purpose pages |

### CMS Decision Rules
- **Free + simple + client edits infrequently** → Decap CMS / Netlify CMS (Git-based, no cost)
- **Content-heavy + editorial team** → Sanity or Contentful
- **Blog-first** → Ghost (includes newsletter, membership, great editor)
- **E-commerce** → Shopify first, Snipcart if they already have a static site
- **Client won't edit anything** → No CMS. Ship clean HTML and charge for updates, or teach them basic file editing.

---

## 8. Stack Recommendations by Project Type

Always explain the framework tradeoff upfront on every project before writing code. Use this section to justify the recommendation.

### Stack Decision Framework

**Start here:** What does the site need to do?

```
Is it primarily content and information? (marketing, small business, blog, landing page)
  → Start with vanilla HTML/CSS/JS or a static site generator
  → Only add a framework if interactivity genuinely requires it

Does it have complex interactivity? (filters, real-time data, user accounts, dynamic UI)
  → React + Tailwind or Vue + Tailwind
  → Next.js if SEO matters AND it's a React app

Is it a simple landing page or small business site with minimal JS?
  → Vanilla HTML/CSS/JS — fastest to build, easiest to hand off, no dependencies
```

### Stack Options and When to Use Each

**Vanilla HTML/CSS/JS**
- Best for: Small business sites, simple marketing sites, landing pages, any project where simplicity and deliverability matter
- Pros: No build step, no dependencies, easiest to hand off (ZIP file works), fastest load times, Dereck is most comfortable here
- Cons: No component reuse across pages without copy-paste, no reactive UI
- Deliver as: ZIP of static files, GitHub repo, or deploy to Netlify/Vercel with drag-and-drop

**HTML + Tailwind CSS**
- Best for: Projects where consistent utility-first styling matters, or where a design system needs to be applied systematically across many components
- Pros: Consistent spacing and sizing, utility classes reduce custom CSS, works well with static HTML
- Cons: Requires a build step (Tailwind CLI or CDN play version for simple projects), class-heavy HTML can be hard to read
- Deliver as: Built CSS file + HTML, or via Tailwind CDN for simple projects

**React + Tailwind**
- Best for: SaaS dashboards, web apps with dynamic state, e-commerce with complex filtering, any project with significant user interaction
- Pros: Component reuse, reactive state, large ecosystem, easy to add interactivity
- Cons: Heavier for simple sites, requires Node environment, more complex handoff
- Deliver as: GitHub repo with README, deployed to Vercel

**Next.js + Tailwind**
- Best for: React projects that also need SEO (marketing sites built in React, blogs, e-commerce where SSR matters)
- Pros: Server-side rendering, static generation, built-in routing, image optimization
- Cons: More complex, overkill for simple sites
- Deliver as: GitHub repo, deploy to Vercel (native Next.js host)

**Astro**
- Best for: Content-heavy sites (blogs, marketing sites, documentation) that want component-based development without heavy JS
- Pros: Ships zero JS by default, fast, supports React/Vue components where needed
- Cons: Smaller ecosystem, less familiar to most developers
- Deliver as: GitHub repo, deploy to Netlify or Vercel

### Tradeoff Explanation Template

Always present this upfront when code is requested:

```
Stack recommendation: [chosen stack]
Reason: [1–2 sentences tied to project needs]

Alternative considered: [other option]
Why not: [1–2 sentences explaining the tradeoff]

Delivery format: [ZIP / GitHub repo / Vercel deploy]
Build requirements: [Node version, npm commands, or "none — open index.html directly"]
```

---

## 9. Delivery Format by Project Type

Default delivery is always all project files. The format depends on client needs and project complexity.

| Project Type | Recommended delivery | Notes |
|---|---|---|
| Small business site (vanilla) | ZIP of static files + GitHub repo | Client or their host uploads files. Simple. |
| Small business site (with CMS) | GitHub repo + Netlify/Vercel deploy | CMS connects to Git repo. Client edits through CMS UI. |
| Marketing site | GitHub repo + Vercel/Netlify deploy | Easy to update, automatic deploys on push |
| Landing page | ZIP or Vercel deploy | ZIP for clients who paste into their own system, Vercel for standalone |
| Blog | GitHub repo + Netlify deploy + CMS setup | Full setup including CMS config |
| E-commerce (Shopify) | Shopify theme files + setup instructions | Delivered inside Shopify admin |
| E-commerce (static + Snipcart) | GitHub repo + Vercel deploy | Snipcart script added to HTML |
| SaaS / web app | GitHub repo + Vercel deploy + README | Includes setup instructions, env variables documented |

### Hosting Notes
- **Vercel**: Best for Next.js and React projects. Free tier is generous. Automatic deploys from GitHub.
- **Netlify**: Best for static sites and sites with Decap/Netlify CMS. Free tier includes form handling. Drag-and-drop deploy for simple projects.
- **GitHub Pages**: Free static hosting. Good for simple sites but no server-side functionality.
- **Shopify**: Self-contained hosting for e-commerce. Not applicable for other project types.

### What Every Delivery Package Includes (minimum)
- All source files (HTML, CSS, JS, assets)
- A `README.md` with: project overview, how to run locally, how to deploy, how to update content
- Any CMS configuration files
- Font files or import links documented
- Image assets optimized and organized
- A summary of design decisions (token values, font choices, color system) so the client or future developer can maintain consistency

---

## 10. Redesign / Audit Projects

### What it is
An existing site that needs to be improved, refreshed, or fully rebuilt. The client already has something — the job is to evaluate it objectively and either improve what's there or replace it with something better.

### Always start with an audit — never jump straight to redesign
Before proposing any changes, run the structured audit from SKILL.md's Audit Mode:

1. **Classify** the project type and primary business goal
2. **Audit across five areas**, severity rated High / Medium / Low:
   - IA and navigation
   - Visual hierarchy and clarity
   - Forms and flows
   - Accessibility and responsiveness (WCAG 2.2 AA)
   - Performance and content
3. **Add SEO audit** (read `references/seo-basics.md`):
   - Page titles and meta descriptions
   - Heading structure
   - Image alt text and file sizes
   - Core Web Vitals score (run PageSpeed Insights)
   - Local SEO signals (if small business)
4. **Prioritized improvement plan** — what to fix first, what can wait
5. **Decision point**: patch the existing site OR rebuild from scratch?

### Patch vs Rebuild Decision

**Patch (improve existing):**
- Structure is sound but design is outdated
- Content is good and mostly accurate
- Client has a limited budget or tight timeline
- Technical stack is reasonable and maintainable

**Rebuild:**
- Site is built on a platform the client wants to leave (Wix, Weebly, Flash)
- Layout is so outdated it would take longer to patch than rebuild
- Content needs a full rewrite anyway
- Client wants a fundamentally different direction

### Audit Output Format

```markdown
## Site Audit — [Business Name]
**URL:** [site URL]
**Date:** [date]
**Project type:** [e.g. Small business plumbing site]
**Primary goal:** [e.g. Phone calls and quote requests]

### High Priority (fix before or during launch)
- [Issue] — [specific location on site] — [recommendation]

### Medium Priority (fix in first iteration)
- [Issue] — [recommendation]

### Low Priority (future consideration)
- [Issue] — [recommendation]

### What's Working Well
- [Keep these — don't fix what isn't broken]

### SEO Snapshot
- Page titles: [Pass / Fail — details]
- H1 structure: [Pass / Fail — details]
- Mobile PageSpeed score: [score] / 100
- Core Web Vitals: [LCP / INP / CLS — pass or fail]
- Local signals: [Present / Missing]

### Recommendation
[Patch / Rebuild] — [2–3 sentence justification]

### Proposed Scope
[If patching: list specific changes]
[If rebuilding: treat as new build per project-types.md]
```

---

## 11. Hosting Notes — Corrected

The following clarifies accurate hosting costs to use in client conversations and proposals.

### Netlify (recommended for simple sites)
- **Free tier**: allows commercial use for static sites — this is the honest "no monthly fee" story
- **Custom domain**: free to connect on Netlify — client only pays for the domain itself (~$10–15/year from Namecheap or Cloudflare)
- **Best for**: vanilla HTML/CSS/JS sites, sites with Decap CMS, any static site
- **Forms**: Netlify has built-in form handling on the free tier (100 submissions/month) — no backend needed

### Vercel
- **Hobby tier**: free BUT restricted to non-commercial use — **not appropriate for client sites**
- **Pro tier**: $20/month — required for any commercial (client) project
- **Custom domain**: free to connect on both tiers — domain cost is separate
- **Best for**: React, Next.js, or any project that benefits from Vercel's edge network

### Honest client pitch on hosting costs
```
Simple small business site (Netlify):
  Domain: ~$12/year (one-time annual)
  Hosting: $0/month (Netlify free tier)
  Platform fee: $0 (you own the code — no Wix/Squarespace subscription)
  Total: ~$12/year

React/Next.js site (Vercel):
  Domain: ~$12/year
  Hosting: $20/month (Vercel Pro — required for commercial sites)
  Platform fee: $0
  Total: ~$252/year

Compare to Wix: $192–$540/year (and you don't own the code)
Compare to Squarespace: $192–$588/year (and you don't own the code)
```

The "you own the code" angle is the strongest differentiator — make sure clients understand what that means: if they ever want to switch designers, move hosts, or hand the site to a developer, they take the code with them. No platform lock-in, no starting over.
