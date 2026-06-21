# Accessibility Reference

This file covers WCAG 2.2 AA compliance in full — the POUR framework, per-criterion guidance, component-level checklists, ARIA patterns, keyboard navigation requirements, and testing methods. Read this file when speccing components, writing ARIA guidance, running accessibility checks, or delivering any final spec.

Accessibility is non-negotiable on every project. It is not a feature — it is a baseline quality standard. Every design delivered must pass WCAG 2.2 AA.

---

## Table of Contents
1. [The POUR Framework](#1-the-pour-framework)
2. [Perceivable](#2-perceivable)
3. [Operable](#3-operable)
4. [Understandable](#4-understandable)
5. [Robust](#5-robust)
6. [Component-Level Checklists](#6-component-level-checklists)
7. [ARIA Patterns](#7-aria-patterns)
8. [Keyboard Navigation Patterns](#8-keyboard-navigation-patterns)
9. [Testing Methods](#9-testing-methods)
10. [Quick Reference — WCAG 2.2 AA Checklist](#10-quick-reference--wcag-22-aa-checklist)

---

## 1. The POUR Framework

WCAG 2.2 is organized around four principles. Every criterion belongs to one of these:

| Principle | Core question |
|---|---|
| **Perceivable** | Can users perceive all content — regardless of sight, hearing, or other sensory ability? |
| **Operable** | Can users operate all functionality — regardless of how they interact with the page? |
| **Understandable** | Can users understand the content and how the interface works? |
| **Robust** | Does the content work reliably across assistive technologies and browsers? |

Three conformance levels exist: A (minimum), AA (standard — required), AAA (enhanced — aspirational). This skill targets **AA as the baseline** for every project.

---

## 2. Perceivable

### 1.1 — Text Alternatives
**1.1.1 Non-text content (A)**
Every non-text element that conveys information must have a text alternative.

- Informative images: `alt="descriptive text explaining what the image shows"`
- Decorative images: `alt=""` (empty alt, not missing alt)
- Functional images (linked images, icon buttons): `alt="describes the action"` e.g. `alt="Go to homepage"`
- Complex images (charts, graphs): short alt + a longer description in adjacent text or `aria-describedby`
- Icons used as UI controls: `aria-label` on the button, not the icon itself

```html
<!-- Informative image -->
<img src="team.jpg" alt="The Acme Co team at their Sacramento office, 2024">

<!-- Decorative image -->
<img src="divider.svg" alt="">

<!-- Icon button -->
<button aria-label="Close navigation">
  <svg aria-hidden="true" focusable="false">...</svg>
</button>

<!-- Complex chart -->
<figure>
  <img src="chart.png" alt="Bar chart showing revenue growth from 2022–2024">
  <figcaption>Revenue grew 40% year-over-year from 2022 to 2024. Full data in the table below.</figcaption>
</figure>
```

### 1.2 — Time-Based Media
**1.2.1 Audio-only and video-only (A)**
- Audio-only content (podcast, audio clip): provide a transcript
- Video-only content (silent animation): provide a text description or audio description

**1.2.2 Captions for prerecorded video (A)**
- All prerecorded video with audio must have synchronized captions
- Auto-generated captions are not sufficient unless reviewed and corrected

**1.2.3 Audio description or media alternative (A)**
- Prerecorded video must have audio descriptions of visual content not conveyed in dialogue, OR a text alternative

**1.2.5 Audio description for prerecorded video (AA)**
- Full audio descriptions required for all prerecorded synchronized media

**Practical note for most web projects:**
If embedding a YouTube video, always enable captions. If using a background video, it's decorative — use `aria-hidden="true"` on the video element and ensure no critical information is conveyed visually only.

### 1.3 — Adaptable
**1.3.1 Info and relationships (A)**
Structure conveyed visually must also be conveyed programmatically.

- Use semantic HTML: `<h1>`–`<h6>`, `<ul>`, `<ol>`, `<table>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<header>`, `<footer>`
- Don't use `<div>` for structural elements — use the correct semantic element
- Table headers must use `<th>` with `scope` attribute
- Lists must use `<ul>` or `<ol>` — not a series of `<div>` or `<p>` elements styled to look like a list

**1.3.2 Meaningful sequence (A)**
- The reading order of the DOM must match the visual order
- Don't use CSS to reorder content in a way that changes meaning (e.g. flexbox `order` that changes reading sequence)

**1.3.3 Sensory characteristics (A)**
- Never refer to content by shape, color, location, or sound alone
- Don't write "click the green button" or "see the section on the right"
- Write "click the Submit button" or "see the Pricing section"

**1.3.4 Orientation (AA)**
- Content must work in both portrait and landscape orientation
- Don't lock orientation unless essential (e.g. a piano keyboard app)

**1.3.5 Identify input purpose (AA)**
- Form inputs collecting personal information must use `autocomplete` attributes
```html
<input type="email" autocomplete="email">
<input type="tel" autocomplete="tel">
<input type="text" autocomplete="name">
<input type="text" autocomplete="given-name">
<input type="text" autocomplete="family-name">
```

### 1.4 — Distinguishable
**1.4.1 Use of color (A)**
- Color must not be the only visual means of conveying information
- Error states: red color + error icon + error text (not red color alone)
- Required fields: label + asterisk (*) + legend explaining asterisk (not red color alone)
- Links in body text: underline + color (not color alone)

**1.4.2 Audio control (A)**
- Any audio that plays automatically for more than 3 seconds must have a pause/stop control
- Applies to background music, autoplay video with audio, ambient sound

**1.4.3 Contrast — minimum (AA)**
- Normal text (under 18pt / 14pt bold): minimum **4.5:1** contrast ratio
- Large text (18pt+ / 14pt+ bold): minimum **3:1** contrast ratio
- Logo text: no requirement (but should still be legible)
- Placeholder text: must meet 4.5:1 (common failure — light gray placeholder on white)

```
Contrast checking tools:
- WebAIM Contrast Checker: webaim.org/resources/contrastchecker
- Stark (Figma plugin)
- Browser DevTools accessibility panel
```

**1.4.4 Resize text (AA)**
- Text must be resizable up to 200% without loss of content or functionality
- Use `rem` or `em` units for font sizes — not `px` only
- Test by zooming browser to 200%

**1.4.5 Images of text (AA)**
- Don't use images of text when the same visual effect can be achieved with real text
- Exception: logos, decorative text images where appearance is essential

**1.4.10 Reflow (AA)**
- Content must reflow at 320px viewport width without horizontal scrolling
- Equivalent to 400% zoom on a 1280px screen
- Test every layout at 320px

**1.4.11 Non-text contrast (AA)**
- UI components (buttons, inputs, checkboxes) and focus indicators must have 3:1 contrast against adjacent colors
- A light gray button border on a white background is a common failure

**1.4.12 Text spacing (AA)**
- Content must not be lost when these are overridden:
  - Line height to 1.5× font size
  - Letter spacing to 0.12× font size
  - Word spacing to 0.16× font size
  - Spacing after paragraphs to 2× font size
- Test with the Text Spacing bookmarklet

**1.4.13 Content on hover or focus (AA)**
- Tooltip or popover content that appears on hover/focus must be:
  - **Dismissible**: user can close it without moving the pointer (ESC key)
  - **Hoverable**: pointer can move over the tooltip without it disappearing
  - **Persistent**: stays visible while the pointer/focus remains

---

## 3. Operable

### 2.1 — Keyboard Accessible
**2.1.1 Keyboard (A)**
- All functionality must be operable via keyboard alone
- No keyboard traps — user must be able to navigate away from any component
- Test: tab through the entire page without using a mouse

**2.1.2 No keyboard trap (A)**
- If keyboard focus enters a component, the user must be able to leave using standard keys (Tab, Shift+Tab, ESC, Arrow keys)
- Exception: modals and dialogs intentionally trap focus — this is correct behavior — but must be closeable with ESC

**2.1.4 Character key shortcuts (A)**
- If single-character keyboard shortcuts are implemented, they must be remappable, disableable, or only active on focus

### 2.2 — Enough Time
**2.2.1 Timing adjustable (A)**
- If there is a time limit on content or session, user must be able to turn off, adjust, or extend it
- Exception: real-time events (auction countdown where timing is essential)

**2.2.2 Pause, stop, hide (A)**
- Moving, blinking, scrolling content that lasts more than 5 seconds must have a pause/stop control
- Auto-updating content (live feeds, tickers) must have a pause control
- Applies to: carousels, marquees, animated hero backgrounds, auto-playing video

### 2.3 — Seizures and Physical Reactions
**2.3.1 Three flashes or below threshold (A)**
- Content must not flash more than 3 times per second
- Affects: strobe effects, rapid animations, video with fast-cutting
- If in doubt: don't use flashing content

### 2.4 — Navigable
**2.4.1 Bypass blocks (A)**
- Provide a skip navigation link as the first focusable element on every page
```html
<a href="#main-content" class="skip-link">Skip to main content</a>
<!-- Visible on focus, hidden otherwise -->

<style>
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
.skip-link:focus {
  top: 0;
}
</style>
```

**2.4.2 Page titled (A)**
- Every page must have a descriptive `<title>` element
- Format: `Page Name — Site Name`
- Not: "Home" or "Untitled"

**2.4.3 Focus order (A)**
- Tab order must follow a logical reading sequence
- DOM order determines tab order — don't rely on CSS for visual reordering of interactive elements

**2.4.4 Link purpose (A)**
- Link text must describe its destination or purpose
- Don't use "click here," "read more," "learn more" as link text alone
- If visual context makes it clear, use `aria-label` to provide a fuller description for screen readers
```html
<!-- Avoid -->
<a href="/services">Read more</a>

<!-- Better -->
<a href="/services">Read more about our landscaping services</a>

<!-- Or with aria-label -->
<a href="/services" aria-label="Read more about our landscaping services">Read more</a>
```

**2.4.6 Headings and labels (AA)**
- Headings must describe the topic or purpose of the section
- Form labels must describe the input's purpose
- Don't use headings for styling — use CSS classes instead

**2.4.7 Focus visible (AA)**
- Keyboard focus indicator must be visible
- Never: `outline: none` or `outline: 0` without a replacement
- Minimum custom focus style:
```css
:focus-visible {
  outline: 2px solid var(--color-primary);
  outline-offset: 2px;
  border-radius: var(--radius-sm);
}
```

**2.4.11 Focus not obscured — minimum (AA) [New in 2.2]**
- When a component receives focus, it must not be entirely hidden by sticky headers, cookie banners, or other overlapping content
- Test: tab through the page with a sticky header — ensure the focused element is at least partially visible

**2.4.12 Focus not obscured — enhanced (AAA) [New in 2.2]**
- Focused component must be fully visible (not partially obscured)
- Aspire to this — it's achievable with proper scroll-margin-top on focusable elements
```css
:focus {
  scroll-margin-top: 80px; /* height of sticky header */
}
```

### 2.5 — Input Modalities
**2.5.3 Label in name (A)**
- For UI components with visible text labels, the accessible name must contain the visible text
- Don't use an aria-label that's completely different from the button's visible text

**2.5.8 Target size — minimum (AA) [New in 2.2]**
- Interactive targets must be at least 24×24 CSS pixels
- Best practice and strongly recommended: 44×44px
- Exception: inline text links (the line height is the target)

---

## 4. Understandable

### 3.1 — Readable
**3.1.1 Language of page (A)**
- Every page must declare its language
```html
<html lang="en">
```

**3.1.2 Language of parts (AA)**
- If a page contains content in another language, mark it
```html
<p>The French term is <span lang="fr">savoir-faire</span>.</p>
```

### 3.2 — Predictable
**3.2.1 On focus (A)**
- Focusing on a component must not trigger an automatic context change
- Don't auto-submit forms or auto-navigate when a field receives focus

**3.2.2 On input (A)**
- Changing a form control's value must not automatically cause a context change unless the user is warned first
- A dropdown that auto-navigates on selection without a submit button fails this criterion

**3.2.3 Consistent navigation (AA)**
- Navigation repeated across pages must appear in the same order on every page
- Don't reorder nav items between pages

**3.2.4 Consistent identification (AA)**
- Components with the same function across pages must be identified consistently
- If the search icon opens search on one page, it must do the same on all pages

### 3.3 — Input Assistance
**3.3.1 Error identification (A)**
- If an input error is detected, the item in error must be identified and the error described to the user in text
- Not just a red border — must include a text message

**3.3.2 Labels or instructions (A)**
- Provide labels or instructions when content requires user input
- Required fields: mark with asterisk + a legend "* Required"
- Input format requirements: show them before the field, not just in the error message

**3.3.3 Error suggestion (AA)**
- If an input error is detected and a correction is known, the suggestion must be provided
- "Please enter a valid email address" is better than "Invalid input"
- "Phone number must be 10 digits" is better than "Incorrect format"

**3.3.4 Error prevention — legal, financial, data (AA)**
- For transactions with legal or financial consequences, at least one of these must be true:
  - Reversible: submissions can be undone
  - Checked: data is checked for errors before submission
  - Confirmed: mechanism for reviewing and confirming before final submission

**3.3.7 Redundant entry (A) [New in 2.2]**
- Information entered in a previous step must not be asked again in the same process unless re-entering is essential
- Example: if user enters their name in step 1 of a checkout, don't ask again in step 3

**3.3.8 Accessible authentication — minimum (AA) [New in 2.2]**
- Authentication processes must not require cognitive function tests (e.g. solving a puzzle, memorizing an image) unless an alternative is provided
- CAPTCHAs must offer an audio alternative or another method

---

## 5. Robust

### 4.1 — Compatible
**4.1.1 Parsing (A)**
- HTML must be valid and well-formed
- No duplicate IDs, no missing closing tags, no improperly nested elements
- Validate with: validator.w3.org

**4.1.2 Name, role, value (A)**
- All UI components must have an accessible name, role, and value that can be determined programmatically
- Use semantic HTML first — it provides name/role/value automatically
- Use ARIA only when semantic HTML cannot provide the needed role

**4.1.3 Status messages (AA)**
- Status messages (success, error, loading complete) must be programmatically determinable without receiving focus
- Use `role="alert"` for urgent messages (errors), `role="status"` for non-urgent (success)
```html
<!-- Error — announced immediately -->
<div role="alert">Your session has expired. Please log in again.</div>

<!-- Success — announced politely -->
<div role="status">Your changes have been saved.</div>
```

---

## 6. Component-Level Checklists

### Navigation
- [ ] Skip to main content link as first focusable element
- [ ] `<nav>` element with `aria-label="Main navigation"` (or "Secondary navigation" for footer nav)
- [ ] Current page indicated with `aria-current="page"`
- [ ] Mobile nav toggle has `aria-expanded` and `aria-controls`
- [ ] Mobile nav overlay is keyboard navigable and closeable with ESC
- [ ] Focus trapped within open mobile nav, returned to trigger on close
- [ ] All nav items are keyboard accessible (tab order follows visual order)

```html
<nav aria-label="Main navigation">
  <a href="/" aria-current="page">Home</a>
  <a href="/services">Services</a>
  <a href="/contact">Contact</a>
</nav>

<button
  aria-expanded="false"
  aria-controls="mobile-nav"
  aria-label="Open navigation">
  <svg aria-hidden="true" focusable="false">...</svg>
</button>

<div id="mobile-nav" hidden>
  <!-- nav links -->
</div>
```

### Forms
- [ ] Every field has a `<label>` with matching `for`/`id`
- [ ] Required fields marked with asterisk + legend explaining asterisk
- [ ] `autocomplete` attributes on personal data fields
- [ ] Inline validation on blur (not submit-only)
- [ ] Error messages below the field with `aria-describedby` linking field to error
- [ ] Error messages are specific ("Enter a valid email address") not generic
- [ ] Form does not clear valid fields on error
- [ ] Submit button is a `<button type="submit">` or `<input type="submit">`
- [ ] Loading state announced to screen readers

```html
<div class="field">
  <label for="email">Email address *</label>
  <input
    type="email"
    id="email"
    name="email"
    autocomplete="email"
    required
    aria-describedby="email-error"
    aria-invalid="true">
  <span id="email-error" role="alert">
    Please enter a valid email address.
  </span>
</div>
```

### Buttons
- [ ] All buttons are `<button>` elements (not `<div>` or `<span>` styled as buttons)
- [ ] Icon-only buttons have `aria-label` describing the action
- [ ] Disabled buttons have `disabled` attribute (not just `aria-disabled`)
- [ ] Loading buttons announce state change to screen readers
- [ ] Minimum 44×44px touch target

```html
<!-- Icon-only button -->
<button aria-label="Close dialog">
  <svg aria-hidden="true" focusable="false" width="24" height="24">...</svg>
</button>

<!-- Loading state -->
<button aria-disabled="true" aria-describedby="loading-msg">
  <span aria-hidden="true">Submitting...</span>
  <span id="loading-msg" class="sr-only">Submitting your form, please wait.</span>
</button>
```

### Modals and Dialogs
- [ ] Uses `role="dialog"` and `aria-modal="true"`
- [ ] Has `aria-labelledby` pointing to the dialog title
- [ ] Has `aria-describedby` if there is descriptive text
- [ ] Focus moves into the dialog when opened (to first focusable element or dialog title)
- [ ] Focus is trapped within the dialog while open
- [ ] ESC key closes the dialog
- [ ] Focus returns to the trigger element when closed
- [ ] Scroll behind modal is locked on mobile

```html
<div
  role="dialog"
  aria-modal="true"
  aria-labelledby="dialog-title"
  aria-describedby="dialog-desc"
  tabindex="-1">
  <h2 id="dialog-title">Confirm deletion</h2>
  <p id="dialog-desc">This action cannot be undone.</p>
  <button>Cancel</button>
  <button>Delete</button>
</div>
```

### Accordions
- [ ] Trigger is a `<button>` element inside the heading
- [ ] `aria-expanded` toggles between true/false on the trigger
- [ ] `aria-controls` on trigger points to the panel ID
- [ ] Panel has `id` matching `aria-controls`
- [ ] Panel is hidden/shown with `hidden` attribute or `display: none` (not just opacity)

```html
<div class="accordion">
  <h3>
    <button
      aria-expanded="false"
      aria-controls="panel-1">
      What is your return policy?
    </button>
  </h3>
  <div id="panel-1" hidden>
    <p>We offer 30-day returns on all orders...</p>
  </div>
</div>
```

### Cards (Clickable)
- [ ] If the entire card is clickable, wrap in `<a>` tag or use a single link that covers the card
- [ ] Don't stack multiple links/buttons on a clickable card without clear differentiation
- [ ] Card title is in a heading element at the appropriate level
- [ ] Focus state is visible on the entire card

```html
<!-- Entire card is a link -->
<a href="/services/landscaping" class="card">
  <img src="landscaping.jpg" alt="Landscaping service — garden bed installation">
  <h3>Landscaping</h3>
  <p>Full garden design and installation services...</p>
</a>

<!-- Card with multiple actions -->
<article class="card">
  <img src="landscaping.jpg" alt="">
  <h3><a href="/services/landscaping">Landscaping</a></h3>
  <p>Full garden design and installation services...</p>
  <button>Get a quote</button>
</article>
```

### Images and Media
- [ ] All informative images have descriptive alt text
- [ ] All decorative images have `alt=""`
- [ ] SVG icons used as UI controls have `aria-hidden="true"` on the SVG and `aria-label` on the button
- [ ] Background images (CSS) never convey critical information
- [ ] Video has captions
- [ ] Autoplay video is muted, has `aria-hidden="true"`, and has a pause control

### Tables
- [ ] Data tables use `<table>`, `<thead>`, `<tbody>`, `<th>`, `<td>`
- [ ] Column headers use `<th scope="col">`
- [ ] Row headers use `<th scope="row">`
- [ ] Table has a `<caption>` or is labeled with `aria-label` or `aria-labelledby`
- [ ] Complex tables (multiple header levels) use `id` and `headers` attributes
- [ ] Don't use tables for layout — use CSS Grid or Flexbox

---

## 7. ARIA Patterns

### The ARIA Rules

**Rule 1: Use semantic HTML first.** ARIA is a supplement, not a replacement. A `<button>` is always better than `<div role="button">`.

**Rule 2: Don't change native semantics.** Don't add `role="heading"` to a `<p>` element. Use `<h2>` instead.

**Rule 3: All interactive ARIA elements must be keyboard operable.** If you add `role="button"` to a `<div>`, you must also add `tabindex="0"` and keyboard event handlers.

**Rule 4: Don't use `role="presentation"` or `aria-hidden="true"` on focusable elements.**

**Rule 5: Interactive elements must have an accessible name.** Buttons, links, inputs — all must have a label.

### Common ARIA Roles

| Role | When to use | HTML equivalent |
|---|---|---|
| `role="alert"` | Urgent status messages | — (no HTML equivalent) |
| `role="status"` | Non-urgent status messages | — |
| `role="dialog"` | Modal dialogs | `<dialog>` |
| `role="navigation"` | Nav landmark | `<nav>` |
| `role="main"` | Main content | `<main>` |
| `role="banner"` | Site header | `<header>` (top-level) |
| `role="contentinfo"` | Site footer | `<footer>` (top-level) |
| `role="search"` | Search landmark | `<search>` (new) |
| `role="complementary"` | Sidebar | `<aside>` |
| `role="tab"` | Tab control | — |
| `role="tabpanel"` | Tab panel | — |
| `role="tooltip"` | Tooltip | — |

### Common ARIA Properties

| Property | Purpose | Example |
|---|---|---|
| `aria-label` | Provides an accessible name | `aria-label="Close dialog"` |
| `aria-labelledby` | Points to element that labels this one | `aria-labelledby="modal-title"` |
| `aria-describedby` | Points to element that describes this one | `aria-describedby="field-error"` |
| `aria-expanded` | State of collapsible content | `aria-expanded="false"` |
| `aria-controls` | Points to element this one controls | `aria-controls="nav-menu"` |
| `aria-hidden` | Hides from assistive tech | `aria-hidden="true"` |
| `aria-live` | Announces dynamic content updates | `aria-live="polite"` |
| `aria-current` | Current item in set | `aria-current="page"` |
| `aria-invalid` | Field has error | `aria-invalid="true"` |
| `aria-required` | Field is required | `aria-required="true"` |
| `aria-disabled` | Element is disabled | `aria-disabled="true"` |

### Live Regions

Use live regions for dynamic content updates that need to be announced without focus change:

```html
<!-- Polite: announced at next break in speech (success messages, cart updates) -->
<div aria-live="polite" aria-atomic="true">
  Item added to cart.
</div>

<!-- Assertive: announced immediately, interrupts current speech (errors, urgent alerts) -->
<div aria-live="assertive" role="alert">
  Session expired. Please log in again.
</div>
```

---

## 8. Keyboard Navigation Patterns

### Standard Keyboard Interactions

| Key | Action |
|---|---|
| Tab | Move focus to next interactive element |
| Shift + Tab | Move focus to previous interactive element |
| Enter | Activate link or button |
| Space | Activate button; scroll page |
| ESC | Close modal, dropdown, tooltip, or cancel action |
| Arrow keys | Navigate within a widget (menu, tabs, listbox, slider) |
| Home / End | Jump to first/last item in a list or widget |

### Widget-Specific Patterns

**Dropdown menus:**
- Tab to the menu trigger button
- Enter/Space opens the menu
- Arrow keys navigate items
- ESC closes menu and returns focus to trigger
- Tab closes menu and moves to next element

**Tabs:**
- Tab moves focus to the active tab
- Arrow keys move between tabs (left/right)
- Enter/Space activates the focused tab
- Home/End jump to first/last tab

**Modals:**
- Focus moves into modal on open (first focusable element)
- Tab cycles through focusable elements inside modal only (trapped)
- ESC closes modal
- Focus returns to trigger element on close

**Accordions:**
- Tab to the accordion trigger button
- Enter/Space toggles the panel
- Arrow keys navigate between accordion headers (optional but recommended)

**Carousels:**
- Tab to the carousel region
- Previous/Next buttons are keyboard focusable
- Auto-play must be pauseable
- Arrow keys navigate slides (optional)

### Focus Management Rules
- When a modal or overlay opens: move focus INTO it immediately
- When a modal or overlay closes: return focus TO the trigger that opened it
- When content is added dynamically: move focus to the new content OR use a live region to announce it
- When an error occurs: move focus to the first error OR use `role="alert"` to announce it
- Never move focus unexpectedly without user initiation

---

## 9. Testing Methods

### Manual Testing (required for every project)

**Keyboard-only test:**
1. Disconnect or ignore the mouse
2. Tab through the entire page from top to bottom
3. Verify: every interactive element is reachable, focus is always visible, tab order is logical, all modals/overlays can be opened and closed, no keyboard traps

**Screen reader test (basic):**
- macOS: VoiceOver (built-in) — CMD + F5 to enable
- Windows: NVDA (free) or JAWS
- Mobile: iOS VoiceOver or Android TalkBack
- Test: headings structure, form labels, image alt text, button names, live region announcements

**Zoom test:**
1. Set browser to 200% zoom
2. Verify: no horizontal scroll, no content overlap, no text cut off, all functionality still works

**Color contrast test:**
- Use WebAIM Contrast Checker or Stark (Figma)
- Check every text/background combination
- Check UI components (button borders, input borders) for 3:1 non-text contrast

**Reflow test:**
1. Set browser viewport to 320px wide (or zoom to 400% on 1280px)
2. Verify: all content readable, no horizontal scroll, no loss of functionality

### Automated Testing (catches ~30% of issues)
- **axe DevTools** (Chrome extension): free, catches common WCAG violations
- **WAVE** (Chrome extension): visual accessibility feedback
- **Lighthouse** (Chrome DevTools): accessibility audit with score
- **HTMLValidate** or **W3C Validator**: catches structural HTML errors

Automated tools are helpful but cannot catch: focus management, keyboard traps, logical reading order, meaningful alt text quality, color-only meaning issues, or cognitive accessibility problems. Manual testing is always required.

---

## 10. Quick Reference — WCAG 2.2 AA Checklist

Run this checklist before finalizing every project. Mark each item Pass / Fail / N/A.

### Perceivable
- [ ] All images have alt text (informative) or alt="" (decorative)
- [ ] Video has captions
- [ ] Color is not the only means of conveying information
- [ ] Normal text contrast: 4.5:1 minimum
- [ ] Large text contrast: 3:1 minimum
- [ ] UI component contrast: 3:1 minimum
- [ ] Focus indicator contrast: 3:1 minimum
- [ ] Text resizable to 200% without loss of content
- [ ] Content reflows at 320px without horizontal scroll
- [ ] Placeholder text meets contrast requirements
- [ ] Autoplay audio/video has a pause/stop control
- [ ] Personal data inputs have autocomplete attributes
- [ ] Orientation not locked (unless essential)

### Operable
- [ ] All functionality operable by keyboard alone
- [ ] No keyboard traps
- [ ] Skip to main content link present and working
- [ ] Every page has a descriptive title
- [ ] Tab order is logical and follows reading order
- [ ] Link text describes destination or purpose
- [ ] Headings describe their sections
- [ ] Focus is always visible (no outline: none without replacement)
- [ ] Sticky headers do not fully obscure focused elements
- [ ] Touch targets are minimum 24×24px (ideally 44×44px)
- [ ] Moving/blinking content can be paused or stopped
- [ ] No content flashes more than 3 times per second

### Understandable
- [ ] Page language declared in `<html lang="...">`
- [ ] Focusing a component does not trigger unexpected context change
- [ ] Navigation is consistent across pages
- [ ] Components with same function identified consistently
- [ ] Form errors identified in text (not color alone)
- [ ] Error messages are specific and suggest corrections
- [ ] Required fields labeled with asterisk + legend
- [ ] No repeated entry of same information within a single process
- [ ] Authentication does not require solving a puzzle without alternative

### Robust
- [ ] HTML is valid (no duplicate IDs, proper nesting)
- [ ] All interactive elements have accessible name, role, and value
- [ ] ARIA used correctly and only when semantic HTML is insufficient
- [ ] Status messages announced without requiring focus
- [ ] `role="alert"` for urgent messages, `role="status"` for non-urgent
