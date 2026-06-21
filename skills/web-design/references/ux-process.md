# UX Process Reference

This file covers the full Double Diamond process in detail, UX heuristics enforcement, information architecture and navigation rules, content strategy, and Figma output standards. Read this file during discovery, IA planning, wireframing, content writing, and Figma spec work.

---

## Table of Contents
1. [Double Diamond — Detailed Steps](#1-double-diamond--detailed-steps)
2. [Discovery Questionnaires](#2-discovery-questionnaires)
3. [UX Heuristics — Enforcement Rules](#3-ux-heuristics--enforcement-rules)
4. [Information Architecture and Navigation](#4-information-architecture-and-navigation)
5. [Layout and Responsive Behavior](#5-layout-and-responsive-behavior)
6. [Content Strategy and UX Writing](#6-content-strategy-and-ux-writing)
7. [Figma Output Standards](#7-figma-output-standards)

---

## 1. Double Diamond — Detailed Steps

Always state which step you are in at the start of each response. The process is sequential but not rigid — revisit earlier steps when new information changes the picture.

### Discover
Goal: understand context deeply before touching layout or visuals.

- Run the discovery questionnaire for the project type (see Section 2)
- Always trigger the research phase before moving forward — read `ux-research-generative.md`
- Synthesize findings into a brief summary: what you know, what you're assuming, what's still unknown
- Do not proceed to Define until business goals, user goals, and constraints are clear

### Define
Goal: frame the problem so every design decision has a clear reason.

Output these four things in order:
1. **Problem statement** — one sentence, plain language. Format: "Help [user] [accomplish goal] so they can [outcome]." Example: "Help busy homeowners quickly find and trust a local plumber so they can book a service call without anxiety."
2. **Key user journeys** — 3–5 journeys, each as a short linear sequence. Example: "New visitor → understands offer → sees proof → contacts."
3. **Page/flow priority list** — ordered from most to least critical. Flag which pages are MVP vs nice-to-have.
4. **Sitemap** — output as an ordered list. Label each item as Primary Nav, Secondary Nav, Footer, or Utility (e.g. 404, privacy policy).

### Develop
Goal: explore solutions before committing to one.

Steps in order:
1. Propose IA and page hierarchy (confirm with the user before going further)
2. Write wireframe-level descriptions — sections in order, layout notes, content priorities. No visual polish, no color, no font choices yet.
3. Propose **exactly 3 distinct visual directions**. For each: a name, a one-sentence vibe, 3–4 key layout moves, and a rough palette/type direction. Label them clearly (e.g. Direction A / B / C).
4. Wait for the user to choose a direction before developing further.
5. Once direction is chosen, propose full component set: nav, hero, cards, CTAs, forms, modals, footers, etc.
6. For any section where two approaches are equally valid, offer a variant and explain the tradeoff.

### Deliver
Goal: produce a complete, implementation-ready spec.

Output in this order:
1. **High-fidelity design spec** — spacing scale, typography stack, color token usage, component states (default, hover, active, focus, disabled, error)
2. **Developer-ready guidance** — semantic HTML structure per page, ARIA requirements, responsive breakpoints, interaction behaviors, animation specs
3. **Anti-pattern self-check** — run before finalizing (read `references/anti-patterns.md`)
4. **Delivery checklist** — see below

**Standard delivery checklist:**
- [ ] All text meets 4.5:1 contrast ratio (3:1 for large text)
- [ ] All interactive elements have visible focus states
- [ ] Keyboard navigation works for all flows
- [ ] Skip to content link present
- [ ] Semantic HTML structure confirmed (header, nav, main, section, footer)
- [ ] ARIA labels on all non-text interactive elements
- [ ] Forms have labels, inline validation, and clear error messages
- [ ] All images have alt text (or aria-hidden if decorative)
- [ ] Mobile layout tested at 360px, 480px
- [ ] Tablet layout tested at 768px
- [ ] Desktop layout tested at 1024px, 1280px, 1440px
- [ ] Core Web Vitals considered: lazy-load images, optimize fonts, minimal JS
- [ ] prefers-reduced-motion respected for all animations
- [ ] Anti-pattern self-check complete (read `references/anti-patterns.md`)

---

## 2. Discovery Questionnaires

Use the appropriate questionnaire based on project type. If multiple types apply, combine relevant sections.

### All Projects — Universal Questions
Always ask these regardless of project type:
1. What does the business do and who is it for? (one sentence)
2. What is the single most important action a visitor should take? (primary conversion)
3. What are 1–2 secondary actions? (newsletter, download, learn more)
4. Who is the target user? (role, context, technical level, device they'll likely use)
5. What are the user's biggest questions or objections when they land on the site?
6. Are there existing brand guidelines? (logo, colors, fonts — yes/no, and if yes, share them)
7. What 2–3 competitor or reference sites does the client like, and what specifically do they like about each?
8. What do they hate about those or other sites?
9. What is the technical stack or preference? (or "no preference")
10. Will users need to edit content after handoff? (determines CMS recommendation)
11. What is the timeline and budget range?

### Marketing / Branding Sites
Additional questions:
- What is the brand personality in 3–5 adjectives?
- Is there existing content (copy, images) or does it need to be created?
- Are there multiple audiences, or one primary audience?
- What pages are needed at launch vs later?

### SaaS Dashboards / Web Apps
Additional questions:
- What are the 3 most common tasks a logged-in user performs?
- Is there existing data or are we designing with placeholder data?
- What are the key metrics or KPIs the dashboard must display?
- Are there user roles with different permissions or views?
- What is the authentication flow? (sign up, sign in, forgot password)

### E-commerce
Additional questions:
- How many products / product categories?
- What payment processor? (Stripe, PayPal, etc.)
- Is there inventory management or fulfillment complexity?
- What are the most common reasons users abandon carts for this type of product?
- Are there trust signals needed? (reviews, certifications, guarantees)

### Small Business Sites (trades, services, local businesses)
Additional questions:
- Does the business serve a specific geographic area? (affects local SEO)
- What is the primary conversion — phone call, form submission, or booking?
- Does the business have photos/portfolio work to showcase?
- Are there testimonials or reviews available?
- Does the site need a booking or scheduling system?

### Landing Pages (standalone)
Additional questions:
- What is the traffic source? (paid ads, email, organic — this affects headline strategy)
- Is there a single CTA or multiple?
- Is there a deadline or offer expiration?
- What objections must the page overcome to convert?

### Blog / Content Sites
Additional questions:
- Who is writing the content — the client or a team?
- What categories or topics will be covered?
- Is there a newsletter or subscription element?
- How important is SEO to this project?

### Redesigns / Audits
Additional questions:
- What is broken or underperforming about the current site?
- Are there analytics showing where users drop off?
- What must stay the same? (brand, content, existing URLs)
- What is the biggest complaint from current users?

---

## 3. UX Heuristics — Enforcement Rules

Apply these heuristics to every design. For each key screen, explicitly state how the design satisfies each one. Do not skip this step.

### 1. Clarity Over Cleverness
- Content and labels must be immediately understandable in plain language
- No clever or cute labels that require interpretation (e.g. "Let's Talk" is weaker than "Contact Us")
- CTAs must state the verb and outcome: "Get a free quote," "Start your free trial," not "Go" or "Submit"
- Enforcement check: would a first-time visitor understand every label without context?

### 2. Visual Hierarchy
- One primary action per page — everything else is secondary
- Strong headings that state what the business does and for whom
- Progressive disclosure: show the most important information first, details on demand
- Enforcement check: cover the page with your hand, reveal it slowly — is the H1 the clearest thing?

### 3. Consistency
- Identical spacing, typography, colors, and interaction patterns across all pages
- Identical elements must behave identically — if a blue button submits a form on page 1, it must not navigate on page 2
- Component variants must have clear rationale — do not introduce a new button style without a documented reason
- Enforcement check: list every interactive element type and confirm each has exactly one behavior

### 4. Feedback
- Every button, form, and async action must show clear status
- Required states for all interactive elements: loading, success, error, empty
- Form errors must be specific ("Enter a valid email address") not generic ("Invalid input")
- Enforcement check: trace every user action — what does the UI show at each step?

### 5. Forgiveness
- Easy undo/exit on every destructive or irreversible action
- No dead ends — every error state must have a recovery path
- Forms must not clear on error; preserve what the user typed
- Enforcement check: what is the worst thing a user can accidentally do, and how do they recover?

### 6. Recognition Over Recall
- Show users available options; do not make them remember hidden rules or states
- Navigation labels must be visible at all times on desktop; accessible at one tap on mobile
- Filters, sort options, and actions must be visible, not hidden behind unlabeled icons
- Enforcement check: can a user complete every core task without reading documentation?

---

## 4. Information Architecture and Navigation

Design IA and navigation before touching any visual design. Output sitemaps and nav structures as ordered lists with role labels.

### Sitemap Format
```
Primary Nav:
  1. Home
  2. Services
  3. About
  4. Pricing
  5. Blog
  6. Contact

Secondary Nav (in header or footer):
  - Case Studies
  - FAQ

Footer:
  - Privacy Policy
  - Terms of Service
  - Sitemap

Utility:
  - 404
  - Thank You (post-form)
  - Search Results
```

### Navigation Rules
- **5–7 top-level items maximum** for simple sites. More than 7 requires justification.
- **No deep nesting** unless the information architecture genuinely requires it (e.g. large e-commerce with many categories)
- **Descriptive, non-cute labels**: "Pricing" not "Plans," "Blog" not "Insights," "Contact" not "Let's Chat" — unless brand voice strongly warrants it
- **Persistent header and footer** across all pages — no exceptions
- **Mobile nav**: hamburger menu is acceptable but must be keyboard accessible and screen-reader announced. Always include a close button and focus trap.
- **Active state**: current page must be visually indicated in the nav

### Grouping Logic
Group pages by user mental model, not internal business structure:
- "What we do" → Services, Products, Features
- "Why trust us" → About, Team, Case Studies, Testimonials
- "What it costs" → Pricing, Plans
- "Learn more" → Blog, Resources, FAQ
- "Get in touch" → Contact, Book a Call

---

## 5. Layout and Responsive Behavior

Always design mobile-first. Describe how each key page reflows at mobile, tablet, and desktop.

### Grid System
- **Mobile**: 1–2 column grid, 16px gutters, 16px page margins
- **Tablet**: 4–6 column grid, 24px gutters, 32px page margins
- **Desktop**: 12-column grid, 24–32px gutters, auto margins with max-width container

### Spacing Scale
Use this scale for all padding, margin, and gap values. Do not invent arbitrary values.
```
4px   — micro spacing (icon gaps, tight inline elements)
8px   — small (internal component padding)
12px  — small-medium
16px  — base (default padding, small gaps)
24px  — medium (section internal spacing)
32px  — large (component separation)
48px  — XL (section separation on mobile)
64px  — 2XL (section separation on tablet)
96px  — 3XL (section separation on desktop)
128px — 4XL (hero padding, major section breaks)
```

### Breakpoints
```
360px  — small mobile (minimum supported)
480px  — large mobile
768px  — tablet
1024px — small desktop / large tablet landscape
1280px — desktop
1440px — large desktop
1920px — wide (max-width container, centered)
```

### Responsive Patterns Per Layout Type
**Hero sections**
- Mobile: full-width, stacked (text above image or text only), CTA full-width button
- Tablet: side-by-side or large text with background image
- Desktop: generous padding, max-width contained, strong typographic scale

**Navigation**
- Mobile: hamburger menu, full-screen or slide-in drawer, large tap targets (min 44×44px)
- Tablet: condensed horizontal nav or hamburger depending on item count
- Desktop: full horizontal nav, possible sticky behavior

**Card grids**
- Mobile: single column
- Tablet: 2 columns
- Desktop: 3–4 columns depending on content density

**Forms**
- Mobile: single column, full-width inputs, large labels above fields
- Tablet+: can introduce 2-column layout for short fields (first/last name)
- Always: label above field (never placeholder-only), inline validation

**Tables and data-heavy components**
- Mobile: horizontal scroll with sticky first column, or card-based alternative layout
- Never hide critical data at mobile — if it doesn't fit, restructure the component

### Max-Width Container
Default: 1280px centered with auto horizontal margins. Adjust per project if needed. Always document the chosen max-width in the design system spec.

---

## 6. Content Strategy and UX Writing

Claude provides content strategy and drafts example copy as part of every layout — not just boxes and placeholders.

### Voice and Tone Defaults
- Concise, concrete, and scannable — no filler phrases
- Active voice — "Get a quote" not "A quote can be requested"
- Match brand adjectives provided in discovery — these override defaults
- Avoid jargon unless the audience is technical and expects it

### Page Structure Rules
**H1** — states what the business does and who it's for. Format: "[What you do] for [who]." Example: "Custom tile work for Sacramento homeowners."

**Hero subheading** — expands on the H1 with the key benefit or differentiator. 1–2 sentences maximum.

**Section headings (H2)** — descriptive and outcome-focused. "Why clients choose us" not "About."

**Body copy** — short paragraphs (2–3 sentences max), bullet lists for features, plain language throughout.

### CTA Rules
- **Primary CTA**: verb + outcome. Examples: "Get a free quote," "Start your free trial," "Book a call today."
- **Secondary CTA**: lower commitment. Examples: "See our work," "Learn how it works," "Download the guide."
- Never use: "Submit," "Click here," "Learn more" without context, "Go."
- Every page has one primary CTA. Secondary CTAs are allowed but must be visually subordinate.

### Form UX Rules
- Ask only necessary fields — every field added reduces conversion
- Group related fields visually
- Label above every field — never placeholder-only
- Inline validation: validate on blur, not on submit-only
- Error messages: specific and actionable ("Your email must include @" not "Invalid email")
- Success state: confirm what happens next ("We'll be in touch within 1 business day")

### Draft Copy
For every layout spec, Claude drafts:
- H1 and hero subheading
- CTA label(s)
- Section headings
- 1–2 feature/benefit bullet sets
- Form field labels and placeholder hints
- Error and success message examples

Mark all draft copy clearly as `[DRAFT COPY]` so it is never confused with final content.

---

## 7. Figma Output Standards

When the user asks for Figma-oriented output, use high detail. Always include the following for every frame and component.

### Frame Specifications
```
Frame name: [Page] / [Breakpoint]  e.g. "Home / Desktop"
Width: [exact px]
Height: [hug contents or fixed px]
Breakpoints to create: 360, 768, 1280 (minimum). Add 1440 if needed.
```

### Auto Layout Specifications
For every section and component that uses Auto Layout, specify:
- **Direction**: Horizontal or Vertical
- **Spacing**: gap value in px (from spacing scale)
- **Padding**: top / right / bottom / left in px
- **Alignment**: start, center, end, space-between
- **Resizing**: Fixed, Hug, or Fill

Example:
```
Component: Primary Button
Auto Layout: Horizontal
Padding: 12px top / 24px right / 12px bottom / 24px left
Gap: 8px (between icon and label if icon present)
Alignment: Center
Resizing: Hug width, Fixed height 48px
```

### Component Specifications
For every component, specify:
- **Component name** (use consistent naming: ComponentName/Variant/State)
- **Variants**: list all (e.g. Button/Primary/Default, Button/Primary/Hover, Button/Primary/Disabled)
- **Properties**: which properties are exposed (text, icon, color, size)
- **Which elements are components** vs one-off instances — flag this explicitly

### Naming Convention
```
Frames:     PageName/Breakpoint          (e.g. Home/Desktop)
Components: ComponentName/Variant/State  (e.g. Card/Featured/Default)
Layers:     Descriptive, no "Frame 47"  (e.g. "Hero Section", "Nav Container")
Colors:     Use token names             (e.g. color/primary/500)
Text:       Use style names             (e.g. type/heading/h1)
```

### Interaction Notes
For any element that should be prototyped, specify:
- Trigger: On Click / On Hover / On Focus
- Action: Navigate to / Open overlay / Scroll to
- Animation: Instant / Dissolve / Smart Animate, duration in ms
- Example: "Mobile nav hamburger: On Click → Open overlay (nav drawer) → Smart Animate 200ms ease-out"

### Prototype Flow Notes
Describe which screens should be connected in a prototype flow and in what order. Example:
```
Flow: New visitor conversion
1. Home / Desktop
2. Services / Desktop (via nav)
3. Contact / Desktop (via CTA)
4. Thank You / Desktop (via form submit)
```
