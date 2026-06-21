# SEO Basics Reference

SEO is a design concern, not just a developer or marketing concern. Every layout decision, heading structure, page title, image, and URL affects how a site ranks and how Google understands what the business does. Read this file during Step 3 (Develop) and Step 4 (Deliver) for any project where search visibility matters — which is almost every client site.

This file covers on-page SEO that intersects directly with design and front-end decisions. It does not cover off-page SEO (link building, PR) or paid search — those are outside the scope of this skill.

---

## Table of Contents
1. [Why SEO Is a Design Decision](#1-why-seo-is-a-design-decision)
2. [Page Titles and Meta Descriptions](#2-page-titles-and-meta-descriptions)
3. [Heading Structure](#3-heading-structure)
4. [URL Structure](#4-url-structure)
5. [Image SEO](#5-image-seo)
6. [Core Web Vitals — Performance as SEO](#6-core-web-vitals--performance-as-seo)
7. [Local SEO for Small Business Sites](#7-local-seo-for-small-business-sites)
8. [Structured Data / Schema Markup](#8-structured-data--schema-markup)
9. [Content Structure for SEO](#9-content-structure-for-seo)
10. [Technical SEO Checklist](#10-technical-seo-checklist)
11. [SEO Anti-Patterns](#11-seo-anti-patterns)
12. [Answer Engine Optimization (AEO)](#12-answer-engine-optimization-aeo)

---

## 1. Why SEO Is a Design Decision

Most SEO failures on small business sites are not content failures — they are design and structure failures. The design team is responsible for:

- **Heading hierarchy** — one H1 per page, logical H2/H3 structure
- **Page titles** — descriptive, unique, under 60 characters
- **URL structure** — clean, readable, keyword-relevant
- **Image optimization** — file size, format, alt text, dimensions
- **Page speed** — layout choices that affect Core Web Vitals
- **Mobile usability** — Google uses mobile-first indexing
- **Internal linking** — how pages connect to each other
- **Informational hierarchy** — what Google reads first matches what the business wants to rank for

Every design decision either helps or hurts SEO. Build it in from the start — retrofitting SEO onto a finished site is harder and less effective.

---

## 2. Page Titles and Meta Descriptions

### Page Titles (`<title>`)

The page title is the single most important on-page SEO element. It appears in:
- Browser tab
- Google search results (the blue clickable headline)
- Social share previews

**Rules:**
- Unique title for every page — no two pages share a title
- Under 60 characters (Google truncates at ~60)
- Include the primary keyword naturally — don't force it
- Format: `Primary Keyword — Business Name` or `Business Name | Primary Keyword`
- Never: "Home" or "Untitled" or "Page 1"

**Templates by project type:**

```
Small business homepage:
"[City] [Service] | [Business Name]"
→ "Sacramento Plumber | Rodriguez Plumbing"

Service page:
"[Service] in [City] | [Business Name]"
→ "Bathroom Remodeling in Modesto | Tile Pro"

About page:
"About [Business Name] | [Service] in [City]"
→ "About Rodriguez Plumbing | Sacramento Plumber"

Contact page:
"Contact [Business Name] | [City] [Service]"
→ "Contact Rodriguez Plumbing | Sacramento Plumber"

Blog post:
"[Post title] | [Business Name]"
→ "How to Fix a Leaking Faucet | Rodriguez Plumbing"
```

### Meta Descriptions

Meta descriptions don't directly affect rankings but dramatically affect click-through rate from search results. Google sometimes ignores them and generates its own — but well-written ones get used.

**Rules:**
- Unique description for every page
- 120–155 characters (Google truncates beyond this)
- Include the primary keyword naturally
- End with a clear CTA or value proposition
- Write for the human who sees this in search results, not for Google

**Template:**
```
[What the business does] in [location]. [Key benefit or differentiator]. [CTA].
```

**Example:**
```
Expert plumbing services in Sacramento, CA. Licensed, insured, and available
24/7 for emergencies. Call today for a free estimate. (154 characters)
```

### Implementation in HTML

```html
<head>
  <title>Sacramento Plumber | Rodriguez Plumbing</title>
  <meta name="description"
        content="Expert plumbing services in Sacramento, CA. Licensed, insured,
                 and available 24/7 for emergencies. Call today for a free estimate.">

  <!-- Open Graph (social sharing) -->
  <meta property="og:title" content="Sacramento Plumber | Rodriguez Plumbing">
  <meta property="og:description" content="Expert plumbing services in Sacramento, CA...">
  <meta property="og:image" content="https://example.com/assets/og-image.jpg">
  <meta property="og:url" content="https://example.com">
  <meta property="og:type" content="website">

  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:title" content="Sacramento Plumber | Rodriguez Plumbing">
</head>
```

---

## 3. Heading Structure

Headings are how Google understands the structure and content of a page. They are also accessibility landmarks (screen readers navigate by headings). Design and SEO goals align perfectly here.

### Rules

**One H1 per page — exactly one, never zero, never two.**
The H1 is the page's main topic. It should:
- State what the business does and who it's for
- Include the primary keyword naturally
- Match or closely relate to the page title

**H2s define the main sections of the page.**
Each H2 should describe what that section covers. Google reads H2s to understand page structure.

**H3s are subsections within H2 sections.**
Use for breaking up long content, FAQs, feature groups.

**Never use headings for styling alone.**
If you want large text, use CSS classes — don't bump something to H1 because it "looks right."

### Heading Structure by Page Type

**Homepage:**
```
H1: Sacramento Plumber — Rodriguez Plumbing
  H2: Our Plumbing Services
    H3: Drain Cleaning
    H3: Water Heater Installation
    H3: Emergency Repairs
  H2: Why Choose Rodriguez Plumbing
  H2: What Our Customers Say
  H2: Serving Sacramento and Surrounding Areas
  H2: Contact Us Today
```

**Service page:**
```
H1: Bathroom Remodeling in Modesto, CA
  H2: Our Bathroom Remodeling Process
    H3: Step 1: Free Consultation
    H3: Step 2: Design and Planning
    H3: Step 3: Installation
  H2: Bathroom Remodeling Costs
  H2: Before and After Gallery
  H2: Frequently Asked Questions
```

**Blog post:**
```
H1: How to Fix a Leaking Kitchen Faucet (Step-by-Step Guide)
  H2: What You'll Need
  H2: Step 1: Turn Off the Water Supply
  H2: Step 2: Remove the Faucet Handle
  H2: When to Call a Plumber Instead
```

### Common Heading Mistakes to Avoid
- Using H1 for the site logo or tagline instead of the page topic
- Multiple H1s on a single page
- Skipping heading levels (H1 → H3 with no H2)
- Decorative text elements marked as headings
- Generic H1s like "Welcome" or "Home"

---

## 4. URL Structure

URLs appear in search results and are a minor ranking signal. More importantly, clean URLs build trust with users who see them before clicking.

### Rules
- Use hyphens to separate words — never underscores, spaces, or camelCase
- All lowercase
- Short and descriptive — include the primary keyword, skip filler words
- Match the page content — the URL should describe what's on the page
- No dynamic parameters for content pages (`?id=123` is bad for static pages)

### URL Structure Templates

```
Homepage:
https://example.com/

Service page:
https://example.com/services/bathroom-remodeling/

About:
https://example.com/about/

Contact:
https://example.com/contact/

Blog index:
https://example.com/blog/

Blog post:
https://example.com/blog/how-to-fix-leaking-faucet/

Location page (multi-location businesses):
https://example.com/sacramento-plumber/
https://example.com/modesto-plumber/
```

### Bad URL Examples and Fixes

| Bad | Good | Why |
|---|---|---|
| `/page?id=42` | `/services/drain-cleaning/` | Descriptive, keyword-rich |
| `/Services/BathroomRemodeling` | `/services/bathroom-remodeling/` | Lowercase, hyphens |
| `/my-awesome-new-post-about-plumbing-tips-for-homeowners` | `/blog/plumbing-tips-homeowners/` | Concise |
| `/home` | `/` | Homepage is always root |

---

## 5. Image SEO

Images are one of the most commonly botched SEO elements on small business sites. Getting them right improves both SEO and page speed.

### File Names
- Rename files before uploading — never `IMG_4832.jpg` or `screenshot001.png`
- Use descriptive, hyphen-separated names
- Include the keyword where natural
```
Bad:  IMG_4832.jpg
Good: sacramento-plumber-bathroom-renovation.webp
```

### Alt Text
Alt text serves two purposes: accessibility (screen readers) and SEO (Google reads alt text to understand images).

```html
<!-- Informative image -->
<img src="bathroom-renovation-modesto.webp"
     alt="Completed bathroom renovation in Modesto CA — new tile, vanity, and fixtures">

<!-- Team photo -->
<img src="rodriguez-plumbing-team.webp"
     alt="The Rodriguez Plumbing team in front of their Sacramento office">

<!-- Decorative image -->
<img src="divider-pattern.svg" alt="">
```

**Alt text rules:**
- Describe what's actually in the image
- Include location and service keywords where naturally relevant
- Don't keyword-stuff ("plumber Sacramento CA plumbing service Sacramento" is spam)
- Keep under 125 characters
- Decorative images get empty alt (`alt=""`) — never skip the attribute entirely

### Image Format and Size
- Use **WebP** as the primary format — smaller file size, same quality
- Fall back to JPEG for older browser compatibility using `<picture>`
- **Never serve images larger than they display** — a hero image that displays at 1200px should be max 1200px wide
- Compress before uploading — target under 200KB for most images, under 100KB for thumbnails

```html
<!-- Responsive image with WebP and JPEG fallback -->
<picture>
  <source srcset="hero-bathroom.webp" type="image/webp">
  <img src="hero-bathroom.jpg"
       alt="Bathroom remodeling service in Modesto CA"
       width="1200"
       height="600"
       loading="lazy">
</picture>

<!-- Hero image (above fold) — do NOT lazy load -->
<img src="hero-bathroom.webp"
     alt="Bathroom remodeling service in Modesto CA"
     width="1200"
     height="600"
     fetchpriority="high">
```

---

## 6. Core Web Vitals — Performance as SEO

Google uses Core Web Vitals as a ranking signal. They measure real user experience — not just page speed. Poor Core Web Vitals hurt rankings, especially on mobile.

### The Three Core Web Vitals

**LCP — Largest Contentful Paint**
How long it takes for the largest visible element (usually the hero image or heading) to load.
- Good: under 2.5 seconds
- Needs improvement: 2.5–4 seconds
- Poor: over 4 seconds

**Design decisions that affect LCP:**
- Hero image file size and format (WebP, properly sized)
- Not lazy-loading the hero image (`fetchpriority="high"` instead)
- Render-blocking CSS or JS in `<head>`
- Web font loading strategy (`font-display: swap`, preconnect)

**INP — Interaction to Next Paint** (replaced FID in 2024)
How quickly the page responds to user interactions (clicks, taps, key presses).
- Good: under 200ms
- Poor: over 500ms

**Design decisions that affect INP:**
- Heavy JavaScript that blocks the main thread
- Complex animations running on scroll
- Too many event listeners

**CLS — Cumulative Layout Shift**
How much the page layout shifts as it loads (images popping in, fonts loading, ads moving content).
- Good: under 0.1
- Poor: over 0.25

**Design decisions that affect CLS:**
- Always specify `width` and `height` on `<img>` tags
- Use `aspect-ratio` CSS for responsive images
- Load web fonts without causing layout shift (`font-display: swap`)
- Reserve space for dynamic content (ads, embeds)

### How to Check Core Web Vitals
- **Google PageSpeed Insights**: pagespeed.web.dev — test any URL, get field and lab data
- **Lighthouse** in Chrome DevTools — run locally
- **Google Search Console** → Core Web Vitals report (for live sites)

Target: all three in the green zone on both mobile and desktop before delivery.

---

## 7. Local SEO for Small Business Sites

Local SEO is the highest-leverage SEO work for small business clients. A well-optimized local site can rank in Google's Map Pack (the three businesses shown with a map at the top of local search results) — which drives significant call volume.

### Google Business Profile (GBP)
This is separate from the website but deeply connected to it. Always recommend clients set this up or claim their existing listing.

**Key GBP optimization points:**
- Business name exactly as it appears everywhere (no keyword stuffing in the name)
- Primary category that best describes the business
- Complete address and service area
- Phone number (must match the website exactly)
- Website URL
- Business hours (keep updated)
- Photos — real photos, updated regularly
- Reviews — encourage happy customers to leave Google reviews

### NAP Consistency
**NAP = Name, Address, Phone number.** These must be identical everywhere:
- Website (footer, contact page, header)
- Google Business Profile
- Yelp, Facebook, and other directories
- Any other site that mentions the business

Even minor inconsistencies (St. vs Street, Suite vs Ste) can hurt local rankings.

### Local SEO On-Page Elements

**H1 includes location:**
```
"Sacramento Plumber | Rodriguez Plumbing"
"Tile Installation Services in Modesto, CA"
```

**Homepage copy mentions location naturally:**
```
"Serving Sacramento, Elk Grove, Roseville, and surrounding areas..."
"Locally owned and operated in Modesto's Central Valley since 2010..."
```

**Footer includes full NAP:**
```html
<footer>
  <address>
    <strong>Rodriguez Plumbing</strong><br>
    1234 Main Street, Sacramento, CA 95814<br>
    <a href="tel:+19165551234">(916) 555-1234</a><br>
    Mon–Fri: 7am–6pm | Sat: 8am–4pm | 24/7 Emergency Service
  </address>
</footer>
```

**Embed Google Maps on contact page:**
```html
<!-- Google Maps embed — helps confirm location to Google -->
<iframe
  src="https://www.google.com/maps/embed?pb=..."
  width="600"
  height="450"
  loading="lazy"
  title="Rodriguez Plumbing location on Google Maps"
  aria-label="Map showing Rodriguez Plumbing location in Sacramento CA">
</iframe>
```

### Location Pages (Multi-Location Businesses)
If a business serves multiple cities, create a dedicated page per city:
```
/sacramento-plumber/
/modesto-plumber/
/stockton-plumber/
```

Each page must have unique content — not copy-pasted with the city name swapped. Google penalizes thin, duplicate location pages.

### Local Schema Markup
Add `LocalBusiness` schema to the homepage (see Section 8).

---

## 8. Structured Data / Schema Markup

Schema markup (also called structured data) helps Google understand what type of business a site represents and can unlock rich results in search (star ratings, FAQs, business hours in the search result).

### LocalBusiness Schema (Small Business Sites)

Add to the `<head>` or as a `<script>` tag in the body of the homepage:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Plumber",
  "name": "Rodriguez Plumbing",
  "image": "https://example.com/assets/rodriguez-plumbing-logo.png",
  "url": "https://example.com",
  "telephone": "+19165551234",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "1234 Main Street",
    "addressLocality": "Sacramento",
    "addressRegion": "CA",
    "postalCode": "95814",
    "addressCountry": "US"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 38.5816,
    "longitude": -121.4944
  },
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday"],
      "opens": "07:00",
      "closes": "18:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Saturday",
      "opens": "08:00",
      "closes": "16:00"
    }
  ],
  "priceRange": "$$",
  "areaServed": ["Sacramento", "Elk Grove", "Roseville", "Modesto"],
  "sameAs": [
    "https://www.facebook.com/rodriguezplumbing",
    "https://www.yelp.com/biz/rodriguez-plumbing"
  ]
}
</script>
```

**`@type` values by business type:**
- Plumber, Electrician, HVACBusiness, Locksmith (trades)
- Restaurant, FoodEstablishment (food)
- BeautySalon, HairSalon, DaySpa (wellness)
- LegalService, AccountingService (professional services)
- Florist, ClothingStore, BookStore (retail)
- Photographer, Artist (creative)
- GeneralContractor, RoofingContractor (construction)

### FAQ Schema

Add to pages with FAQ sections to potentially unlock FAQ rich results in Google:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "How much does drain cleaning cost in Sacramento?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Drain cleaning in Sacramento typically costs between $150 and $350 depending on the severity of the clog and accessibility. We offer free estimates — call us today."
      }
    },
    {
      "@type": "Question",
      "name": "Do you offer emergency plumbing services?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes. Rodriguez Plumbing provides 24/7 emergency plumbing services throughout Sacramento and surrounding areas. Call (916) 555-1234 any time."
      }
    }
  ]
}
</script>
```

### Validate Schema
Always validate before delivery: **schema.org/SchemaValidator** or **Google's Rich Results Test** (search.google.com/test/rich-results)

---

## 9. Content Structure for SEO

### Keyword Strategy for Small Business Sites
Most small business clients don't need a complex keyword strategy. Focus on:

1. **Primary keyword** — what the business does + where
   - "Sacramento plumber" / "Modesto tile installation" / "Bay Area landscaping"

2. **Service keywords** — specific services, one per page
   - "drain cleaning Sacramento" / "bathroom tile installation Modesto"

3. **Long-tail keywords** — questions people actually search
   - "how much does a plumber cost in Sacramento"
   - "best tile installer near me Modesto CA"

### Content Length Guidelines

| Page type | Minimum word count | Notes |
|---|---|---|
| Homepage | 300–500 words | Focus on clarity, not length |
| Service page | 500–800 words | Describe the service in detail |
| Location page | 400–600 words | Unique content per location |
| Blog post | 800–1500+ words | More depth = more rankable |
| Contact page | 150–250 words | Short is fine — it's not a ranking page |
| About page | 300–500 words | Human and specific |

### Internal Linking

Internal links help Google discover pages and understand site structure. They also keep visitors on the site longer.

**Rules:**
- Every page should be reachable within 2–3 clicks from the homepage
- Link from high-authority pages (homepage, service index) to deeper pages
- Use descriptive anchor text: "our drain cleaning service" not "click here"
- Link to related content from blog posts
- Never orphan a page (a page with no internal links pointing to it)

**Practical pattern for small business sites:**
```
Homepage → links to all service pages
Each service page → links to contact page and 2–3 related services
Blog posts → link to relevant service pages
Contact page → links back to homepage and services
```

---

## 10. Technical SEO Checklist

Run before every delivery. Mark each item Pass / Fail / N/A.

### Essential (every project)
- [ ] Unique `<title>` on every page (under 60 characters)
- [ ] Unique `<meta name="description">` on every page (120–155 characters)
- [ ] One `<h1>` per page — no more, no less
- [ ] Logical heading hierarchy (H1 → H2 → H3, no skipping)
- [ ] All images have descriptive alt text (or `alt=""` for decorative)
- [ ] All image files are WebP format, properly sized, under 200KB
- [ ] `<img>` tags have `width` and `height` attributes
- [ ] Hero/above-fold image has `fetchpriority="high"`, NOT `loading="lazy"`
- [ ] Below-fold images have `loading="lazy"`
- [ ] Clean URL structure (lowercase, hyphens, descriptive)
- [ ] `lang` attribute on `<html>` element
- [ ] Viewport meta tag: `<meta name="viewport" content="width=device-width, initial-scale=1">`
- [ ] Canonical tag on each page: `<link rel="canonical" href="[full URL]">`
- [ ] Open Graph tags (og:title, og:description, og:image, og:url)
- [ ] Robots.txt file present (allows all by default, no accidental blocking)
- [ ] Sitemap.xml generated and linked in robots.txt
- [ ] No broken internal links
- [ ] All pages internally linked — no orphaned pages
- [ ] PageSpeed Insights score: Performance 80+ on mobile

### Local business (add to above)
- [ ] NAP (Name, Address, Phone) in footer — consistent with GBP
- [ ] Location mentioned naturally in H1 or hero subheading
- [ ] Google Maps embed on contact page
- [ ] LocalBusiness schema markup on homepage
- [ ] FAQ schema on pages with FAQ sections (if applicable)
- [ ] Google Business Profile claimed and complete (advise client)

### Blog / content site (add to above)
- [ ] Every post has a unique title and meta description
- [ ] Author name and publish date visible
- [ ] Internal links from posts to relevant service or product pages
- [ ] Images in posts have alt text
- [ ] Posts have a clear H1 and logical H2 structure

---

## 11. SEO Anti-Patterns

### Multiple H1s
**Pattern:** Marking the logo, tagline, AND page title all as H1.
**Fix:** One H1 per page — the page's main topic. Logo = `<a>` inside `<header>`. Tagline = `<p>` or styled text.

### Duplicate Page Titles
**Pattern:** Every page has the title "Business Name" with no page-specific descriptor.
**Fix:** Unique, descriptive title per page following the templates in Section 2.

### Missing or Duplicate Meta Descriptions
**Pattern:** No meta descriptions, or the same description copy-pasted across all pages.
**Fix:** Unique description per page, written for the human reader, 120–155 characters.

### Keyword Stuffing
**Pattern:** "Sacramento plumber Sacramento CA plumbing services Sacramento best plumber Sacramento"
**Fix:** Use the primary keyword once naturally in the H1, once in the first paragraph, once in a H2, and in the meta title/description. That's enough.

### Images Without Alt Text
**Pattern:** `<img src="photo.jpg">` with no alt attribute at all.
**Fix:** Always include alt attribute. Describe the image naturally, include location/service keyword where relevant.

### Non-Descriptive Anchor Text
**Pattern:** "Click here to learn more about our services"
**Fix:** "Learn more about our drain cleaning services in Sacramento"

### Blocking Crawlers Accidentally
**Pattern:** A `robots.txt` file with `Disallow: /` left from development, or `<meta name="robots" content="noindex">` on pages that should be indexed.
**Fix:** Review robots.txt and meta robots tags before every launch.

### No Sitemap
**Pattern:** No sitemap.xml — Google has to discover all pages by crawling links.
**Fix:** Generate a sitemap and submit to Google Search Console. For vanilla HTML sites, create `sitemap.xml` manually or use an online generator. For Next.js/Astro/etc., use the built-in sitemap generation.

### Thin Location Pages
**Pattern:** Copy-pasted location pages where only the city name changes.
**Fix:** Each location page needs unique content — specific service area details, local references, unique customer stories or testimonials from that area.

### Ignoring Mobile Performance
**Pattern:** Beautiful desktop design that scores 30/100 on mobile PageSpeed Insights.
**Fix:** Test on mobile from the start. Core Web Vitals on mobile are Google's primary ranking signal — mobile score matters more than desktop.

---

## 12. Answer Engine Optimization (AEO)

A growing share of searches now end inside an AI answer — ChatGPT, Perplexity, Google AI Overviews, Gemini — where the user reads a synthesized response and never clicks a blue link. AEO is the practice of structuring a site so those engines extract and **cite** it as the answer. It is not a replacement for SEO; it builds on the same foundation, and most AEO work also improves traditional rankings. For local service businesses this is a real opportunity: someone asking an assistant "who's a reliable plumber near Manteca?" is a high-intent lead, and the businesses structured to be cited will win those.

### How AEO differs from classic SEO

| Classic SEO | AEO |
|---|---|
| Goal: rank in the list of links | Goal: be the source the AI quotes |
| Success = clicks and sessions | Success = citations, mentions, assisted calls/conversions |
| Optimizes pages for crawlers | Optimizes passages for extraction |

### What actually moves citations (do these)

1. **Answer-first structure.** Lead every section with a direct, one- to two-sentence answer, then expand. AI engines extract the clean answer near a heading. Burying it in paragraph four loses the citation.
2. **Sequential, descriptive headings.** Strict H1 → H2 → H3 hierarchy, with headings phrased the way people ask questions ("How much does a kitchen remodel cost?"). Well-structured pages are cited meaningfully more often than unstructured ones.
3. **A real FAQ section with `FAQPage` schema.** Build it from actual customer questions (pull these from the client's call logs, emails, the discovery questionnaire). Each Q is a heading, each A leads with the direct answer. `FAQPage`, `HowTo`, and `Article` schema all measurably lift citation likelihood.
4. **Plain, extractable facts.** State services, areas served, hours, certifications, pricing approach, and "what makes us different" as clear declarative sentences — not buried in marketing prose. Tables, ordered lists, and step-by-step formats extract especially well.
5. **Freshness.** AI engines heavily favor recently updated pages — the large majority of citations for commercial queries come from content updated within the last year. Put a visible "last updated" date on key pages and refresh the top few pages quarterly.
6. **Entity consistency (this is the local advantage).** Keep Name / Address / Phone identical across the site, the footer, schema, and especially the **Google Business Profile**. Consistent entity signals + a complete, active GBP are what make a local business legible to AI answers. Encourage and respond to reviews.

### AEO checklist (small-business site)

- [ ] Every key page opens with a direct answer to the question it targets
- [ ] Headings are sequential and phrased as real user questions
- [ ] A FAQ section exists, built from real customer questions, with `FAQPage` schema
- [ ] Services, areas served, and hours are stated as plain facts (and in `LocalBusiness` schema)
- [ ] NAP is identical across site, schema, and Google Business Profile
- [ ] Google Business Profile is complete, categorized, and active
- [ ] Key pages carry a visible last-updated date; a refresh cadence is set
- [ ] Comparison/pricing/process info uses lists or tables where possible

### Measuring it

There's no rank tracker for AI answers, so test directly: write 10–15 questions a real customer would ask, run them across ChatGPT, Perplexity, and Google AI Overviews, and note where the client's business is cited or mentioned versus competitors. Re-run quarterly and after content refreshes to see what's moving. Track the indirect payoff too — calls and form fills from people who "found you through AI" or a voice assistant.
