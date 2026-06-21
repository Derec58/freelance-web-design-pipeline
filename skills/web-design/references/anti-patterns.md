# Anti-Patterns Reference

This file defines what to avoid, how to self-check before finalizing any design, and how to handle conflict when a client requests something that violates best practices. Read this file before finalizing any design output and during any audit.

The self-check at the bottom of this file is mandatory before every final delivery.

---

## Table of Contents
1. [Generic Design Anti-Patterns](#1-generic-design-anti-patterns)
2. [AI Fingerprint Anti-Patterns](#2-ai-fingerprint-anti-patterns)
3. [Layout and Composition Anti-Patterns](#3-layout-and-composition-anti-patterns)
4. [Typography Anti-Patterns](#4-typography-anti-patterns)
5. [Color Anti-Patterns](#5-color-anti-patterns)
6. [Navigation Anti-Patterns](#6-navigation-anti-patterns)
7. [UX and Interaction Anti-Patterns](#7-ux-and-interaction-anti-patterns)
8. [Accessibility Anti-Patterns](#8-accessibility-anti-patterns)
9. [Performance Anti-Patterns](#9-performance-anti-patterns)
10. [Content and Copy Anti-Patterns](#10-content-and-copy-anti-patterns)
11. [Mobile Anti-Patterns](#11-mobile-anti-patterns)
12. [Pre-Delivery Self-Check](#12-pre-delivery-self-check)
13. [Conflict Resolution Playbook](#13-conflict-resolution-playbook)

---

## 1. Generic Design Anti-Patterns

These are the most common failure modes — the output that makes a site look like it was assembled from a template with no thought given to the specific business, audience, or context.

### The Default SaaS Hero Formula
**Pattern:** Top nav + centered headline + two buttons + logo strip of client logos + three identical feature cards in a row.
**Why it fails:** It's been used so many times it communicates nothing distinctive. The visitor's brain pattern-matches it to "generic software product" and disengages.
**Fix:** Break at least two of these conventions. Offset the hero text, use an asymmetric layout, lead with a bold visual instead of a logo strip, make the three cards do different things visually.

### Generic Gradient Backgrounds
**Pattern:** Purple-to-blue or blue-to-purple gradient as the primary hero or page background.
**Why it fails:** It has become the universal signal for "AI startup" or "generic SaaS." It communicates nothing about the specific brand.
**Fix:** If a gradient is right for the brand, build it from the actual brand colors and give it a specific mood. Mesh gradients, angular gradients, or subtle tints are more distinctive than linear blue-to-purple.

### Identical Feature Cards
**Pattern:** Three or four cards in a row, same size, same icon style, same weight, no hierarchy between them.
**Why it fails:** Equal weight means no priority — the eye doesn't know where to go. It also feels like a component library demo, not a designed product.
**Fix:** Introduce hierarchy. Make one card larger or featured. Alternate layout direction. Use a bento grid. Let one item break the grid.

### Anonymous Utility Typography
**Pattern:** System font or a common utility font (Inter, Roboto) at consistent weights with no typographic personality.
**Why it fails:** No visual identity. Every site using system fonts looks the same at a glance.
**Fix:** Choose a display font with personality for headings. Use weight contrast aggressively. Even if the body font is neutral, the heading font should carry the brand's tone.

### Inconsistent Component Styling
**Pattern:** Multiple button styles with no rationale, different card radii on the same page, arbitrary spacing values.
**Why it fails:** Signals a lack of intentional design. Users subconsciously notice inconsistency even if they can't name it — it erodes trust.
**Fix:** Define a token system before touching components. Every visual decision traces back to a token.

---

## 2. AI Fingerprint Anti-Patterns

These are visual and typographic patterns that have become overrepresented in AI-generated design output. They don't just look generic — they actively signal "this was made by a tool, not a designer." Avoid all of them by default unless there is a specific, documented reason to use one.

The goal is for every site to look like it was made with intent for a specific business, not assembled from the most probable design tokens.

### Inter as the Default Font
**Pattern:** Using Inter (or Inter + Inter) as the font stack because it's the safe, clean, universally available choice.
**Why it fails:** Inter has become the typographic fingerprint of AI-generated UI. It's a good font, but its ubiquity now communicates "generated" rather than "designed." A plumbing company, a bakery, and a law firm should not share a typeface.
**Fix:** Choose display fonts that match the business's tone. Reserve neutral sans-serifs like Inter for body copy only, paired with a distinctive display face. Consult the typography section of `design-system.md` for pairings by brand archetype.

### Purple-to-Blue Gradient as the Hero Background
**Pattern:** A linear or mesh gradient from purple (#7C3AED range) to blue (#2563EB range) as the primary hero background or brand identity.
**Why it fails:** This specific combination is the most common gradient in AI-generated SaaS and tech design. It communicates nothing about the actual brand and immediately reads as AI output to designers and increasingly to general audiences.
**Fix:** If a gradient is right for the brand, derive it from the actual brand colors defined in the project's token set. Build gradients with intent — angular, radial, or mesh; warm or cool based on brand tone — not by defaulting to the purple-blue ramp.

### Pure Black or Pure White as a Base
**Pattern:** Using `#000000` as the background color for dark mode or text, or `#FFFFFF` as the page background.
**Why it fails:** Pure black and white are the default zero-effort choices and they look it. Pure black backgrounds feel harsh and flat. Pure white has the same problem — it reads as unstyled. Both are AI fingerprints.
**Fix:** Use near-black (`oklch(12% 0.01 270)` or similar) for dark surfaces. Use off-white (`oklch(97% 0.005 90)` or similar) for light backgrounds. The perceptual difference is subtle but the visual refinement is immediate.

### Gray Text on a Colored Background Surface
**Pattern:** Muted gray text (`color: #9CA3AF` or similar) placed on a colored card, colored section background, or dark surface.
**Why it fails:** Gray text assumes a white or near-white background. On a colored or dark surface it almost always fails contrast (WCAG 1.4.3) and looks like a copy-paste from a different component. It is one of the most common AI composition errors.
**Fix:** Text on any non-neutral surface must be re-evaluated for contrast. On dark surfaces use near-white or white text. On colored surfaces, derive a text color that achieves 4.5:1 against that specific background. Never apply gray muted text globally — it's context-dependent.

### AI Dark Mode (Dark Gray Cards on Black)
**Pattern:** Dark mode implemented as near-black cards (`#1F2937`) on a pure black (`#000000`) background, with white text and blue accent — the default GPT/Claude/Gemini aesthetic.
**Why it fails:** This specific combination is now strongly associated with AI tool interfaces. Applied to a local business, restaurant, or service site it looks mismatched and off-brand. It also tends to result in very low surface contrast between layers.
**Fix:** Dark mode needs its own deliberate palette derived from the brand. If the brand is warm, the dark mode should use warm-tinted dark surfaces. Use the OKLCH color system to build dark mode tokens with proper chroma rather than defaulting to neutral grays.

### Gradient Text on Headings
**Pattern:** CSS gradient applied to heading text (`background-clip: text`) — typically purple-to-blue or blue-to-cyan — used as a visual accent on H1 or H2.
**Why it fails:** Gradient text was a distinctive effect for about 18 months. It is now the single most recognizable visual fingerprint of AI-generated design. It appears in roughly 40% of AI design output.
**Fix:** Use color contrast, weight, and size to create heading hierarchy. If a heading needs an accent, use an underline treatment, a background highlight, or a contrasting word in a different color — not a gradient clip.

### Nested Cards Inside Cards
**Pattern:** A card component that contains another card or panel as its primary content — information layered inside boxes inside boxes.
**Why it fails:** Nested cards create visual weight without hierarchy. They look like AI that didn't know where to put information so it kept wrapping it. They also create spatial claustrophobia on mobile.
**Fix:** Flatten the information architecture. If content feels like it needs a card inside a card, that's a signal the outer card is doing too much. Split the content into separate sections or use a different layout pattern (accordion, tabs, or a simple list).

### Bounce or Elastic Easing on UI Transitions
**Pattern:** CSS animations or JS transitions using `cubic-bezier` bounce curves, spring physics with high stiffness/low damping, or Framer Motion's default spring — applied to modals, dropdowns, cards on hover, or page transitions.
**Why it fails:** Bounce and elastic easing feel playful and energetic when used intentionally (children's products, games, very casual brands). Applied generically they feel AI-generated because they are the default in AI-suggested animation code. They also violate motion design principles for serious or professional brands.
**Fix:** Default to ease-out for entrances, ease-in for exits, ease-in-out for transitions between states. Use `cubic-bezier(0.16, 1, 0.3, 1)` (a fast-out-slow-in curve) as the house default. Reserve spring/bounce for explicitly playful contexts — document the rationale when used.

---

## 3. Layout and Composition Anti-Patterns

### Centered Everything
**Pattern:** Every section is center-aligned text, centered CTAs, centered cards — top to bottom.
**Why it fails:** Monotonous rhythm. Center alignment is weak for long-form content and creates a carnival-poster feel when overused.
**Fix:** Use center alignment for hero text and short impact statements. Switch to left-aligned layouts for content sections, feature lists, and body copy.

### No Breathing Room
**Pattern:** Sections crammed together with minimal spacing, dense text blocks, no whitespace between elements.
**Why it fails:** Increases cognitive load and makes content harder to scan. Users leave before engaging.
**Fix:** Apply section spacing from the spacing scale (--space-12 to --space-24 between sections). Let content breathe.

### Infinite Equal Sections
**Pattern:** Every section of the page has the same height, the same padding, the same visual weight.
**Why it fails:** No rhythm, no contrast. The eye has no reason to keep scrolling.
**Fix:** Vary section density. Alternate between content-heavy and spacious sections. Use one bold section as a visual anchor.

### Grid-Breaking Elements Everywhere
**Pattern:** Overlapping elements, diagonal layouts, and off-grid placements used throughout the entire page.
**Why it fails:** A broken grid works because it's a contrast against order. If everything is broken, nothing stands out.
**Fix:** Use one or two intentional grid-breaking moments. Let the rest of the layout be orderly.

### Full-Bleed Images Without Purpose
**Pattern:** Large background images behind every section regardless of whether they add information or atmosphere.
**Why it fails:** Heavy images slow the page, compete with text, and often have poor contrast for overlaid copy.
**Fix:** Use background images deliberately — hero sections or one key featured section. Everywhere else, use color, typography, and whitespace.

---

## 4. Typography Anti-Patterns

### Placeholder Typography
**Pattern:** Using font choices like "Heading" and "Body" without actual font decisions, or leaving Lorem Ipsum in a spec.
**Why it fails:** Typography is a design decision, not a dev task. The choice of font changes the entire tone of a design.
**Fix:** Always specify actual font families in every spec, even early wireframes. Use draft copy, never Lorem Ipsum.

### Too Many Type Sizes
**Pattern:** Six or more distinct font sizes used with no systematic relationship between them.
**Why it fails:** Visual chaos. The hierarchy becomes unreadable.
**Fix:** Use the defined type scale. Pick 3–4 sizes per page and use weight and color to differentiate within those sizes.

### Low-Contrast "Aesthetic" Text
**Pattern:** Light gray text on white, very thin font weights for body copy, text over busy images without overlay.
**Why it fails:** Fails WCAG 2.2 AA (4.5:1 required), alienates users with low vision, and often fails in bright sunlight on mobile.
**Fix:** Minimum 4.5:1 contrast for body text, 3:1 for large text. Never use font weights below 400 for body copy. Always add a dark overlay before placing text on images.

### All-Caps Body Copy
**Pattern:** Setting paragraphs or long labels in all-caps for stylistic effect.
**Why it fails:** Significantly reduces reading speed. Fine for short labels, badges, and section identifiers — not for body text.
**Fix:** Reserve all-caps for labels under 4–5 words. Use sentence case or title case for everything else.

### Orphaned Words (Widows)
**Pattern:** A single word left alone on the last line of a heading or paragraph.
**Why it fails:** Looks unfinished, breaks the visual rhythm of text blocks.
**Fix:** Use `text-wrap: balance` on headings. Manually adjust line breaks in key copy.

---

## 5. Color Anti-Patterns

### Relying on Color Alone
**Pattern:** Using color as the only indicator of meaning — e.g. red text for errors with no icon or label.
**Why it fails:** Fails WCAG 1.4.1. Color-blind users miss the signal entirely.
**Fix:** Always pair color with a secondary indicator — icon, label, pattern, or shape change.

### Equally Weighted Palette
**Pattern:** Three or four brand colors used at equal visual weight across the page.
**Why it fails:** No hierarchy. The eye doesn't know what to focus on. Everything competes.
**Fix:** Establish one dominant color, one supporting color, and one accent used sparingly. The accent is for CTAs and high-attention moments only.

### Pure White + Pure Black
**Pattern:** #FFFFFF background with #000000 text throughout.
**Why it fails:** Maximum contrast creates harsh reading experience. Also feels flat and undesigned.
**Fix:** Use near-white backgrounds (#F8F8F8, #FAF9F7) and near-black text (#1A1A1A, #111827). The difference is subtle but the feel is dramatically more refined.

### Semantic Color Misuse
**Pattern:** Using red for decorative elements, green for branding, or yellow for standard UI elements.
**Why it fails:** Users have strong associations between semantic colors and meaning. Red = danger, green = success. Using them decoratively creates confusion.
**Fix:** Reserve semantic colors (red, green, amber, blue) for their intended roles. Use brand colors for decorative and structural purposes.

### Dark Mode as an Afterthought
**Pattern:** Implementing dark mode by inverting all colors or applying a CSS filter to the page.
**Why it fails:** Inverted colors break images, distort brand colors, and often create contrast failures.
**Fix:** Dark mode requires its own token set. If there isn't time to do it properly, don't ship it. A broken dark mode is worse than no dark mode.

---

## 6. Navigation Anti-Patterns

### Mega-Menus on Simple Sites
**Pattern:** Dropdown mega-menus with columns, icons, and descriptions for a site with 5–8 pages.
**Why it fails:** Cognitive overload. If your site is small, your nav should be simple.
**Fix:** Mega-menus are only justified for large e-commerce or enterprise sites with genuinely complex content hierarchies. For most sites: flat nav, 5–7 items.

### Non-Descriptive Labels
**Pattern:** Nav labels like "Solutions," "Insights," "Platform," "Journey" that could mean anything.
**Why it fails:** Users can't predict what they'll find. Recognition fails, recall is required.
**Fix:** Use plain descriptive labels: "Services," "Blog," "Pricing," "About Us," "Contact."

### No Active State
**Pattern:** All nav items look the same regardless of which page the user is on.
**Why it fails:** Users lose their sense of location. Violates heuristic #6 (visibility of system status).
**Fix:** Current page must have a visually distinct active state — underline, color change, or background highlight.

### Hamburger-Only on Desktop
**Pattern:** Using a hamburger menu on desktop because "it saves space."
**Why it fails:** Hides navigation from users who expect it to be visible. Increases clicks to reach any page.
**Fix:** Hamburger menus are for mobile only. On desktop, show full navigation unless the site is a focused single-task app (e.g. a full-screen tool).

### No Skip Navigation
**Pattern:** Keyboard users must tab through the entire navigation on every page to reach the main content.
**Why it fails:** Fails WCAG 2.4.1. Extremely frustrating for keyboard-only and screen reader users.
**Fix:** Add a "Skip to main content" link as the first focusable element on every page. Visible on focus, hidden otherwise.

---

## 7. UX and Interaction Anti-Patterns

### First-Load Popups and Interstitials
**Pattern:** Modal popup appears immediately when a user lands on the page (newsletter signup, cookie banner, discount offer).
**Why it fails:** User has given no signal of interest yet. It interrupts the reason they came and damages trust.
**Fix:** Delay popups until after meaningful engagement — 30+ seconds on page, after a scroll threshold, or on exit intent. Cookie consent banners are required but should be minimal.

### Autoplay Video and Audio
**Pattern:** Video or audio plays automatically when the page loads.
**Why it fails:** Fails WCAG 1.4.2. Startles users, drains battery on mobile, makes the page feel out of control.
**Fix:** Video should be play-on-click. If motion in the background is desired, use a muted looping video with `autoplay muted playsinline` — no audio, and a pause control visible.

### Infinite Scroll Without Escape
**Pattern:** Infinite scroll with no way to return to a specific position or filter/paginate instead.
**Why it fails:** Users can't bookmark a position, can't navigate forward/back reliably, and can't find something they saw earlier.
**Fix:** For most content sites, use pagination or a "Load more" button. If infinite scroll is used, preserve scroll position on back-navigation.

### Forms That Clear on Error
**Pattern:** Form validation fails and the entire form clears — user must re-enter everything.
**Why it fails:** Extremely frustrating, especially on long forms. Users often abandon.
**Fix:** Preserve all valid field values on error. Only highlight and focus the field that failed.

### Unclear Button States
**Pattern:** Buttons that look identical in default and disabled states, or that give no visual feedback when clicked.
**Why it fails:** Users don't know if the action registered. They click again, creating duplicate submissions.
**Fix:** Disabled buttons must look clearly inactive (reduced opacity, cursor change). Loading buttons must show a spinner and disable re-click.

### Dead-End Error Pages
**Pattern:** 404 or error pages that just say "Page not found" with no next steps.
**Why it fails:** Users hit a dead end and leave. The site failed to recover gracefully.
**Fix:** Every error page must include: the search bar, links to key sections, and a human explanation of what happened.

### Overuse of Modals
**Pattern:** Modals for confirmation dialogs, content previews, forms, image galleries, sub-menus — everything is a modal.
**Why it fails:** Modals interrupt flow and trap users on mobile. They also create accessibility challenges if not implemented correctly.
**Fix:** Reserve modals for actions that genuinely require the user's full attention before proceeding (confirm deletion, complete a focused task). Prefer inline patterns or new pages for content.

---

## 8. Accessibility Anti-Patterns

These are WCAG 2.2 AA violations — not optional, not "nice to have." Any of these in a delivered design is a defect.

### Missing Focus States
**Pattern:** Interactive elements have no visible focus indicator (outline removed with `outline: none` and not replaced).
**Why it fails:** Fails WCAG 2.4.7 and 2.4.11. Keyboard users cannot see where they are.
**Fix:** Never remove the default focus outline without replacing it with a visible custom one. Minimum: 2px solid outline with sufficient contrast, offset from the element.

### Images Without Alt Text
**Pattern:** `<img>` tags with no `alt` attribute, or `alt=""` on informative images.
**Why it fails:** Fails WCAG 1.1.1. Screen reader users get no information about the image.
**Fix:** Every informative image has descriptive alt text. Decorative images use `alt=""`. Icons that convey meaning need aria-label or title.

### Form Fields Without Labels
**Pattern:** Inputs with placeholder text only — no `<label>` element associated.
**Why it fails:** Fails WCAG 1.3.1. Placeholder text disappears on focus, leaving the user uncertain what the field is for. Screen readers may not announce placeholder text.
**Fix:** Every form field has a `<label>` with matching `for`/`id` attributes. Placeholder is a hint, never a substitute for a label.

### Color Contrast Failures
**Pattern:** Light gray text on white, colored text on colored backgrounds, text over images without overlay.
**Why it fails:** Fails WCAG 1.4.3. Excludes users with low vision.
**Fix:** Check every text/background combination with a contrast checker. Minimum 4.5:1 for normal text, 3:1 for large text (18pt+ or 14pt+ bold), 3:1 for UI components and focus indicators.

### Keyboard Traps
**Pattern:** Opening a modal or menu that cannot be closed with the keyboard, or a widget that captures all keyboard input.
**Why it fails:** Fails WCAG 2.1.2. Keyboard-only users become stuck.
**Fix:** Every overlay (modal, drawer, dropdown) must be closeable with ESC. Focus must be trapped within the overlay while open and returned to the trigger element when closed.

### Touch Targets Too Small
**Pattern:** Links, buttons, and icons with tap targets smaller than 24×24px (WCAG 2.5.8) or 44×44px (best practice).
**Why it fails:** Fails WCAG 2.5.8. Difficult or impossible to tap accurately on mobile, especially for users with motor impairments.
**Fix:** Minimum 44×44px tap target for all interactive elements. Use padding to extend the clickable area if the visual size must stay small.

### Auto-Playing Animations Without Control
**Pattern:** CSS or JS animations that loop indefinitely with no way to pause them.
**Why it fails:** Fails WCAG 2.2.2. Can trigger seizures or vestibular disorders in sensitive users.
**Fix:** All looping animations must respect `prefers-reduced-motion`. Any animation lasting more than 5 seconds must have a pause control.

---

## 9. Performance Anti-Patterns

Performance is a UX issue — slow sites lose users before the design is ever seen.

### Unoptimized Images
**Pattern:** Full-resolution JPEGs or PNGs loaded on mobile, no lazy loading, no modern formats.
**Why it fails:** Largest Contentful Paint (LCP) tanks. Mobile users on slower connections bounce before content appears.
**Fix:** Use WebP or AVIF formats. Implement `loading="lazy"` on below-fold images. Use `srcset` for responsive images. Compress images to the smallest acceptable quality.

### Loading Large JS Bundles
**Pattern:** A full React or Vue app loaded for a simple marketing site or small business site.
**Why it fails:** Adds hundreds of KB of JavaScript that blocks rendering and delays interactivity.
**Fix:** For content-focused marketing sites, use vanilla HTML/CSS/JS or a static site generator. Reserve React/Vue for sites that genuinely need component reactivity.

### Render-Blocking Resources
**Pattern:** CSS and JS loaded in `<head>` without `defer` or `async`, Google Fonts loaded synchronously.
**Why it fails:** Blocks the browser from rendering the page until resources are downloaded and parsed.
**Fix:** Load non-critical CSS asynchronously. Add `defer` to JS files. Use `font-display: swap` for web fonts. Preconnect to font origins.

### No Image Dimensions Specified
**Pattern:** Images without `width` and `height` attributes in HTML.
**Why it fails:** Browser can't reserve space — causes Cumulative Layout Shift (CLS) as images load in.
**Fix:** Always specify `width` and `height` on `<img>` elements. Use `aspect-ratio` CSS for responsive images.

### Heavy Fonts with No Subsetting
**Pattern:** Loading an entire variable font file or multiple font weights when only 2–3 are used.
**Why it fails:** Font files can be 300–500KB each. Loading unused weights wastes bandwidth.
**Fix:** Specify only the weights needed in Google Fonts URL. Use `unicode-range` for character subsetting if self-hosting.

---

## 10. Content and Copy Anti-Patterns

### Vague Headlines
**Pattern:** "Welcome to our website." / "Your partner in success." / "Innovation for tomorrow."
**Why it fails:** Says nothing about what the business does or for whom. Fails the 5-second test immediately.
**Fix:** H1 must state what the business does and who it's for. "Custom tile work for Sacramento homeowners." "Bookkeeping software for freelancers."

### Jargon-Heavy Copy
**Pattern:** Industry jargon, internal terminology, or buzzwords that the target audience doesn't use.
**Why it fails:** Users can't recognize themselves in the copy. "Synergistic solutions for enterprise-grade workflows" means nothing to a small business owner looking for accounting software.
**Fix:** Write in the language the user uses when describing their own problem. Use words from user interviews and reviews where possible.

### Weak CTAs
**Pattern:** "Submit," "Click here," "Learn more," "Go."
**Why it fails:** No value, no outcome, no motivation to act.
**Fix:** CTA = verb + outcome. "Get a free quote," "Start your free trial," "Book a 15-minute call," "Download the guide."

### Lorem Ipsum in Deliverables
**Pattern:** Placeholder text left in wireframes or specs handed to developers.
**Why it fails:** Developers build layouts to fit placeholder content that's wildly different from real content. Layout breaks when real copy goes in.
**Fix:** Always draft real or realistic copy — even if marked `[DRAFT COPY]`. Real content reveals layout problems that Lorem Ipsum hides.

### Walls of Text
**Pattern:** Long paragraphs with no subheadings, no bullets, no visual breaks.
**Why it fails:** Web users scan before they read. Unbroken text blocks are skipped.
**Fix:** Max 3 sentences per paragraph on web. Use subheadings every 150–200 words. Break features and benefits into scannable bullets.

---

## 11. Mobile Anti-Patterns

### Desktop-First Thinking
**Pattern:** Designing the desktop layout first, then trying to squeeze it into mobile.
**Why it fails:** Mobile is often the primary device for the target audience. Desktop-first leads to compromised mobile experiences.
**Fix:** Define mobile layout and content hierarchy first. Desktop is an enhancement, not the baseline.

### Tiny Tap Targets
**Pattern:** Nav links, footer links, and small icon buttons under 44px in height.
**Why it fails:** Finger taps are imprecise. Small targets cause mis-taps and frustration.
**Fix:** Minimum 44×44px for all tappable elements on mobile. Use padding to extend targets without changing visual size.

### Horizontal Scrolling (Unintentional)
**Pattern:** Content overflows the viewport width, causing horizontal scroll on mobile.
**Why it fails:** Feels broken. Users assume the site isn't mobile-friendly and leave.
**Fix:** Test every layout at 360px width. Set `max-width: 100%` on images and media. Use `overflow-x: hidden` on the body only as a last resort after fixing the underlying cause.

### Hiding Critical Content on Mobile
**Pattern:** Key content, pricing, or features hidden or removed at mobile breakpoints.
**Why it fails:** Mobile users often have higher intent than desktop browsers. Hiding content from them loses conversions.
**Fix:** Restructure, don't hide. Condense tables into cards, move sidebars below main content, stack columns — but keep all critical content accessible.

### Fixed-Width Elements
**Pattern:** Elements with `width: 400px` or similar fixed values that overflow on small screens.
**Why it fails:** Breaks layout below that viewport width.
**Fix:** Use `max-width` instead of `width` for containers. Use `width: 100%` with a `max-width` cap.

---

## 12. Pre-Delivery Self-Check

Run this checklist before finalizing every design output. Output the result explicitly:
**"Pre-delivery check: passed"** or **"Pre-delivery check: [X items flagged — here's what I fixed/flagged]"**

### AI Fingerprint Check
- [ ] Heading font is NOT Inter used alone — a display font with brand personality is paired or substituted
- [ ] No purple-to-blue gradient used as hero background or primary brand element
- [ ] Background is not pure `#000000` or `#FFFFFF` — off-white or near-black OKLCH values used
- [ ] No gray muted text placed on colored or dark surfaces without contrast verification
- [ ] Dark mode (if implemented) uses brand-derived surface colors, not the default dark gray on black AI aesthetic
- [ ] No gradient text clip on headings
- [ ] No cards nested inside cards as primary layout pattern
- [ ] All animations use ease-out / ease-in / ease-in-out — no bounce or elastic easing unless explicitly justified

### Generic Pattern Check
- [ ] Hero avoids the default formula (nav + centered H1 + 2 buttons + logo strip + 3 identical cards)
- [ ] Color palette is not default tech blue/purple gradient
- [ ] Feature cards have visual hierarchy — not three identical items in a row
- [ ] Typography has personality — not anonymous utility fonts used without justification
- [ ] Component styles are consistent — no unexplained style variations across pages

### Layout and Composition Check
- [ ] Not everything is center-aligned
- [ ] Sections have varied rhythm and density
- [ ] Whitespace is used intentionally — not filled with content for content's sake
- [ ] Grid breaks (if any) are intentional and used sparingly

### Accessibility Check
- [ ] All text meets 4.5:1 contrast ratio (3:1 for large text)
- [ ] All interactive elements have visible focus states
- [ ] No color used as the only indicator of meaning
- [ ] All form fields have associated labels
- [ ] Images have alt text specified
- [ ] Touch targets are minimum 44×44px
- [ ] Skip to main content link included
- [ ] prefers-reduced-motion respected for all animations

### Responsive Check
- [ ] Mobile layout described at 360px
- [ ] Tablet layout described at 768px
- [ ] Desktop layout described at 1280px
- [ ] No content hidden on mobile that is critical to conversion
- [ ] No fixed-width elements that would overflow on small screens

### Content Check
- [ ] H1 states what the business does and for whom
- [ ] All CTAs use verb + outcome format
- [ ] No Lorem Ipsum — all copy is draft or final
- [ ] No jargon that the target audience wouldn't recognize

### Performance Check
- [ ] Images specified as WebP/AVIF with lazy loading for below-fold images
- [ ] No heavy JS framework recommended for a simple content site
- [ ] Font loading strategy specified (font-display: swap, preconnect)

---

## 13. Conflict Resolution Playbook

When the user or a client requests something that conflicts with best practices, follow this pattern every time:

**Step 1 — Identify** the specific issue and name which standard it violates.
**Step 2 — Explain** the trade-off in plain, non-condescending language.
**Step 3 — Propose** a compliant alternative that preserves the intent.
**Step 4 — Decide** — give the user the final call with full information.

Never refuse outright. Never comply silently. Always explain and propose.

### Common Conflicts and Responses

**"I want the text to be light gray on white — it looks clean."**
> "Light gray on white typically fails the 4.5:1 contrast requirement (WCAG 1.4.3), which means users with low vision — and many users in bright sunlight on mobile — won't be able to read it. A slightly darker gray like #595959 on white still looks refined and clean while passing contrast. Want me to spec that instead?"

**"Can you add autoplay video to the hero?"**
> "Autoplay video (with audio) fails WCAG 1.4.2 and tends to spike bounce rates on mobile due to data usage. A muted looping background video with `autoplay muted playsinline` is accessible and achieves the same atmospheric effect — users who want sound can click to unmute. Want me to spec it that way?"

**"Make the font really small — it looks more elegant."**
> "Text below 16px for body copy starts failing contrast requirements at typical font weights and is particularly problematic on mobile. Elegance through type comes from spacing, weight contrast, and font choice rather than small size. I can achieve a refined, typographic feel at 16–18px body with tighter tracking and a strong display font. Want me to show that direction?"

**"Put a popup on the homepage as soon as people arrive."**
> "Immediate first-load popups tend to damage trust and increase bounce rates — users came for a reason and the popup interrupts before they've had a chance to engage. A much more effective approach is triggering the popup after 30 seconds, after a scroll threshold, or on exit intent — when there's a signal of interest. Want me to design it with one of those triggers?"

**"Can we remove the focus outlines? They look bad."**
> "Focus outlines are required for keyboard accessibility (WCAG 2.4.7) — removing them without a replacement makes the site unusable for keyboard-only users and fails compliance. The issue is usually that browser defaults are ugly — I can design a custom focus style that looks intentional and on-brand while being fully compliant. Want me to spec that?"

**"I want to use Comic Sans / [controversial font choice]."**
> "Worth flagging before we commit: Comic Sans carries strong associations with informality and is widely recognized as a font that signals low production value to many audiences — which can undermine trust, especially for service businesses or anything where credibility matters. That said, it's your call and it can work for the right context (children's brands, very casual local businesses, intentionally playful brands). If you want to move forward with it, I'll make sure it's used in a way that's still readable and accessible, and I'll pair it with a neutral body font to keep the reading experience comfortable. Want to stick with it, or explore a similarly playful alternative that carries less baggage?"

---

## 14. SEO Anti-Patterns (Design-Related)

These SEO failures are directly caused by design and structure decisions — not content or marketing gaps. Every one of these is preventable at the design stage.

### Missing or Duplicate Page Titles
**Pattern:** Every page has `<title>Business Name</title>` with no page-specific descriptor, or no title at all.
**Why it fails:** Google uses the title as a primary ranking signal. Duplicate titles tell Google all pages are the same topic.
**Fix:** Unique, descriptive title per page. Format: `Primary Keyword — Business Name`. Under 60 characters.

### Multiple H1s on One Page
**Pattern:** The logo, the tagline, and the hero headline are all marked as H1.
**Why it fails:** Google uses the H1 to understand the page's main topic. Multiple H1s create ambiguity.
**Fix:** Exactly one H1 per page — the page's main topic. Logo and tagline are links or styled text, never headings.

### No Alt Text on Images
**Pattern:** `<img src="photo.jpg">` with no alt attribute.
**Why it fails:** Google cannot index images without alt text. Screen readers announce nothing.
**Fix:** Always include `alt` attribute. Describe the image naturally, include location/service keywords where relevant.

### Emojis Used as Icons
**Pattern:** Using 📞 or ✅ as UI icons instead of SVG.
**Why it fails:** Emojis render inconsistently across devices and operating systems, look unprofessional in professional contexts, and cannot be styled with CSS. Screen readers announce them as their full unicode name ("telephone receiver" not "call us").
**Fix:** Always use SVG icons — Heroicons, Lucide, or Phosphor are all free, consistent, accessible, and CSS-styleable.

### Missing cursor: pointer on Clickable Elements
**Pattern:** Clickable cards, custom button elements, or interactive divs that don't show the hand cursor on hover.
**Why it fails:** Users expect the cursor to change to a pointer on anything clickable. Without it, users are uncertain whether an element is interactive.
**Fix:** All clickable elements — buttons, links, cards, interactive elements — must have `cursor: pointer` in CSS. This should be part of the component defaults.
```css
button, a, [role="button"], .card--clickable {
  cursor: pointer;
}
```

### Non-Descriptive Anchor Text
**Pattern:** "Click here," "Read more," "Learn more" with no context.
**Why it fails:** Google uses anchor text to understand what the linked page is about. Generic anchor text provides no signal. Screen reader users navigating by links hear a list of "read more, read more, read more."
**Fix:** Use descriptive anchor text: "Learn more about our drain cleaning services" not "Learn more."
