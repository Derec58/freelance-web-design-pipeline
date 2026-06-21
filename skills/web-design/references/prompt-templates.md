# Prompt Templates Reference

This file contains reusable prompt templates for specific task types. Each template is ready to copy, paste, and adapt for a new project. Brackets `[like this]` indicate fields to fill in before using.

These templates are designed for Dereck to use when starting a new conversation or task with Claude. They are not instructions for Claude — they are tools for Dereck to get consistent, high-quality output quickly.

Read this file when Dereck asks for a reusable prompt, wants to start a specific type of task from scratch, or needs a structured starting point for a client project.

---

## Table of Contents
1. [Template 1 — High-Level Responsive Design Brief](#1-high-level-responsive-design-brief)
2. [Template 2 — Wireframes and Section Breakdown](#2-wireframes-and-section-breakdown)
3. [Template 3 — Full Design System and Responsive UI Spec](#3-full-design-system-and-responsive-ui-spec)
4. [Template 4 — HTML/CSS-Ready Responsive Layout](#4-htmlcss-ready-responsive-layout)
5. [Template 5 — Multiple Design Concepts for the Same Page](#5-multiple-design-concepts-for-the-same-page)
6. [Template 6 — Figma-Oriented Layout Description](#6-figma-oriented-layout-description)
7. [Template 7 — Audit and Improve an Existing Layout](#7-audit-and-improve-an-existing-layout)
8. [Template 8 — UX Research Report](#8-ux-research-report)
9. [Template 9 — Small Business Site Fast Brief](#9-small-business-site-fast-brief)
10. [Template 10 — Landing Page Brief](#10-landing-page-brief)
11. [Template 11 — SaaS Dashboard Brief](#11-saas-dashboard-brief)
12. [Template 12 — Content and Copy Brief](#12-content-and-copy-brief)
13. [How to Get the Best Results](#13-how-to-get-the-best-results)

---

## 1. High-Level Responsive Design Brief

**Use when:** You want Claude to propose IA, layouts, and visual direction for a new project. No code yet — just the full design plan.

```
You are a senior product/UI/UX designer working with me, Dereck, as a design partner.

Design a responsive [marketing site / web app / e-commerce site / blog] for: [business name].

Context
- Industry: [industry]
- Target audience: [describe audience — e.g. "local homeowners with little technical knowledge"]
- Primary goal: [e.g. "book a call", "request a quote", "start free trial"]
- Secondary goals: [e.g. newsletter signup, learn more, read case studies]
- Brand attributes: [e.g. friendly, premium, playful, minimalist, bold, trustworthy]
- Existing brand constraints: [colors, logo, typography if any — or "none yet"]
- Reference sites: [2–3 URLs and what specifically I like about each]
- Technical stack preference: [vanilla HTML/CSS/JS / Tailwind / React / no preference]
- CMS needed: [yes / no / unsure]
- Timeline: [e.g. 2 weeks]

Deliverables
1. Sitemap — top-level pages and key subpages, labeled Primary / Secondary / Footer / Utility
2. For each key page: responsive layout described section-by-section in plain language
   - For each section: purpose, key content, hierarchy, components used
   - How the layout adapts at mobile (360px), tablet (768px), and desktop (1280px)
3. Mini design system proposal:
   - Color tokens (primary, secondary, accent, background, surface, text, semantic)
   - Typography (font choices with justification, size scale, weights)
   - Core components (buttons, inputs, cards, nav, footer) with variants and states
4. Accessibility considerations (WCAG 2.2 AA): contrast, keyboard nav, focus states, semantic structure
5. Short rationale for key design decisions tied to user needs and business goals

Before starting:
- Classify the project type and state which preset you're using
- Suggest a research phase — ask what research exists and whether to generate a full research report first
- Ask me 3–5 clarifying questions if anything is ambiguous
- Then output in clear labeled sections. No code yet.
```

---

## 2. Wireframes and Section Breakdown

**Use when:** You already know the pages needed and want detailed layout and structure without visual design yet.

```
You are a senior UX designer working with me, Dereck, as a design partner.

Create wireframe-level responsive layouts (no visuals, no code) for these pages: [list pages].

Context
- Business: [brief description]
- Primary user: [who they are and what they need]
- Primary conversion goal: [what we want users to do]

For each page:
1. State the main user goal and primary business goal for that page
2. Define the content flow in order — section 1, section 2, etc.
   For each section:
   - Name and purpose
   - Key content elements
   - Recommended layout pattern (e.g. "two-column text + image", "three feature cards", "sticky sidebar")
   - Suggested copy placeholders (headline theme, subheading theme, CTA label)
3. Describe how the layout adapts for:
   - Mobile (360px): single column, stacked elements, sticky CTAs, nav behavior
   - Tablet (768px): columns, card layouts, side-by-side elements
   - Desktop (1280px): grid usage, max-width, additional breathing room
4. Call out accessibility requirements per section (tap targets, form labels, skip links, contrast-sensitive areas)

Output as structured text with headings and bullets. No code. No visual polish.
A designer should be able to translate this directly into wireframes.
```

---

## 3. Full Design System and Responsive UI Spec

**Use when:** You want a complete design system — tokens, components, behavior — ready for implementation.

```
You are a design systems expert and front-end–aware UI designer working with me, Dereck.

Based on this project:
[Paste brief, IA, or earlier wireframe output here]

Produce a complete mini design system and responsive UI spec ready for implementation.

Design Tokens
- Colors: name + hex + role + intended use for each token
- Typography: font families (with justification), weights, sizes, line heights for headings, body, captions, buttons
- Spacing scale: 4/8/12/16/24/32/48/64/96/128px — note where each is typically used
- Border radius, shadows, borders: document the set for cards, buttons, inputs

Components
For each core component (buttons, inputs, cards, nav, modals, accordions, tooltips, alerts, tabs, footer):
- Structure and content slots
- Visual style
- All variants (primary/secondary/ghost, card types, etc.)
- All states: default, hover, active, focus, disabled, error, loading, empty
- Accessibility notes: touch target size, focus visibility, ARIA needs

Responsive UI Spec
- For each major page/template: how components arrange at mobile, tablet, desktop
- Breakpoint-specific changes: columns, stacking order, hidden vs collapsed, type scale adjustments
- Header/nav behavior at each breakpoint
- Form layout at each breakpoint
- Tables or data-heavy components — how to make them usable on mobile

Accessibility
- WCAG 2.2 AA assumed throughout
- Contrast expectations for every color combination
- Focus indicators specification
- Keyboard navigation patterns
- ARIA patterns for complex components (modals, accordions, dropdowns)

Output in clearly labeled sections ready to copy into documentation.
```

---

## 4. HTML/CSS-Ready Responsive Layout

**Use when:** You want production-ready code for a specific page.

```
You are a senior front-end engineer and UI designer working with me, Dereck.

Generate semantic HTML and modern CSS for a responsive [page type — e.g. "small business homepage"] for [business/product name].

Context
- Business: [what they do, who they serve]
- Primary conversion: [e.g. phone call, quote request, signup]
- Brand: [3–5 adjectives + key colors + font preferences or "your choice"]
- Any specific components needed: [e.g. gallery, testimonials, contact form]

Stack
First, recommend a stack with full tradeoff explanation (vanilla HTML/CSS/JS vs Tailwind vs React).
Then implement using the recommended stack.

Code requirements
- Semantic HTML5: header, nav, main, section, article, aside, footer
- Mobile-first CSS with breakpoints at 360px (base), 768px, 1280px
- CSS custom properties for all design tokens (colors, typography, spacing)
- Responsive typography and spacing using the 4px base scale
- Comments explaining major sections and key layout decisions

Accessibility
- Visible focus states for all interactive elements
- Sufficient color contrast (4.5:1 normal text, 3:1 large text and UI)
- Labels and ARIA attributes for nav, landmarks, forms, and complex components
- Skip to main content link
- prefers-reduced-motion media query for all animations

Delivery
- Outline the layout sections briefly first
- Then output complete HTML and CSS in separate, clearly labeled code blocks
- Include a stack recommendation block before the code
```

---

## 5. Multiple Design Concepts for the Same Page

**Use when:** You want to explore different visual and layout directions before committing to one.

```
You are a senior product designer exploring multiple design directions with me, Dereck.

The content and structure below must stay roughly the same, but the layout and visual design should differ significantly across concepts.

Content / structure to use:
[Paste structured content, section list, or JSON-like description of the page]

Task: Propose exactly 3 distinct responsive design concepts for this page.

For each concept:
1. Name the concept and describe the design vibe in one sentence
   (e.g. "Editorial Brutalism — high contrast, bold type, raw grid")
2. Describe the layout for mobile, tablet, and desktop:
   - Section order and grid patterns
   - Placement of key elements (hero, features, testimonials, CTAs)
   - What changes between breakpoints
3. Define a palette direction and typography direction for this concept
4. Call out 2–3 specific things that make this concept visually distinct from the other two
5. Note any accessibility considerations specific to this style
   (e.g. contrast risks on dark backgrounds, motion guidelines)

Output the three concepts as clearly separated sections.
After all three, ask me which direction to develop further.
Do not develop any further until I choose.
```

---

## 6. Figma-Oriented Layout Description

**Use when:** The design will be built in Figma and you need a detailed, Figma-ready spec.

```
You are a senior product designer describing designs for Figma handoff.
Work with me, Dereck, as a design partner.

Design a responsive [site/app type] for [client/product].

Context
- Business: [what they do, who they serve]
- Brand: [adjectives, colors, fonts or "your choice"]
- Pages needed: [list pages]

For each key page, describe the layout in Figma terms:

Frames
- Frame name and size for desktop (1440px), tablet (768px), mobile (390px)
- Constraints for key elements

Auto Layout
- For each section and component: direction, gap, padding (T/R/B/L), alignment, resizing behavior
- Which containers use Auto Layout vs absolute positioning

Components
- List which elements should be components vs one-off instances
- For each component: name (ComponentName/Variant/State format), variants, exposed properties
- Which components are shared across pages

Spacing and Grid
- Grid columns, gutters, and margins at each breakpoint
- Container max-width
- Specific spacing values between sections (from the 4px scale)

Interactions (for prototype)
- Which elements trigger interactions (On Click, On Hover)
- What happens (Navigate to, Open overlay, Scroll to)
- Animation type and duration

Output everything so a Figma designer can build the frames and components step-by-step
without guessing at any values.
```

---

## 7. Audit and Improve an Existing Layout

**Use when:** You have an existing site or design and want a structured critique and improvement plan.

```
You are a senior UI/UX and front-end expert working with me, Dereck.

I'm going to share an existing layout [description / code / screenshots].
[Paste or describe the existing site/design here]

Step 1 — Audit
Classify the project type and primary goals.
Run a structured audit across these five areas. Group issues by severity: High / Medium / Low.
- IA and navigation
- Visual hierarchy and clarity
- Forms and flows
- Accessibility and responsiveness (WCAG 2.2 AA)
- Performance and content (high-level)

Step 2 — Improvement Plan
Propose a prioritized list of improvements in order of impact.
For each improvement: what to change, why, and what the expected outcome is.

Step 3 — Revised Spec
For the highest-priority improvements, produce a revised wireframe or layout spec.
If code changes are needed, describe them before writing any code —
then output the revised code with comments explaining each change.

Run the generic-pattern self-check before finalizing any revised design.
Output the check result explicitly.
```

---

## 8. UX Research Report

**Use when:** You need a full UX research report for a new project — generated from assumptions or interpreted from existing data.

```
You are a senior UX researcher working with me, Dereck, as a research partner.

Generate a UX research report for: [project name / business type].

[Choose one:]
A) No research exists — generate a full assumption-based report
B) I have existing research — [paste raw notes, discovery call description, or upload file]

Before generating the report, ask:
1. Do you want the standard structure (Goals → Personas → Findings → Recommendations)
   or a custom structure for this project?
2. [If B] What format is the existing research in and what decisions should it inform?

Report structure (standard):
1. Research Goals — what decisions this research informs
2. Methods used — or "Assumption-based proto-research" if no real research exists
3. User Personas — 2–3 proto-personas with goals, frustrations, key questions, design implications
4. Jobs-to-Be-Done — 3–5 JTBD statements with derived design requirements
5. Key Findings — top 5–7 insights, clearly labeled as confirmed or assumed
6. Design Requirements — derived from findings, labeled Must Have / Should Have / Nice to Have
7. Recommendations — prioritized list of design opportunities
8. Open Questions — what we still don't know and how to find out

Label all assumption-based content clearly — never present assumptions as confirmed research.
Output as a clean markdown document.

After the report, produce the Research-to-Design Bridge:
- Top insights (bullet list)
- Design requirements (derived from insights)
- Prioritized opportunity list
Then ask: "Do you want to add, remove, or re-order anything before I move to wireframes?"
```

---

## 9. Small Business Site Fast Brief

**Use when:** You need to move quickly on a simple local or trade business site. Streamlined brief for common project type.

```
You are a senior web designer working with me, Dereck.

Design a responsive small business website for: [business name].

Business info
- Type: [e.g. plumber, photographer, landscaper, tile installer, salon]
- Location: [city/region]
- Primary conversion: [phone call / quote form / booking link]
- Unique selling point: [what makes them different — or "unknown, help me define this"]
- Brand adjectives: [3–5 words]
- Existing brand assets: [logo yes/no, colors yes/no, photos yes/no]

Pages needed: [Home, Services, Gallery/Portfolio, About, Contact — adjust as needed]

Deliverables (in order)
1. Homepage section breakdown (mobile-first)
2. Component list with priority order
3. Mini design system (color tokens, font pairing, spacing)
4. Stack recommendation with tradeoff explanation
5. Implementation notes — semantic HTML structure, accessibility requirements

Prioritize:
- Phone/CTA visible above fold on mobile
- Real or realistic photo placeholders (no stock photo descriptions)
- Trust signals (years in business, reviews, license/certifications)
- Fast to build — balance speed with genuine creative decisions

Run the generic-pattern self-check before finalizing. Report the result.
```

---

## 10. Landing Page Brief

**Use when:** You need a focused, conversion-optimized standalone landing page.

```
You are a senior conversion-focused web designer working with me, Dereck.

Design a responsive landing page for: [product / service / offer name].

Context
- Traffic source: [paid ads / email / organic / social — affects headline strategy]
- Primary conversion goal: [e.g. "free trial signup", "book a demo", "download guide"]
- Target audience: [who they are, what they care about, their main objection]
- Key value proposition: [what makes this offer worth acting on now]
- Offer details: [what they get, any urgency or deadline]
- Brand: [adjectives + colors + fonts or "your choice"]
- Ad headline (if paid traffic): [paste the headline so we can match message]

Requirements
- One primary CTA only — no competing actions
- No persistent site navigation — logo only
- CTA appears minimum 3 times (hero, mid-page, final section)
- Remove all exits (no social links, no nav links to other pages)
- Address top objection explicitly in the FAQ or copy

Deliverables
1. Page structure — sections in order with purpose and content for each
2. Visual direction — 3 concepts, then develop the chosen one
3. Copy draft — H1, subheading, CTA label, section headings, FAQ questions
4. Stack recommendation with tradeoff explanation
5. Accessibility and implementation notes

Run the generic-pattern self-check before finalizing.
```

---

## 11. SaaS Dashboard Brief

**Use when:** You're designing a web app or dashboard — logged-in experience, not a marketing site.

```
You are a senior product designer specializing in SaaS and dashboard design,
working with me, Dereck, as a design partner.

Design a responsive SaaS dashboard for: [product name].

Context
- Product: [what it does in one sentence]
- Primary users: [role, technical level, how often they use it]
- Top 3 tasks users perform: [list them]
- Key metrics or data the dashboard must display: [list them]
- User roles (if multiple): [e.g. Admin, Team Member, Viewer]
- Authentication: [email/password / SSO / both]
- Existing design system or brand: [yes/no — if yes, describe]

Deliverables
1. App structure — page/view list with nav hierarchy
2. Dashboard layout — KPI cards, charts, tables, nav pattern
3. Component list — prioritized, with variants and states for each
4. Empty states — what users see before any data exists
5. Auth flow spec — login, signup, forgot password
6. Mini design system — tokens, typography, component states
7. Accessibility requirements — keyboard nav, focus management, live regions for async updates
8. Stack recommendation with tradeoff explanation (React + Tailwind is likely right — confirm why)

Design for information density and keyboard efficiency.
Every async action must have a loading, success, and error state.
Run the generic-pattern self-check before finalizing.
```

---

## 12. Content and Copy Brief

**Use when:** You need draft copy, UX writing, or content strategy for a specific page or section.

```
You are a senior UX writer and content strategist working with me, Dereck.

Write draft copy for: [page name / section name / component].

Context
- Business: [what they do, who they serve]
- Audience: [who is reading this — their role, context, knowledge level]
- Brand voice: [adjectives — e.g. "friendly, direct, no jargon"]
- Primary goal of this copy: [what it should make the reader think, feel, or do]
- Word limit or constraints: [e.g. "hero headline under 8 words", "CTA under 4 words"]

Produce
1. 3 headline options (H1 or section heading) — each with a different angle
2. 1–2 subheading options per headline
3. Body copy (if needed) — short paragraphs, bullet-friendly, scannable
4. 2–3 CTA options — verb + outcome format
5. Error and success message copy (if this is a form or interactive element)

Label all output as [DRAFT COPY].
Explain the strategy behind each option briefly — what angle it takes and why.
After drafts, recommend which option best serves the goal and explain why.
```

---

## 13. How to Get the Best Results

### General rules for prompting this skill

**1. Always include brand adjectives.**
The single biggest driver of non-generic output is brand personality. "Bold, industrial, no-nonsense" produces a different design than "warm, approachable, community-driven." Include at least 3 adjectives in every brief.

**2. Always include reference sites.**
Point to 2–3 sites you like and say specifically what you like — the layout, the typography, the color approach, the density. References constrain the solution space in productive ways.

**3. Specify what to avoid.**
"Avoid generic SaaS layouts and default blue/purple gradients" is a powerful constraint. Add anything you've seen too much of or that the client has explicitly rejected.

**4. State the fidelity level you want.**
- "Early concept" → IA and wireframes only, no code
- "Ready to build" → full spec + code
- "Quick options" → 3 visual directions, no deep spec
- "Figma spec" → Figma-oriented detail level

**5. Give Claude permission to push back.**
Add "If any of my constraints conflict with best practices, tell me and propose an alternative" to any brief. This activates the conflict resolution behavior.

**6. Use iterative refinement.**
Don't try to get everything in one prompt. First prompt: direction. Second prompt: "push this further in [specific dimension]." Third prompt: code or spec. This is how you teach Claude your taste over time.

**7. Paste in your own examples.**
If you have a spec, wireframe, or design you're proud of, paste it in and say "match this level of detail and reasoning for the new project." Claude will calibrate to your style.

**8. Use "concise mode" when you need speed.**
Add "short version — bullet points only, 1–3 bullets per step" to any template to get a compressed output that still respects the process.

### Anti-generic prompt additions

Add any of these to a template to push against generic output:

```
Do not default to typical AI/Bootstrap-style layouts or generic blue/purple gradients.
Avoid overused hero layouts (logo row + 3 identical feature cards) unless I ask for them.
Make deliberate, opinionated choices in typography, color, and layout.
Explain each major visual decision in brand- and audience-specific terms — not generic buzzwords like "modern" or "clean."
```

```
Before finalizing, run the generic-pattern self-check and report the result.
If any pattern fails, revise and explain what you changed.
```

```
Propose exactly 3 distinct visual directions before committing to one.
Each must have a clear name, a one-sentence vibe, and 3–4 specific layout moves.
Do not develop any direction further until I choose.
```

---

## 14. Project Scoping Template

**Use when:** You've completed a discovery call and need to turn the client's answers into a clear project scope, timeline, and proposal.

```
You are a senior web designer and project manager working with me, Dereck.

I just completed a discovery call with a potential client. Here's what I learned:

Business: [paste discovery call notes or questionnaire answers]

Based on this, help me:

1. CLASSIFY the project type (use the presets from the skill)

2. SCOPE the project:
   - Recommended pages (list each with a one-line description)
   - Key features and components needed
   - CMS recommendation (yes/no, which one, why)
   - Stack recommendation with tradeoff explanation
   - What's explicitly NOT included (to prevent scope creep)

3. ESTIMATE the timeline:
   - Milestone 1: Research + wireframes (X weeks)
   - Milestone 2: Design review (X weeks)
   - Milestone 3: Development + launch (X weeks)
   - Total: X weeks from deposit to delivery

4. PRICE the project:
   - Base range given the scope
   - Any factors that could push it higher or lower
   - Payment structure recommendation

5. DRAFT a proposal email I can send within 24 hours

Flag anything from the discovery notes that's unclear or could cause scope
creep if not addressed upfront.
```

---

## 15. Cold Outreach Prep Template

**Use when:** You've identified a prospect and want Claude to help you research them and prepare a personalized outreach message before contacting them.

```
You are helping me, Dereck, prepare a cold outreach message for a potential
web design client.

Prospect info:
- Business name: [name]
- Business type: [e.g. plumber, photographer, restaurant]
- Location: [city]
- Current website: [URL or "none"]
- How I found them: [Google Maps / Yelp / Instagram / driving by / etc.]
- What I noticed: [specific issue — e.g. "site doesn't load on mobile,"
  "no website," "doesn't rank for [keyword] in [city]"]
- Outreach channel: [email / phone / Instagram DM / text / in person]

Using the outreach scripts from the `client-acquisition` skill as a base:

1. Write a personalized outreach message for this specific business and channel.
   Make it specific to what I noticed — not generic.

2. If this is an email: suggest 3 subject line options.

3. Note 1–2 additional observations I should make before reaching out
   (what else to check on their site, Google listing, or social).

4. Suggest the best time/approach for this channel and business type.

Keep the message short, warm, and specific. Lead with the observation,
not the pitch.
```
