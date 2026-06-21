# Stack and Delivery Reference

This file covers framework selection, the upfront tradeoff explanation template, CMS recommendations, hosting options, delivery formats, and handoff standards. Read this file whenever code is requested, a stack decision needs to be made, a CMS needs to be recommended, or a project is approaching delivery.

Always explain the stack tradeoff upfront on every project before writing any code. Never skip this step — the explanation is part of the deliverable.

---

## Table of Contents
1. [Stack Decision Process](#1-stack-decision-process)
2. [Vanilla HTML/CSS/JS](#2-vanilla-htmlcssjs)
3. [HTML + Tailwind CSS](#3-html--tailwind-css)
4. [React + Tailwind](#4-react--tailwind)
5. [Next.js + Tailwind](#5-nextjs--tailwind)
6. [Astro](#6-astro)
7. [Upfront Tradeoff Explanation Template](#7-upfront-tradeoff-explanation-template)
8. [CMS Selection](#8-cms-selection)
9. [Hosting and Deployment](#9-hosting-and-deployment)
10. [Delivery Formats](#10-delivery-formats)
11. [Handoff Standards](#11-handoff-standards)

---

## 1. Stack Decision Process

Run through this decision tree at the start of every project where code will be written. State the recommendation and reasoning before writing a single line.

```
Step 1 — What does the site primarily do?

  Displays content and information
  (marketing, small business, blog, landing page)
        │
        ▼
  Step 2 — Does it have significant interactivity?
  (user accounts, dynamic filtering, real-time data, complex state)
        │
        ├── No → Vanilla HTML/CSS/JS (default)
        │         Add Tailwind if design system consistency matters
        │
        └── Yes → React + Tailwind
                  Next.js if SEO also matters

  Is it primarily a web application?
  (SaaS dashboard, internal tool, client portal)
        │
        ▼
  React + Tailwind or Next.js + Tailwind
  (depending on SEO requirements)

  Is it a content-heavy site with some interactivity?
  (large blog, documentation, marketing + interactive features)
        │
        ▼
  Astro (ships zero JS by default, supports React components where needed)
```

### Decision Factors Checklist

Answer these before recommending a stack:

- [ ] Does the client need to edit content after handoff? (CMS needed)
- [ ] Does the site have user accounts or authentication?
- [ ] Does the site have real-time data or complex dynamic state?
- [ ] Does SEO matter significantly? (affects SSR/SSG decision)
- [ ] What is Dereck's comfort level with this stack? (vanilla is most comfortable)
- [ ] What is the client's technical level? (affects hosting and handoff choices)
- [ ] Is there a hard performance requirement? (favors vanilla or Astro)
- [ ] Is there a tight timeline? (favors vanilla — no build step, fastest to ship)
- [ ] Will other developers maintain this code? (affects framework choice)

---

## 2. Vanilla HTML/CSS/JS

### When to use
- Small business sites
- Simple marketing and branding sites
- Standalone landing pages
- Any project where simplicity, speed of delivery, and easy handoff matter most
- When Dereck is working solo and timeline is tight
- When the client is non-technical and needs to receive files they can open directly

### Strengths
- No build step — open `index.html` directly in a browser
- No dependencies — nothing to install, nothing to break, nothing to update
- Easiest handoff — ZIP file works, anyone can receive and use it
- Fastest load times — no framework overhead
- Dereck is most comfortable here — fastest path from design to working code
- Future-proof — vanilla HTML/CSS/JS will work forever

### Weaknesses
- No component reuse — shared elements (nav, footer) must be copy-pasted across pages
- No reactive state — dynamic UI (live filters, real-time updates) requires manual DOM manipulation
- Scaling to many pages becomes tedious without a build tool or templating layer
- No hot reload without a dev server (use VS Code Live Server extension)

### When NOT to use
- Any project requiring user authentication
- Projects with significant dynamic state or real-time data
- E-commerce beyond a static catalog with a simple cart (use Shopify or add Snipcart)
- Projects where the client team will build on top of it using a framework

### Hosting for vanilla HTML projects
**Use Netlify (free tier) — not Vercel Hobby — for client sites.**
Vercel's Hobby tier is restricted to non-commercial use. Client sites are commercial by definition.
Netlify's free tier allows commercial use on static sites with no caveats.
- Custom domain: free to connect on Netlify — client pays ~$12/year for the domain itself
- Forms: Netlify handles up to 100 form submissions/month free — no backend needed
- Deploy: drag-and-drop the project folder at app.netlify.com/drop, or connect GitHub for auto-deploys

**Honest hosting pitch to clients:**
"Your only ongoing cost is your domain — about $12 a year. Hosting is free on Netlify for a site like yours.
Compare that to Wix at $16–$45 every month, forever — and with Wix, you don't even own the code."


### File structure (recommended)
```
project-name/
├── index.html
├── about.html
├── services.html
├── contact.html
├── css/
│   ├── reset.css
│   ├── tokens.css       ← CSS custom properties (design tokens)
│   ├── typography.css
│   ├── components.css
│   └── styles.css       ← main stylesheet, imports others
├── js/
│   └── main.js
├── assets/
│   ├── images/
│   ├── fonts/
│   └── icons/
└── README.md
```

### CSS architecture for vanilla projects
```css
/* tokens.css — all custom properties */
:root {
  --color-primary: #2C3E50;
  --color-accent: #E74C3C;
  --font-display: 'Playfair Display', serif;
  --font-body: 'Jost', sans-serif;
  /* ... full token set */
}

/* reset.css — normalize browser defaults */
*, *::before, *::after { box-sizing: border-box; }
body { margin: 0; }
img { max-width: 100%; display: block; }
/* ... */

/* Typography, components, layout in separate files */
/* styles.css imports everything */
@import './reset.css';
@import './tokens.css';
@import './typography.css';
@import './components.css';
```

### Performance defaults for vanilla
```html
<!-- In <head> -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="css/styles.css">

<!-- Images: always specify width and height -->
<img src="assets/images/hero.webp"
     alt="Descriptive alt text"
     width="1200"
     height="600"
     loading="lazy">  <!-- lazy on below-fold images -->

<!-- JS: defer all scripts -->
<script src="js/main.js" defer></script>
```

---

## 3. HTML + Tailwind CSS

### When to use
- Projects where a design system needs to be applied systematically
- Multi-page sites where visual consistency across many components matters
- When the client or future developer is familiar with Tailwind
- When Dereck wants utility-first styling without a full framework

### Strengths
- Consistent spacing, sizing, and color via utility classes
- No custom CSS naming conventions needed (no BEM debates)
- Great IntelliSense support in VS Code
- Can be used with vanilla HTML via CDN (no build step for simple projects)
- Scales well to larger projects with a build step

### Weaknesses
- Class-heavy HTML can become hard to read
- Requires a build step for production (purging unused styles)
- CDN version includes all classes (~3MB) — not suitable for production without purging
- Learning curve if client or developer is unfamiliar

### Two modes

**CDN mode (no build step — for simple projects):**
```html
<script src="https://cdn.tailwindcss.com"></script>
<!-- Use in development or low-traffic simple projects only -->
<!-- Configure in a script tag: -->
<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          primary: '#2C3E50',
          accent: '#E74C3C',
        },
        fontFamily: {
          display: ['Playfair Display', 'serif'],
          body: ['Jost', 'sans-serif'],
        }
      }
    }
  }
</script>
```

**CLI mode (production — recommended for larger projects):**
```bash
npm install -D tailwindcss
npx tailwindcss init
# Configure tailwind.config.js
# Add build script to package.json
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```

### When NOT to use
- Tiny one-page projects where a few lines of custom CSS is faster
- Projects where the client needs to understand or edit the CSS
- When the developer receiving the code is unfamiliar with Tailwind

---

## 4. React + Tailwind

### When to use
- SaaS dashboards and web apps
- E-commerce with complex filtering and cart state
- Any project with significant dynamic UI (real-time updates, complex state, user accounts)
- Multi-page applications where component reuse across routes matters

### Strengths
- Component-based — build once, reuse everywhere
- Reactive state — UI updates automatically when data changes
- Massive ecosystem — libraries for everything
- Excellent developer tooling (Vite, hot reload, React DevTools)
- Tailwind integrates seamlessly

### Weaknesses
- Overkill for simple content sites — adds build complexity and JS overhead
- Larger bundle size — not appropriate for simple marketing sites
- Steeper learning curve for non-React developers
- SEO limitations with client-side rendering (use Next.js if SEO matters)

### Project setup (Vite — recommended for React without SSR needs)
```bash
npm create vite@latest project-name -- --template react
cd project-name
npm install
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

### File structure (recommended)
```
project-name/
├── public/
│   └── assets/
├── src/
│   ├── components/
│   │   ├── ui/           ← primitive components (Button, Input, Card)
│   │   └── layout/       ← layout components (Nav, Footer, Section)
│   ├── pages/            ← page-level components
│   ├── hooks/            ← custom React hooks
│   ├── utils/            ← utility functions
│   ├── styles/
│   │   └── index.css     ← Tailwind directives + custom CSS
│   ├── App.jsx
│   └── main.jsx
├── tailwind.config.js
├── vite.config.js
├── package.json
└── README.md
```

### When NOT to use
- Simple marketing sites, small business sites, landing pages
- Projects where load speed is paramount (ship vanilla instead)
- Projects where the receiving developer is not comfortable with React

---

## 5. Next.js + Tailwind

### When to use
- React projects that also need strong SEO (marketing sites built in React, e-commerce)
- Large content sites that benefit from static generation (blogs, documentation)
- Projects where both SEO and dynamic React features are needed
- When deploying to Vercel (native integration — optimal performance)

### Strengths
- Server-side rendering (SSR) and static generation (SSG) — best of both worlds
- Built-in routing (file-based) — no react-router needed
- Image optimization built in (`next/image`)
- Font optimization built in (`next/font`)
- Native Vercel deployment — zero config
- API routes — lightweight backend without a separate server

### Weaknesses
- More complex than plain React — more concepts to learn
- Overkill for simple apps that don't need SSR/SSG
- Longer build times for large sites
- Vendor coupling to Vercel (works elsewhere but Vercel is the optimal host)

### Project setup
```bash
npx create-next-app@latest project-name
# Choose: TypeScript (optional), Tailwind (yes), App Router (yes)
cd project-name
npm run dev
```

### When NOT to use
- Simple React apps with no SEO requirements (use Vite + React instead)
- Small business or marketing sites (vanilla HTML is faster to build and ship)
- When the team is not comfortable with the Next.js mental model

---

## 6. Astro

### When to use
- Content-heavy sites that want component-based development without heavy JS (blogs, marketing sites, documentation)
- Sites where performance is a top priority — Astro ships zero JS by default
- Projects where you want to mix static content with React/Vue components in specific places
- Marketing sites for tech companies where the developer audience will appreciate zero-JS philosophy

### Strengths
- Zero JS shipped by default — only hydrates components that need interactivity
- Supports React, Vue, Svelte components in the same project
- Excellent for content-focused sites
- File-based routing like Next.js
- Content Collections — built-in structured content management for blogs

### Weaknesses
- Smaller ecosystem than React/Next.js
- Less familiar to most developers — harder to hand off
- Not appropriate for highly dynamic apps (SaaS dashboards, real-time features)
- Fewer third-party integrations than React ecosystem

### When NOT to use
- SaaS dashboards or web apps with complex state
- Projects where the client team will build on top of it using React
- When Dereck is unfamiliar and timeline is tight (stick to vanilla or React)

---

## 7. Upfront Tradeoff Explanation Template

**Always output this before writing any code.** Fill in all fields. Never skip this step.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STACK RECOMMENDATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Recommended: [Stack name]

Why this stack for this project:
[1–3 sentences tied to specific project needs — not generic reasons.
Reference the project type, client needs, interactivity level, SEO requirements,
timeline, and/or handoff requirements.]

Alternative considered: [Other stack]
Why not: [1–2 sentences explaining the specific tradeoff for this project.]

[If a second alternative is worth mentioning:]
Also considered: [Other stack]
Why not: [1–2 sentences.]

Delivery format: [ZIP of static files / GitHub repo / Vercel deploy / Netlify deploy]
Build requirements: [e.g. "None — open index.html directly in a browser"
                   or "Node 18+, run npm install then npm run dev"]
Client can edit content: [Yes — via [CMS name] / No — contact Dereck for changes]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Example — Small Business Site

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STACK RECOMMENDATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Recommended: Vanilla HTML/CSS/JS

Why this stack for this project:
This is a 5-page local plumbing site with no dynamic features —
just content, contact form, and a photo gallery. Vanilla HTML gives
us the fastest load times, the simplest handoff, and no build-step
complexity. The client won't be editing content themselves, so no CMS
is needed. This is the fastest path from design to a live, deliverable site.

Alternative considered: HTML + Tailwind CSS
Why not: The design system for this project is simple enough that a
well-organized custom CSS file is faster to write and easier to hand
off than a Tailwind setup. Tailwind adds value at scale — this project
doesn't need it.

Alternative considered: React + Tailwind
Why not: No dynamic state or interactivity that would justify the
framework overhead. Loading a React bundle for a 5-page static site
would hurt Core Web Vitals and add unnecessary complexity.

Delivery format: ZIP of static files + GitHub repo
Build requirements: None — open index.html directly in any browser
Client can edit content: No — contact Dereck for content changes
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Example — SaaS Dashboard

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STACK RECOMMENDATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Recommended: React + Tailwind (via Vite)

Why this stack for this project:
This SaaS dashboard requires dynamic state (real-time data updates,
interactive filters, user account management), component reuse across
many views, and a reactive UI that responds instantly to user actions.
React is the right tool for this level of interactivity. Tailwind keeps
the design system consistent across a large component library.
SEO is not a concern for authenticated dashboard views, so plain
React via Vite is simpler and faster than Next.js.

Alternative considered: Next.js + Tailwind
Why not: The dashboard is fully authenticated — SEO is irrelevant for
logged-in views. Vite + React is simpler to configure and faster to
develop without the SSR complexity that Next.js adds.

Alternative considered: Vanilla HTML/CSS/JS
Why not: The level of dynamic state and interactivity in this dashboard
would require complex manual DOM manipulation in vanilla JS — React
handles this cleanly and maintainably.

Delivery format: GitHub repo + Vercel deployment
Build requirements: Node 18+, run npm install then npm run dev
Client can edit content: N/A — app manages its own data
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 8. CMS Selection

### Decision Table

| Scenario | Recommended CMS | Why |
|---|---|---|
| Simple site, client edits infrequently | **Decap CMS** | Free, Git-based, works with any static site, simple UI |
| Simple site, client never edits | None | Ship static files, client calls for changes |
| Content-heavy site, editorial team | **Sanity** | Flexible schema, excellent editor, real-time collaboration |
| Content-heavy site, simpler needs | **Contentful** | Structured content, good API, well-documented |
| Blog-first, newsletter important | **Ghost** | Purpose-built for publishing, built-in newsletter and membership |
| E-commerce, any size | **Shopify** | Best-in-class e-commerce, hosting included, huge app ecosystem |
| E-commerce, small catalog on existing site | **Snipcart** | Add cart to any HTML site without platform migration |
| Digital products only | **Gumroad** or **Lemon Squeezy** | Purpose-built for digital sales, handles tax compliance |
| SaaS / web app | None | Application manages its own data |

### CMS Setup Notes

**Decap CMS (formerly Netlify CMS)**
- Requires: Netlify hosting, GitHub repo
- Setup: Add a `admin/` folder with `config.yml` to the project
- Client experience: Logs into `/admin` URL, edits content in a form UI, changes commit to GitHub automatically
- Cost: Free
- Best for: Small business sites, simple marketing sites where client needs occasional content updates

**Sanity**
- Requires: Node.js project, Sanity account (free tier generous)
- Setup: `npm create sanity@latest` — creates a Studio (admin panel) and connects to your frontend via API
- Client experience: Sanity Studio — highly customizable, clean editing interface
- Cost: Free tier (up to 3 users, 500k API requests/month), paid above that
- Best for: Blogs, marketing sites with complex content models, editorial teams

**Ghost**
- Requires: Ghost hosting (Ghost Pro — paid) or self-hosted (Digital Ocean droplet)
- Setup: Ghost Pro is turnkey. Self-hosted requires server setup.
- Client experience: Beautiful editorial interface, built-in newsletter, membership tiers
- Cost: Ghost Pro starts ~$9/month. Self-hosting is cheaper but requires maintenance.
- Best for: Blogs and content publications where newsletter is also important

**Shopify**
- Requires: Shopify account ($29/month minimum)
- Setup: Create store, build or buy theme, configure products and payments
- Client experience: Shopify admin — excellent product management, orders, inventory
- Cost: $29–$299/month depending on plan
- Best for: Any e-commerce project

**Contentful**
- Requires: Contentful account, API key
- Setup: Define content model in Contentful, fetch via API in the frontend
- Client experience: Contentful web app — structured content editing
- Cost: Free tier (5 users, 25k records), paid above
- Best for: Marketing sites and web apps with structured content needs and multiple content editors

---

## 9. Hosting and Deployment

### Hosting Options Comparison

| Platform | Best for | Cost | Deploy method |
|---|---|---|---|
| **Vercel** | React, Next.js — **Pro plan ($20/month) required for commercial/client sites** | Pro: $20/month | GitHub integration (auto-deploy on push) or CLI |
| **Netlify** | Static sites, Decap CMS, form handling | Free tier generous | GitHub integration, drag-and-drop, or CLI |
| **GitHub Pages** | Simple static sites, no backend | Free | Push to gh-pages branch or GitHub Actions |
| **Shopify** | E-commerce only | Included in plan | Theme editor or GitHub integration |
| **Ghost Pro** | Ghost blogs | From $9/month | Managed — no deployment needed |

### Vercel Setup (recommended for React/Next.js)
```bash
# Install Vercel CLI
npm install -g vercel

# Deploy from project root
vercel

# Production deploy
vercel --prod

# Or: connect GitHub repo in Vercel dashboard for automatic deploys
```

**Vercel environment variables:**
- Set in Vercel dashboard → Project → Settings → Environment Variables
- Never commit `.env` files to GitHub
- Document required variables in README.md

### Netlify Setup (recommended for static sites with CMS)
```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
netlify deploy

# Production deploy
netlify deploy --prod

# Or: drag and drop build folder at app.netlify.com/drop
```

**Netlify form handling (free, no backend needed):**
```html
<form name="contact" netlify>
  <input type="hidden" name="form-name" value="contact">
  <!-- form fields -->
</form>
```

### Custom Domain Setup
1. Purchase domain (Namecheap, Google Domains, or Cloudflare)
2. In Vercel/Netlify dashboard: Add domain → follow DNS instructions
3. Update nameservers or add DNS records at domain registrar
4. SSL/HTTPS: Automatic on both Vercel and Netlify (Let's Encrypt)

### Handing Over a Live Vercel/Netlify Site
When transferring a deployed site to a client:
1. Add the client as a team member in the platform (or transfer project ownership)
2. Ensure the domain is registered in the client's name (not yours) if they're taking full ownership
3. Document login credentials and access in the README or a separate handoff doc
4. If you're maintaining the site long-term, keep the project under your account and add client as viewer only

---

## 10. Delivery Formats

Default delivery is always all project files. The format depends on project type and client needs.

### ZIP of Static Files
**When to use:** Simple sites, clients who host themselves or use their own provider, clients who need files uploaded to an existing hosting account.

**What to include:**
- All HTML, CSS, JS files
- All asset files (images, fonts, icons) — optimized
- README.md with setup instructions
- No `node_modules` folder
- No `.env` files

**How to package:**
```bash
# Create clean ZIP excluding unnecessary files
zip -r project-name.zip . -x "*.git*" -x "node_modules/*" -x ".env*" -x ".DS_Store"
```

### GitHub Repository
**When to use:** Projects that will be maintained, updated, or deployed via CI/CD. Any project using Vercel or Netlify with automatic deploys.

**Repository structure:**
```
project-name/
├── .gitignore          ← excludes node_modules, .env, .DS_Store
├── README.md           ← setup, deploy, update instructions
├── [source files]
└── [config files]
```

**Standard .gitignore:**
```
node_modules/
.env
.env.local
.DS_Store
dist/
.next/
```

**Transferring a repo to the client:**
1. Create the repo under your GitHub account during development
2. At handoff: Settings → Transfer repository to client's GitHub account
3. Or: give client maintainer access and they fork/clone
4. Document the transfer process in the README

### Live Deployed Site (Vercel/Netlify)
**When to use:** When Dereck is managing hosting for the client, or when the client wants a live URL they can share immediately.

**Handoff options:**
- **Dereck manages hosting:** Client pays Dereck, Dereck maintains the deployment. Add client as viewer in platform.
- **Client takes ownership:** Transfer project to client's Vercel/Netlify account. Walk them through the dashboard.
- **Client self-hosts:** Deliver GitHub repo + README with deploy instructions. Client sets up their own Vercel/Netlify account.

---

## 11. Handoff Standards

Every project delivery — regardless of format — must include these minimum components.

### README.md Template

```markdown
# [Project Name]

[One sentence describing the project and client.]

## Project Overview
- **Client:** [Client name]
- **Project type:** [e.g. Small business site, SaaS dashboard]
- **Stack:** [e.g. Vanilla HTML/CSS/JS]
- **Live URL:** [URL or "Not yet deployed"]
- **Repo:** [GitHub URL or "Local only"]
- **Designed by:** Dereck ([contact])
- **Delivered:** [Date]

## Design Decisions
### Colors
- Primary: [hex] — [token name]
- Accent: [hex] — [token name]
- Background: [hex]
- [etc.]

### Typography
- Display font: [Font name] — [Google Fonts URL]
- Body font: [Font name] — [Google Fonts URL]
- Base size: 16px, scale: [document the scale]

### Spacing
- Base unit: 4px
- Scale: 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 / 128px

## How to Run Locally
[For vanilla HTML:]
Open `index.html` in any browser. No build step required.

[For Node projects:]
\`\`\`bash
npm install
npm run dev
# Opens at http://localhost:5173 (Vite) or http://localhost:3000 (Next.js)
\`\`\`

## How to Deploy
[For Vercel:]
\`\`\`bash
npm install -g vercel
vercel --prod
\`\`\`
Or push to the main branch — auto-deploys via GitHub integration.

[For Netlify:]
Drag and drop the project folder to app.netlify.com/drop
Or push to main branch for automatic deploy.

## How to Update Content
[If no CMS:]
Edit the relevant HTML file directly. Content is in clearly commented sections.

[If Decap CMS:]
Go to [site URL]/admin and log in with your Netlify credentials.

[If Sanity:]
Go to [Studio URL] and log in with your Sanity credentials.

## File Structure
\`\`\`
[paste the file tree here]
\`\`\`

## Pages
| Page | File | URL |
|---|---|---|
| Home | index.html | / |
| About | about.html | /about |
| [etc.] | | |

## CMS / Content Notes
[Document any CMS setup, content model, or content editing notes here.]

## Environment Variables
[For projects with .env files:]
\`\`\`
VARIABLE_NAME=description of what this is
\`\`\`
Contact Dereck for actual values — never commit these to the repository.

## Known Issues / Future Work
- [Any known bugs or limitations]
- [Features planned for future phases]

## Contact
Built by Dereck. For questions or updates: [contact info]
```

### Design Decisions Summary

Include this in every handoff — either in the README or as a separate `DESIGN.md`:

```markdown
# Design System Summary — [Project Name]

## Color Tokens
| Token | Value | Use |
|---|---|---|
| --color-primary | #[hex] | Buttons, links, key UI |
| --color-accent | #[hex] | CTAs, highlights |
| --color-bg | #[hex] | Page background |
| [etc.] | | |

## Typography
| Role | Font | Size | Weight |
|---|---|---|---|
| Display / H1 | [Font name] | 3rem (desktop) / 2rem (mobile) | 700 |
| H2 | [Font name] | 2.25rem | 700 |
| Body | [Font name] | 1rem | 400 |
| [etc.] | | |

## Spacing Scale
4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 / 128px

## Breakpoints
- Mobile: 360px base
- Tablet: 768px
- Desktop: 1280px

## Components
| Component | Location | Variants |
|---|---|---|
| Button | components.css .btn | Primary, Secondary, Ghost |
| Card | components.css .card | Default, Featured |
| [etc.] | | |

## Accessibility Notes
- WCAG 2.2 AA compliant
- All contrast ratios verified
- Keyboard navigation tested
- Screen reader tested with [tool used]
```

### Pre-Handoff Final Checks

Run these before delivering anything to a client:

**Code quality:**
- [ ] HTML validates (no errors at validator.w3.org)
- [ ] No console errors in browser DevTools
- [ ] No broken links (test every nav item and CTA)
- [ ] All images load correctly
- [ ] Forms submit correctly and show success/error states
- [ ] All placeholder text replaced with real or draft copy

**Performance:**
- [ ] Images are WebP/AVIF format and appropriately sized
- [ ] Lighthouse score: Performance 80+, Accessibility 90+
- [ ] Page loads in under 3 seconds on a simulated mobile connection (Lighthouse)

**Responsive:**
- [ ] Tested at 360px, 768px, 1280px minimum
- [ ] No horizontal scroll at any breakpoint
- [ ] Touch targets are 44×44px minimum on mobile

**Accessibility:**
- [ ] Full accessibility checklist passed (see `references/accessibility.md`)
- [ ] Keyboard navigation tested end-to-end
- [ ] Focus states visible on all interactive elements

**SEO:**
- [ ] Unique page title on every page (under 60 characters)
- [ ] Unique meta description on every page (120–155 characters)
- [ ] One H1 per page with primary keyword
- [ ] All images have alt text and are WebP format
- [ ] LocalBusiness schema on homepage (for small business sites)
- [ ] sitemap.xml generated and linked in robots.txt
- [ ] Google Business Profile setup recommended to client (if small business)
- [ ] PageSpeed Insights mobile score 80+ confirmed

**Delivery package:**
- [ ] README.md complete and accurate
- [ ] Design decisions documented
- [ ] No node_modules, .env, or .DS_Store in the delivery package
- [ ] All fonts either self-hosted or imported via documented URL
- [ ] Client login credentials documented (if CMS or hosting account involved)
