# Design System Defaults Reference

This file defines the house style defaults, design token system, UI style library, typography pairings, component standards, and visual execution rules. Read this file when defining tokens, choosing visual direction, speccing components, or applying the house style to any project.

All defaults defined here are **starting points — override them per project** when brand constraints, audience needs, or creative direction warrants it. Always document overrides in the project's design spec so the system stays consistent within each project.

---

## Table of Contents
1. [Design Token System](#1-design-token-system)
2. [Typography](#2-typography)
3. [Color System](#3-color-system)
4. [Spacing, Radius, and Shadows](#4-spacing-radius-and-shadows)
5. [Component Standards](#5-component-standards)
6. [Visual Direction — UI Style Library](#6-visual-direction--ui-style-library)
7. [Aesthetic Execution Rules](#7-aesthetic-execution-rules)
8. [Dark Mode](#8-dark-mode)

---

## 1. Design Token System

Every project gets a token system — even simple small business sites. Tokens make designs consistent, maintainable, and easier to hand off. Define tokens before touching any component.

### Token Naming Convention
```
category/role/variant
```
Examples:
```
color/primary/500
color/text/muted
color/semantic/error
type/size/h1
type/weight/bold
space/4
radius/md
shadow/card
```

### Token Categories (always define all of these)

| Category | What it covers |
|---|---|
| `color/` | All colors — brand, text, background, border, semantic |
| `type/` | Font families, sizes, weights, line heights |
| `space/` | All spacing values — margins, paddings, gaps |
| `radius/` | Border radius values |
| `shadow/` | Box shadow values |
| `motion/` | Transition durations and easing curves |
| `breakpoint/` | Responsive breakpoint values |

### Minimum Token Set Per Project

```css
/* ─── COLOR (all values in OKLCH) ───────── */
/* Replace example values with project-specific colors from oklch.com */

--color-primary:        oklch(50% 0.18 265);  /* Main brand color */
--color-primary-dark:   oklch(40% 0.18 265);  /* Hover/active state of primary */
--color-secondary:      oklch(60% 0.12 200);  /* Supporting brand color */
--color-accent:         oklch(65% 0.20 55);   /* High-attention moments — CTAs, highlights */

--color-bg:             oklch(97% 0.005 90);  /* Page background — warm off-white */
--color-surface:        oklch(99% 0.002 90);  /* Cards, panels, elevated surfaces */
--color-surface-alt:    oklch(94% 0.008 90);  /* Alternate surface (zebra rows, sidebar) */

--color-text:           oklch(15% 0.010 265); /* Primary body text — near-black */
--color-text-muted:     oklch(45% 0.010 265); /* Secondary text, captions, labels */
--color-text-inverse:   oklch(98% 0.002 90);  /* Text on dark/colored backgrounds */

--color-border:         oklch(88% 0.006 265); /* Default border color */
--color-border-strong:  oklch(75% 0.010 265); /* Emphasized borders */

--color-success:        oklch(52% 0.17 145);  /* Success states */
--color-warning:        oklch(65% 0.18 60);   /* Warning states */
--color-error:          oklch(50% 0.22 25);   /* Error states */
--color-info:           oklch(52% 0.18 265);  /* Informational states */

/* ─── TYPOGRAPHY ─────────────────────────── */
--font-display:         ;   /* Headings, hero text */
--font-body:            ;   /* Body copy, UI text */
--font-mono:            ;   /* Code, technical content (if needed) */

/* ─── SPACING ────────────────────────────── */
--space-1:   4px;
--space-2:   8px;
--space-3:   12px;
--space-4:   16px;
--space-6:   24px;
--space-8:   32px;
--space-12:  48px;
--space-16:  64px;
--space-24:  96px;
--space-32:  128px;

/* ─── RADIUS ─────────────────────────────── */
--radius-sm:   4px;
--radius-md:   8px;
--radius-lg:   16px;
--radius-xl:   24px;
--radius-full: 9999px;  /* Pills, fully rounded */

/* ─── SHADOWS ────────────────────────────── */
--shadow-sm:  0 1px 3px rgba(0,0,0,0.08);
--shadow-md:  0 4px 12px rgba(0,0,0,0.10);
--shadow-lg:  0 8px 24px rgba(0,0,0,0.12);
--shadow-xl:  0 16px 48px rgba(0,0,0,0.14);

/* ─── MOTION ─────────────────────────────── */
--duration-fast:    150ms;
--duration-base:    200ms;
--duration-slow:    300ms;
--ease-out:         cubic-bezier(0.16, 1, 0.3, 1);
--ease-in-out:      cubic-bezier(0.4, 0, 0.2, 1);

/* ─── LAYOUT ─────────────────────────────── */
--max-width:        1280px;
--max-width-prose:  72ch;
--container-pad-x:  clamp(16px, 5vw, 64px);
```

---

## 2. Typography

### House Typography Rules

- Always pair a **display font** (headings, hero) with a **body font** (copy, UI). Never use a single font for everything unless it's genuinely versatile enough to support both roles.
- Inter, Roboto, Arial, and system fonts are **not the default** — but they are valid choices when a client prefers them, when performance is a hard constraint, or when the brand genuinely calls for a utilitarian feel (e.g. a dev tool or minimal SaaS). Always justify the choice explicitly.
- Choose fonts that carry personality appropriate to the brand. The display font sets the tone of the entire site.
- Always import from Google Fonts or self-host for display and body fonts. System fonts are acceptable as a fallback stack or deliberate performance choice — document which and why.

### Type Scale (Desktop)

```
--type-size-xs:    0.75rem   / 12px  — captions, labels, fine print
--type-size-sm:    0.875rem  / 14px  — secondary UI text, metadata
--type-size-base:  1rem      / 16px  — body copy baseline
--type-size-lg:    1.125rem  / 18px  — lead paragraphs, large UI text
--type-size-xl:    1.25rem   / 20px  — small headings, card titles
--type-size-2xl:   1.5rem    / 24px  — H4, section subheadings
--type-size-3xl:   1.875rem  / 30px  — H3
--type-size-4xl:   2.25rem   / 36px  — H2
--type-size-5xl:   3rem      / 48px  — H1 (desktop)
--type-size-6xl:   3.75rem   / 60px  — Hero display (desktop)
--type-size-7xl:   4.5rem    / 72px  — Large hero display (desktop)
```

**Mobile scale:** reduce H1 to ~2rem–2.5rem, hero display to ~2.5rem–3rem. Scale intermediate sizes proportionally.

### Line Heights

```
--leading-tight:    1.2   — display headings
--leading-snug:     1.35  — subheadings, card titles
--leading-normal:   1.5   — body copy baseline
--leading-relaxed:  1.65  — long-form reading content
--leading-loose:    1.8   — captions, small UI text
```

### Font Weight

```
--weight-regular:   400
--weight-medium:    500
--weight-semibold:  600
--weight-bold:      700
--weight-black:     900  — use sparingly, hero emphasis only
```

### Curated Font Pairings — Baseline by Brand Personality

These 7 pairings are starting points organized by brand personality. They are **not a closed list** — treat them as a baseline to jump from. Per-project font choices should always be justified in terms of brand and audience, and can deviate from these pairings whenever the creative direction warrants it. The goal is intentionality, not conformity.

**Elegant / Luxury / Premium**
- Display: Cormorant Garamond, Playfair Display, DM Serif Display
- Body: Jost, DM Sans, Lato
- Mood: refined, timeless, high-end
- Best for: spas, luxury services, photography, boutiques, fine dining

**Bold / Modern / Confident**
- Display: Syne, Clash Display, Cabinet Grotesk, Bebas Neue
- Body: Inter (acceptable here), Plus Jakarta Sans, Outfit
- Mood: strong, contemporary, assured
- Best for: agencies, startups, SaaS, fitness, tech brands

**Friendly / Approachable / Warm**
- Display: Nunito, Poppins, Quicksand, Bricolage Grotesque
- Body: Nunito Sans, Open Sans, Source Sans 3
- Mood: welcoming, accessible, human
- Best for: childcare, community services, food, local businesses, nonprofits

**Editorial / Literary / Intellectual**
- Display: Libre Baskerville, Lora, Fraunces, Spectral
- Body: Source Serif 4, Merriweather, EB Garamond
- Mood: thoughtful, credible, authoritative
- Best for: law, finance, consulting, publishing, education

**Technical / Precise / Clean**
- Display: Space Grotesk (acceptable here), IBM Plex Sans, Epilogue
- Body: IBM Plex Sans, Roboto Mono (for code elements), Fira Sans
- Mood: systematic, reliable, engineered
- Best for: developer tools, SaaS dashboards, fintech, data products

**Playful / Creative / Expressive**
- Display: Fraunces, Unbounded, Righteous, Paytone One
- Body: Karla, Mulish, Nunito
- Mood: fun, unexpected, energetic
- Best for: children's brands, gaming, food apps, creative studios

**Rustic / Artisan / Local**
- Display: Abril Fatface, Calistoga, Zilla Slab, Bitter
- Body: Lato, Source Sans 3, PT Sans
- Mood: handcrafted, authentic, grounded
- Best for: trades, construction, farming, local food, independent shops

---

## 3. Color System

### Color Format Standard — OKLCH

All color tokens are authored in **OKLCH** (`oklch(L% C H)`). OKLCH is the authoring standard for this design system because it is perceptually uniform — equal steps in lightness or chroma look equal to the human eye, which hex does not guarantee. This makes it far easier to build accessible, consistent palettes and predict how colors will look across surfaces.

**OKLCH syntax:**
```css
oklch(L% C H)
/* L = lightness  0% (black) → 100% (white)  */
/* C = chroma     0 (gray)   → ~0.37 (vivid) */
/* H = hue angle  0–360 (red=25, orange=60, yellow=90, green=145, blue=265, purple=310) */
```

**Quick conversion:** Use [oklch.com](https://oklch.com) or the Oklch Color Picker in CSS tooling to convert from a client's hex brand colors. Always convert to OKLCH before defining tokens — never author tokens in hex.

**For client communication and the Design System Output Block:** use hex. Clients don't think in OKLCH. Convert back to hex for proposals, handoff docs, and anything client-facing.

### House Color Philosophy

- **High contrast is non-negotiable**: minimum 4.5:1 for body text, 3:1 for large text and UI components
- **Commit to a palette**: dominant colors with sharp accents outperform timid, evenly-distributed palettes
- **Avoid pure white backgrounds**: off-white (`oklch(97% 0.005 90)` and similar warm-tinted values) feel more refined and are easier on the eyes
- **Avoid pure black text**: use near-black (`oklch(15% 0.01 265)` or similar) for better reading comfort
- **Never rely on color alone** to convey meaning — always pair with icons, labels, or patterns

### Color Palette Archetypes by Project Type

**Marketing / small business — Warm Neutrals**
```
Background:  #FAF9F7  (warm off-white)
Surface:     #FFFFFF
Text:        #1C1917  (warm near-black)
Text muted:  #78716C
Primary:     [brand color]
Border:      #E7E5E4
```

**SaaS / Dashboard — Cool Neutrals**
```
Background:  #F8FAFC
Surface:     #FFFFFF
Text:        #0F172A
Text muted:  #64748B
Primary:     [brand color]
Border:      #E2E8F0
```

**E-commerce — Clean White**
```
Background:  #FFFFFF
Surface:     #F9FAFB
Text:        #111827
Text muted:  #6B7280
Primary:     [brand color]
Border:      #E5E7EB
```

**Dark / High-Contrast**
```
Background:  #0A0A0A or #0F172A
Surface:     #1A1A1A or #1E293B
Text:        #F8FAFC
Text muted:  #94A3B8
Primary:     [brand color — ensure contrast on dark]
Border:      #2D2D2D or #334155
```

### Semantic Color Defaults

```
Success:  #16A34A  (green — accessible on white)
Warning:  #D97706  (amber — accessible on white)
Error:    #DC2626  (red — accessible on white)
Info:     #2563EB  (blue — accessible on white)
```

Always check semantic colors against their background at every usage. Never assume inherited contrast.

### Industry Color Guidance (from ui-ux-pro-max)

| Industry | Recommended palette direction | Avoid |
|---|---|---|
| Healthcare / Medical | Clean whites, soft blues, muted greens | Bright reds (alarm associations), neon |
| Legal / Finance | Navy, dark grays, gold accents | Playful palettes, neon, pastels |
| Food / Restaurant | Warm tones, earth colors, rich deep tones | Cold blues, clinical whites |
| Wellness / Spa | Sage greens, warm neutrals, dusty rose | Harsh primaries, high-saturation colors |
| Construction / Trades | Bold primaries (navy, orange, charcoal) | Pastels, overly delicate palettes |
| Tech / SaaS | Cool grays, deep blues, clean accents | Generic purple gradients, AI clichés |
| Photography / Art | Let the work breathe — neutral backgrounds | Busy patterns, competing colors |
| E-commerce (luxury) | Deep jewel tones, gold, black | Bright primaries, cartoon colors |
| Children / Education | Warm brights, playful secondaries | Clinical whites, all-gray palettes |
| Nonprofit / Community | Warm, approachable, trustworthy | Cold corporate palettes |

---

## 4. Spacing, Radius, and Shadows

### Spacing — Usage Guide

Always pull from the spacing scale defined in the token system. Do not invent arbitrary values.

| Token | Value | Typical use |
|---|---|---|
| `--space-1` | 4px | Icon gaps, tight inline spacing |
| `--space-2` | 8px | Internal component padding (small) |
| `--space-3` | 12px | Small component padding |
| `--space-4` | 16px | Base padding, small gaps between elements |
| `--space-6` | 24px | Medium gaps, internal section spacing |
| `--space-8` | 32px | Component separation |
| `--space-12` | 48px | Section separation (mobile) |
| `--space-16` | 64px | Section separation (tablet) |
| `--space-24` | 96px | Section separation (desktop) |
| `--space-32` | 128px | Hero padding, major section breaks |

### Border Radius — Usage Guide

| Token | Value | Typical use |
|---|---|---|
| `--radius-sm` | 4px | Small UI elements, tags, badges |
| `--radius-md` | 8px | Buttons, inputs, small cards |
| `--radius-lg` | 16px | Cards, modals, panels |
| `--radius-xl` | 24px | Large cards, hero sections, feature blocks |
| `--radius-full` | 9999px | Pills, avatar circles, toggle switches |

**Consistency rule**: choose one or two radius values per project and apply them consistently. Do not mix sharp corners and heavy rounding without clear rationale.

### Shadows — Usage Guide

| Token | Value | Typical use |
|---|---|---|
| `--shadow-sm` | 0 1px 3px rgba(0,0,0,0.08) | Subtle lift — inputs, small cards |
| `--shadow-md` | 0 4px 12px rgba(0,0,0,0.10) | Cards, dropdowns |
| `--shadow-lg` | 0 8px 24px rgba(0,0,0,0.12) | Modals, elevated panels |
| `--shadow-xl` | 0 16px 48px rgba(0,0,0,0.14) | Hero elements, featured sections |

**Shadow philosophy**: use shadows to create depth and grouping, not decoration. One shadow level per elevation tier. Avoid stacking multiple shadow types on a single element.

---

## 5. Component Standards

Every component must be specced with all variants and all states. Never spec a component in default state only.

### Universal State Requirements

Every interactive component requires these states:
- **Default** — resting state
- **Hover** — cursor over element (desktop)
- **Active / Pressed** — click/tap in progress
- **Focus** — keyboard focus (must be visible — WCAG 2.4.11)
- **Disabled** — not interactive (reduce opacity to 0.4–0.5, change cursor)
- **Loading** — async action in progress (spinner or skeleton)
- **Error** — invalid or failed state
- **Success** — completed action confirmation

### Button Component

```
Variants:    Primary, Secondary, Ghost, Destructive, Link
Sizes:       SM (32px h), MD (40px h), LG (48px h), XL (56px h)
Min width:   120px
Min touch target: 44×44px (WCAG 2.5.8)
Padding:     12px 24px (MD), scale proportionally

Primary:
  Default:   bg=--color-primary, text=--color-text-inverse
  Hover:     bg=--color-primary-dark, transition var(--duration-base)
  Focus:     2px solid --color-accent offset 2px
  Disabled:  opacity 0.45, cursor not-allowed

Secondary:
  Default:   bg=transparent, border=2px --color-primary, text=--color-primary
  Hover:     bg=--color-primary at 8% opacity
  
Ghost:
  Default:   bg=transparent, no border, text=--color-primary
  Hover:     bg=--color-primary at 6% opacity

Icon buttons: must have aria-label describing the action
Loading:      Replace label with spinner, keep button width fixed
```

### Input / Form Fields

```
Height:       48px (touch-friendly default)
Padding:      12px 16px
Border:       1px solid --color-border
Radius:       --radius-md
Font:         --type-size-base, --font-body

States:
  Default:    border=--color-border
  Focus:      border=--color-primary, outline=2px solid --color-primary offset 1px
  Filled:     border=--color-border-strong
  Error:      border=--color-error, error message below field in --color-error
  Disabled:   bg=--color-surface-alt, opacity 0.6

Label:        Always above the field, never placeholder-only
              --type-size-sm, --weight-medium, --color-text
Placeholder:  --color-text-muted, descriptive hint not a label substitute
Error msg:    Below field, --type-size-sm, --color-error, with error icon
Helper text:  Below field, --type-size-sm, --color-text-muted
```

### Card Component

```
Variants:     Default, Featured, Horizontal, Compact
Padding:      --space-6 (24px) default, --space-8 (32px) featured
Radius:       --radius-lg
Shadow:       --shadow-md default, --shadow-lg on hover
Border:       1px solid --color-border (optional — use or shadow, not both)

Hover behavior:
  Transform:  translateY(-2px)
  Shadow:     step up one level
  Transition: var(--duration-base) var(--ease-out)

Clickable cards:
  Must have: role="article" or be wrapped in <a>
  Focus state: visible outline on the entire card
  Cursor: pointer
```

### Navigation

```
Desktop nav:
  Height:       64–72px
  Background:   --color-bg or --color-surface with border-bottom
  Max-width:    --max-width container
  Items:        5–7 maximum
  Active state: underline or color change — must be visually distinct
  Sticky:       recommended — use position: sticky, top: 0, z-index: 100
  
Mobile nav:
  Trigger:      Hamburger button, min 44×44px, with aria-label="Open navigation"
  Overlay:      Full-screen or slide-in drawer
  Close:        Visible close button + ESC key support
  Focus trap:   Tab key must stay within open nav
  Animation:    Slide-in or fade, var(--duration-slow) max
  
Skip link:
  "Skip to main content" as first focusable element on every page
  Visible on focus, hidden otherwise
  Links to <main id="main-content">
```

### Hero Section

```
Min height:   100vh (full viewport) or 70vh (partial) — decide per project
Padding:      --space-24 top/bottom (desktop), --space-12 (mobile)
Content max-width: 800px for text-focused, full-bleed for image-led

Required elements:
  H1:     States what the business does and for whom
  Subheading: Expands H1 with key benefit (1–2 sentences)
  Primary CTA: Verb + outcome, --radius-md button, prominent size
  Secondary CTA (optional): lower commitment, ghost or link style

Background options:
  - Solid color (--color-primary or --color-bg)
  - Gradient (brand colors, subtle — not generic purple-to-blue)
  - Full-bleed image with overlay for contrast
  - Split (color left / image right or vice versa)
  - Illustrated or SVG pattern

Typography scale in hero:
  H1: --type-size-6xl desktop, --type-size-4xl mobile
  Subhead: --type-size-lg to --type-size-xl, --weight-regular, --leading-relaxed
```

### Forms (Contact / Quote / Signup)

```
Layout:       Single column on mobile, can be 2-col on desktop for short fields
Field order:  Name → Email → Phone (if needed) → Subject → Message → Submit
Labels:       Above every field, --weight-medium
Submit CTA:   Full-width on mobile, auto-width on desktop, Primary button style
Validation:   Inline on blur — not on submit only
Error display: Below the field that failed, --color-error, with icon
Success state: Inline confirmation message, not a page reload
              "Thank you — we'll be in touch within [X] business days."
```

---

## 6. Visual Direction — UI Style Library

When proposing visual directions, draw from this style library. Always propose exactly 3 directions before committing. Choose styles that fit the brand personality and project type — do not default to the same style repeatedly.

### General UI Styles

| Style | Mood | Best for |
|---|---|---|
| Minimalism / Swiss | Clean, precise, confident | Enterprise, dashboards, documentation |
| Neumorphism | Soft, tactile, calm | Wellness apps, meditation, health |
| Glassmorphism | Modern, layered, premium | SaaS, fintech, creative tools |
| Brutalism | Raw, bold, unforgettable | Design portfolios, art, cultural projects |
| Claymorphism | Friendly, playful, 3D-inflated | SaaS for non-technical users, children |
| Aurora UI | Gradient-rich, ethereal | Modern SaaS, creative agencies |
| Retro-Futurism | Nostalgic + forward, stylized | Gaming, entertainment, music |
| Flat Design | Simple, clear, fast | Startups, MVPs, mobile-first apps |
| Neubrutalism | High-contrast, graphic, Gen Z | Startups, Figma-adjacent brands |
| Bento Box Grid | Modular, organized, modern | Dashboards, portfolios, feature showcases |
| Editorial / Magazine | Typographic, structured, authoritative | Blogs, news, long-form content |
| Organic / Biophilic | Natural textures, curves, earthy | Wellness, sustainability, food |
| Dark Mode (OLED) | Dramatic, focused, premium | Dev tools, SaaS, entertainment |
| Soft UI Evolution | Gentle depth, modern, accessible | Enterprise SaaS, corporate sites |
| Motion-Driven | Kinetic, immersive, dynamic | Portfolio sites, product launches |
| Y2K Aesthetic | Playful, referential, bold | Fashion, music, Gen Z brands |
| Exaggerated Minimalism | Extreme whitespace, typographic | Fashion, architecture, high-end |
| Vintage / Artisan | Handcrafted, warm, authentic | Local food, trades, independent shops |

### Landing Page Patterns

| Pattern | Best for |
|---|---|
| Hero-Centric | Products with strong visual identity |
| Conversion-Optimized | Lead generation, sales pages |
| Feature-Rich Showcase | SaaS, complex products |
| Minimal and Direct | Simple products, apps |
| Social Proof-Focused | Services, B2C products |
| Interactive Product Demo | Software, tools |
| Trust and Authority | B2B, enterprise, consulting |
| Storytelling-Driven | Brands, agencies, nonprofits |

### Dashboard Styles

| Style | Best for |
|---|---|
| Data-Dense | Complex analysis, power users |
| Executive Summary | C-suite, high-level metrics |
| Real-Time Monitoring | Operations, DevOps |
| Drill-Down Analytics | Detailed exploration |
| Financial Dashboard | Finance, accounting |
| Sales Intelligence | Sales teams, CRM |

---

## 7. Aesthetic Execution Rules

These rules apply to every visual direction. They are non-negotiable regardless of style chosen.

### Typography Execution
- Use weight contrast to create hierarchy — not just size
- Pair a display font with a body font — never single-font designs unless intentional and documented
- Avoid identical-weight text at multiple sizes — it creates visual flatness
- Use `text-wrap: balance` on headings to prevent awkward line breaks
- Never use all-caps for body copy — only for labels, badges, and short UI elements
- Line length for body copy: 60–75 characters per line (use `max-width: 72ch`)

### Color Execution
- Dominant color + one sharp accent beats three equally-weighted brand colors
- Background is a design decision — don't default to white; consider off-white, deep navy, warm stone, dark charcoal
- High-saturation color belongs in small doses: CTAs, highlights, icons — not large backgrounds
- Test every color combination in both light and dark environments before committing

### Motion and Interaction
- Default: CSS transitions only — no JS animation library unless the project warrants it
- Page load: one well-orchestrated stagger reveal beats scattered micro-interactions everywhere
- Hover states: subtle is better — transform translateY(-2px), shadow step-up, color shift
- Always include `prefers-reduced-motion` media query:
  ```css
  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
      animation-duration: 0.01ms !important;
      transition-duration: 0.01ms !important;
    }
  }
  ```
- Never animate layout-causing properties (width, height, top, left) — use transform and opacity

### Spatial Composition
- Embrace asymmetry when appropriate — symmetry is safe but forgettable
- Use generous whitespace to group content, not just decorative filler
- Break the grid intentionally — an element that bleeds past the container creates visual interest when used once, not repeatedly
- Overlap elements to create depth without needing shadows
- Diagonal dividers and angled sections: use sparingly, test at every breakpoint

### Backgrounds and Visual Atmosphere
- Avoid flat white or flat gray — add texture, gradient, or tint to create atmosphere
- Grain overlays (CSS or SVG noise filter) add tactility without weight
- Gradient meshes work for hero sections — keep them subtle enough not to compete with text
- Pattern backgrounds: use at very low opacity (3–8%) as texture, never as wallpaper

---

## 8. Dark Mode

Only implement dark mode when:
- The project type genuinely benefits (dev tools, SaaS dashboards, entertainment)
- Brand alignment supports it
- There is time and budget to implement it properly (dark mode done poorly is worse than not having it)

### Dark Mode Token Pattern

```css
/* Light mode (default) — OKLCH values */
:root {
  --color-bg:      oklch(97% 0.005 90);   /* warm off-white */
  --color-text:    oklch(15% 0.010 265);  /* near-black */
  --color-surface: oklch(99% 0.002 90);   /* card surface */
  /* ... full token set */
}

/* Dark mode — derive from brand, not from generic grays */
@media (prefers-color-scheme: dark) {
  :root {
    --color-bg:      oklch(12% 0.010 265); /* near-black, brand-tinted */
    --color-text:    oklch(93% 0.005 90);  /* warm near-white */
    --color-surface: oklch(18% 0.012 265); /* elevated surface */
    /* ... full token set */
  }
}

/* Manual toggle class (if user control is needed) */
[data-theme="dark"] {
  --color-bg:      oklch(12% 0.010 265);
  /* ... */
}
```

### Dark Mode Rules
- Never simply invert colors — dark mode needs its own palette decisions
- Reduce shadow intensity in dark mode — shadows are less visible and can feel heavy
- Use slightly lighter surfaces for elevation (not brighter — lighter gray on dark)
- Images and illustrations may need dark-mode-specific versions or adjustments
- Test contrast for every text/background combination — dark mode has different contrast failure modes than light

---

## 9. Design System Output Block

Before starting any project, produce this formatted summary. It gives Dereck and the client a clear, scannable snapshot of the design direction before a single component is built. Output it at the end of Step 2 (Define) once the visual direction is chosen.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
DESIGN SYSTEM — [Project Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PROJECT TYPE:   [e.g. Small business site / SaaS dashboard / Landing page]
STYLE:          [e.g. Soft UI Evolution / Neubrutalism / Editorial]
KEYWORDS:       [3–5 mood words — e.g. warm, trustworthy, local, bold]

COLORS:
  Primary:      #[hex] — [role, e.g. buttons, links, key UI]
  Secondary:    #[hex] — [role]
  Accent:       #[hex] — [CTAs, highlights]
  Background:   #[hex]
  Surface:      #[hex] — [cards, panels]
  Text:         #[hex]
  Text muted:   #[hex]
  Success:      #16A34A
  Warning:      #D97706
  Error:        #DC2626

TYPOGRAPHY:
  Display:      [Font name] — [Google Fonts URL]
  Body:         [Font name] — [Google Fonts URL]
  Scale:        H1 [size]px / H2 [size]px / H3 [size]px / Body [size]px

SPACING:
  Base unit: 4px | Scale: 4/8/12/16/24/32/48/64/96/128px
  Section separation (desktop): 96px
  Component gap: 24–32px

RADIUS:         [e.g. --radius-md: 8px for buttons/inputs, --radius-lg: 16px for cards]
SHADOWS:        [e.g. --shadow-md for cards, --shadow-lg for modals]

LANDING PATTERN: [e.g. Hero-Centric + Social Proof / Conversion-Optimized]
KEY EFFECTS:    [e.g. Subtle hover lift, staggered page load, CSS transitions only]

AVOID:
  [List 2–4 specific anti-patterns for this project type and style]
  [e.g. "No generic blue gradients / No identical 3-card row / No placeholder fonts"]

STACK:          [Vanilla HTML/CSS/JS / HTML + Tailwind / React + Tailwind]
CMS:            [None / Decap / Sanity / Shopify / Ghost]
HOSTING:        [Netlify (free) / Vercel Pro / GitHub Pages]

SEO PRIORITIES:
  H1 target:    "[Primary keyword — Business Name]"
  Local signal: [City/region to mention in H1 or hero subheading]
  Schema type:  [LocalBusiness @type — e.g. Plumber, Restaurant, Photographer]

PRE-DELIVERY CHECKLIST:
  [ ] Generic-pattern check passed
  [ ] WCAG 2.2 AA accessibility checklist passed
  [ ] SEO technical checklist passed
  [ ] Responsive tested at 360px / 768px / 1280px
  [ ] cursor: pointer on all clickable elements
  [ ] No emojis as icons — SVGs only (Heroicons / Lucide / Phosphor)
  [ ] Hover states with smooth transitions (150–300ms)
  [ ] prefers-reduced-motion respected
  [ ] All images WebP format with alt text
  [ ] Page titles and meta descriptions unique per page
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 10. Chart Type Recommendations (Dashboards and Data)

When speccing SaaS dashboards or any data-heavy interface, specify the right chart type for the data. Wrong chart choices make data harder to understand, not easier.

| Data scenario | Recommended chart | Avoid |
|---|---|---|
| Trend over time (single metric) | Line chart | Bar chart (implies discrete categories) |
| Trend over time (multiple metrics) | Multi-line chart or area chart | Pie chart |
| Comparing categories at a point in time | Bar chart (vertical) | Line chart |
| Comparing many categories | Horizontal bar chart | Vertical bar (labels get cut) |
| Part-to-whole (2–5 segments) | Donut chart | Pie chart with many slices |
| Part-to-whole (many segments) | Stacked bar chart | Donut or pie |
| Distribution of values | Histogram | Line chart |
| Relationship between two variables | Scatter plot | Bar chart |
| Geographic data | Choropleth map or bubble map | Bar chart |
| Progress toward a goal | Progress bar or gauge | Pie chart |
| KPI at a glance (single number) | Stat card with trend indicator | Any chart (overkill for single numbers) |
| Funnel / conversion steps | Funnel chart | Bar chart |
| Real-time monitoring | Line chart with live update | Static snapshot charts |
| Financial performance | Candlestick or OHLC (advanced) / Bar or Line (simple) | Pie chart |
| Ranking | Horizontal bar chart, sorted descending | Pie or donut |
| Heatmap (activity by day/hour) | Calendar heatmap | Bar chart |

### Dashboard Layout Principles
- **KPI cards first** — single numbers with trend arrows at the top. Users scan these before charts.
- **Primary chart below KPIs** — the most important trend or comparison, given the most visual real estate.
- **Secondary charts in a grid** — supporting context, smaller, 2–3 per row.
- **Tables last** — detailed data for users who need to drill down.
- **Empty states on every chart** — what does the user see before there's data? Never leave a blank area.
- **Loading skeletons** — not spinners — for async data. Preserve the layout shape while data loads.
