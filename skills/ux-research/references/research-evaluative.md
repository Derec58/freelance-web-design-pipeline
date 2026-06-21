# UX Research — Evaluative Reference

This file covers all evaluative and post-generative research methods: usability testing, heuristic audits, analytics interpretation, heatmap and session recording analysis, A/B testing, synthesis artifacts, and post-launch research. Read this file during Step 3 (Develop) and Step 4 (Deliver) of the Double Diamond, during audit mode, and for any post-launch review work.

For generative research (discovery, proto-personas, JTBD, card sorting, surveys), read `references/research-generative.md`.

---

## Table of Contents
1. [Usability Testing](#1-usability-testing)
2. [Heuristic and Expert Reviews](#2-heuristic-and-expert-reviews)
3. [Analytics Interpretation](#3-analytics-interpretation)
4. [Heatmap and Session Recording Analysis](#4-heatmap-and-session-recording-analysis)
5. [A/B Testing and Experimentation](#5-ab-testing-and-experimentation)
6. [Synthesis Artifacts](#6-synthesis-artifacts)
7. [Post-Launch Research](#7-post-launch-research)

---

## 1. Usability Testing

### When to Use
- Before launch: test wireframes or prototypes to catch problems early
- After launch: validate that real users can complete core tasks
- After a redesign: confirm improvements didn't introduce new issues

### Task Scenario Writing Rules
Tasks must be realistic, neutral, and specific — never leading.

**Good task:** "You've just moved into a new house and need a plumber. Using this website, find out how to contact them and what it would cost."

**Bad task:** "Click the 'Get a Quote' button." (too directive — tells them where to go)
**Bad task:** "Try to find pricing information." (too vague — no context or motivation)

**Task structure:**
```
Scenario: [Real-life context that motivates the task]
Task: [What to accomplish — without naming the UI element]
Success criteria: [What "done" looks like]
```

### Task Bank by Project Type

**Marketing / small business site:**
1. "You're looking for a [service] in your area. Using this site, figure out if this business can help you and what your next step would be."
2. "You want to see examples of their past work. Find where that information lives."
3. "You've decided you want to get in touch. Find the best way to do that."

**SaaS dashboard:**
1. "You've just logged in. Find [key metric] and tell me what it means."
2. "You want to add a new [item/user/record]. Do that now."
3. "Something looks wrong with [data]. Figure out what happened and where you'd go to fix it."

**E-commerce:**
1. "You're looking for [product type] under $[price]. Find one you'd consider buying."
2. "You've found something you like. Add it to your cart and get to the checkout."
3. "You changed your mind about one item. Remove it from your cart."

**Landing page:**
1. "You've seen an ad for this product. Land on this page and tell me: would you sign up? Why or why not?"
2. "Find out what the product actually does and who it's for."

### Moderation Guide

**Setup script:**
```
"Thank you for helping us today. I want to be clear — we're testing the website,
not you. There are no wrong answers. As you go through the tasks, please think
out loud — tell me what you're looking at, what you're thinking, and what
you're trying to do. I may not answer your questions during the tasks, but
I'll answer everything at the end. Ready to start?"
```

**Neutral prompts during testing:**
- "What are you thinking right now?"
- "What would you do next?"
- "What did you expect to happen there?"
- "How does that compare to what you expected?"

**What NOT to say:**
- "You're doing great" (reassurance biases behavior)
- "Try clicking over here" (leading)
- "That's actually where most people struggle" (priming)

**Post-task questions:**
1. "How easy or difficult was that on a scale of 1–5?"
2. "What, if anything, was confusing?"
3. "What would you have done if this weren't a test?"

**Post-session questions:**
1. "What's your overall impression of the site?"
2. "What was the most confusing part?"
3. "What worked well?"
4. "If you could change one thing, what would it be?"
5. "Would you use or contact this business? Why or why not?"

### Observation Note-Taking Template

```markdown
## Usability Test Notes — [Participant ID] — [Date]

### Task 1: [Task name]
- Expected path:
- Actual path:
- Time to complete:
- Success: [ ] Yes  [ ] Partial  [ ] No
- Obstacles observed:
- Direct quotes:
- Severity: High / Medium / Low
```

### Synthesizing Usability Findings

After 5+ sessions, organize findings into:

```markdown
## Usability Findings Summary

### Critical Issues (fix before launch)
- [Issue] — observed in [X/Y] sessions — [design recommendation]

### Moderate Issues (fix in next iteration)
- [Issue] — observed in [X/Y] sessions — [design recommendation]

### Minor Issues (consider for future)
- [Issue] — [design recommendation]

### What Worked Well
- [Positive observation] — [reinforce this in the design]

### Top 3 Priorities
1.
2.
3.
```

---

## 2. Heuristic and Expert Reviews

Use heuristic reviews when user testing isn't possible or as a first pass before testing. Claude can run a structured heuristic audit on any existing page, wireframe, or prototype description.

### The 10 Nielsen Heuristics — Applied to Web

| # | Heuristic | Web application |
|---|---|---|
| 1 | Visibility of system status | Loading states, form validation, progress indicators |
| 2 | Match between system and real world | Language users recognize, familiar icons, logical flow |
| 3 | User control and freedom | Easy undo, clear exit, back button works |
| 4 | Consistency and standards | Same component = same behavior across all pages |
| 5 | Error prevention | Inline validation, confirm before destructive actions |
| 6 | Recognition over recall | Visible nav, clear labels, no hidden states |
| 7 | Flexibility and efficiency | Keyboard shortcuts, saved preferences, quick paths |
| 8 | Aesthetic and minimalist design | Only necessary content, clear hierarchy |
| 9 | Help users recognize, diagnose, recover from errors | Specific error messages, recovery paths |
| 10 | Help and documentation | In-context help, tooltips, clear instructions |

### Heuristic Audit Output Format

```markdown
## Heuristic Audit — [Page / Component / Site Name]
**Date:** [date]
**Auditor:** Claude (AI expert review — not a substitute for user testing)

### H1 — Visibility of System Status
**Finding:** [What's missing or working]
**Severity:** High / Medium / Low / Pass
**Recommendation:** [Specific fix]

### H2 — Match Between System and Real World
...

[Repeat for all 10 heuristics]

---

### Summary

| Heuristic | Severity |
|---|---|
| H1 Visibility | High |
| H2 Real world match | Pass |
...

### Top 5 Issues to Fix
1. [Issue] — [Heuristic] — [Recommendation]
2.
3.
4.
5.

### Accessibility Quick Check
- [ ] Color contrast passes 4.5:1 for normal text
- [ ] All interactive elements have visible focus states
- [ ] Images have alt text
- [ ] Form fields have associated labels
- [ ] Keyboard navigation works for core flows
```

### Severity Rating Guide

| Severity | Definition | Action |
|---|---|---|
| **High** | Blocks task completion or causes significant confusion | Fix before launch |
| **Medium** | Causes friction or frustration but task is completable | Fix in next iteration |
| **Low** | Minor polish issue, low impact | Consider for future |
| **Pass** | No issue found | No action needed |

---

## 3. Analytics Interpretation

Claude cannot access analytics directly, but can help interpret data the user pastes in and turn observations into design hypotheses.

### Analytics Review Checklist

When the user shares analytics data, check for and interpret these signals:

**Traffic and acquisition:**
- [ ] Top traffic sources — does the design serve these audiences? (organic vs paid vs referral behave differently)
- [ ] Device split — what % mobile vs desktop? Does the design prioritize accordingly?
- [ ] Geographic concentration — local vs national? (affects trust signals, language, imagery)

**Engagement:**
- [ ] Bounce rate by page — high bounce on landing pages signals value prop or load speed issues
- [ ] Time on page — very low = users didn't find what they wanted; very high = confused or deeply engaged (need context)
- [ ] Scroll depth — are users reaching the CTA? Are they stopping before key content?
- [ ] Exit pages — where are users leaving? Is it expected (thank you page) or a problem (pricing page)?

**Conversion:**
- [ ] Conversion rate by traffic source — which sources convert best? Design for that audience first
- [ ] Form abandonment — high abandonment = form is too long, confusing, or asks for too much
- [ ] CTA click rate — low rate = CTA is weak, buried, or untrusted

**Site search:**
- [ ] What are users searching for? If they search for something visible in the nav, that nav label is failing
- [ ] Zero-result searches = content gap

**Performance:**
- [ ] Core Web Vitals — LCP, FID/INP, CLS scores and their impact on user experience
- [ ] Page load time by device — slow mobile load is a primary conversion killer

### Analytics → Design Hypotheses Template

```markdown
## Analytics Interpretation — [Project Name]

### Data Provided
[Summary of what the user shared]

### Key Observations
1. [Observation — e.g. "70% of traffic is mobile but mobile conversion is 3x lower than desktop"]
2. [Observation]
3. [Observation]

### Hypotheses
| Observation | Hypothesis | Recommended test or design change |
|---|---|---|
| [e.g. High bounce on pricing page] | [Users can't find pricing or it's unclear] | [Make pricing visible without scroll, add comparison table] |

### Priority Design Changes
Based on the data, address these in order:
1. [Highest impact change]
2.
3.
```

---

## 4. Heatmap and Session Recording Analysis

Claude can provide a rubric for interpreting heatmaps and session recordings that the user describes or summarizes.

### Heatmap Interpretation Rubric

**Click maps:**
| Pattern | What it means | Design response |
|---|---|---|
| Clicks on non-clickable elements | Users expect that element to be a link | Make it clickable or redesign to reduce confusion |
| Ignored primary CTA | CTA is not visually prominent enough | Increase size, contrast, or reposition above fold |
| Rage clicks (repeated fast clicks) | Element appears broken or unresponsive | Add loading state or fix interaction |
| High clicks on secondary elements | Users prioritize differently than assumed | Elevate that element in the hierarchy |

**Scroll maps:**
| Pattern | What it means | Design response |
|---|---|---|
| Most users stop before key content | Content above is not compelling enough to continue | Restructure — move most important content higher |
| Sharp drop-off at a specific section | That section is repelling users | Simplify, shorten, or remove |
| High engagement deep in page | Users who scroll far are qualified — reward them | Add a secondary CTA at the bottom |

**Move maps (mouse tracking):**
| Pattern | What it means | Design response |
|---|---|---|
| Users scan the F-pattern | Standard reading behavior — support with left-aligned hierarchy | Ensure H2s and key info align to left |
| Users hover over images heavily | Visual content is attracting attention | Use images strategically near CTAs |

### Session Recording Review Framework

When reviewing recordings, note:
1. **Confusion clicks** — clicking things that aren't interactive
2. **Hesitation** — long pauses before acting (signals uncertainty)
3. **Backtracking** — going back repeatedly (signals IA problem)
4. **Rage clicks** — rapid repeated clicks (signals broken interaction)
5. **Ignored elements** — key content or CTAs that users scroll past
6. **Unexpected paths** — routes through the site you didn't anticipate

For each pattern, output:
```
Pattern: [What you observed]
Frequency: [How often — X out of Y sessions]
Likely cause: [IA / visual hierarchy / copy / interaction / performance]
Design recommendation: [Specific change]
```

---

## 5. A/B Testing and Experimentation

Claude can help plan A/B tests, define hypotheses and success metrics, and interpret results the user pastes in.

### When to A/B Test
A/B testing is worth the effort when:
- You have enough traffic to reach statistical significance (generally 1,000+ conversions per variant)
- You have a specific hypothesis grounded in data or user research
- The change is isolated enough to attribute results clearly

Do not A/B test when:
- Traffic is too low (results will be inconclusive)
- The change is too broad (can't isolate what caused the difference)
- You're still in early design exploration (use usability testing instead)

### A/B Test Plan Template

```markdown
## A/B Test Plan — [Test Name]

### Hypothesis
"By changing [element] from [current state] to [proposed state],
we expect [metric] to increase/decrease by [amount],
because [reason grounded in research or data]."

### Variants
- **Control (A):** [Current design — describe]
- **Variant (B):** [Proposed change — describe]

### Primary Metric
[The one number that determines success — e.g. form submission rate]

### Secondary Metrics
[Supporting metrics to watch — e.g. time on page, scroll depth]

### Sample Size Needed
[Calculate using a significance calculator — aim for 95% confidence]

### Test Duration
[Minimum 2 weeks to account for day-of-week variation]

### Success Threshold
[e.g. "Variant B wins if it achieves >10% lift in form submissions at 95% confidence"]
```

### Common A/B Test Ideas by Element

| Element | What to test |
|---|---|
| Hero headline | Value-prop focus vs pain-point focus |
| CTA label | Verb-outcome ("Get a free quote") vs urgency ("Get a quote today") |
| CTA position | Above fold vs sticky vs both |
| Form length | Full form vs minimal form (name + email only) |
| Social proof | Testimonials vs stats vs trust badges |
| Hero layout | Text-left/image-right vs full-width text |
| Pricing display | Show price vs "request a quote" |

### Interpreting A/B Test Results

When the user shares test results:
```markdown
## A/B Test Results — [Test Name]

### Results
- Control: [metric] = [value]
- Variant: [metric] = [value]
- Lift: [%]
- Statistical significance: [%]

### Interpretation
[Win / Loss / Inconclusive] — and why

### Decision
[ ] Ship variant B
[ ] Return to control
[ ] Iterate and retest — [what to change]

### What This Tells Us
[Insight about user behavior that goes beyond this specific test]
```

---

## 6. Synthesis Artifacts

Synthesis is where research becomes design direction. These are the artifacts Claude produces to bridge findings and decisions.

### Insight Summary

After any research phase (real or assumption-based), produce a tight insight summary before the research-to-design bridge:

```markdown
## Insight Summary — [Project Name]

### Research conducted / assumptions generated:
[Brief description of methods or assumption basis]

### Raw themes (before prioritization):
- [Theme 1]
- [Theme 2]
...

### Top 5 Insights (prioritized)
1. **[Insight headline]** — [1–2 sentences of supporting evidence or reasoning]
2.
3.
4.
5.

### What surprised us (or what contradicts assumptions):
- [Unexpected finding]
```

### Problem Statements and HMW Questions

Convert insights into actionable design directions:

**Problem statement format:**
"[User] needs a way to [accomplish goal] because [insight about current situation]."

**How Might We (HMW) format:**
"How might we [help user accomplish goal] without [constraint or trade-off]?"

**Example:**
```
Insight: Homeowners don't trust plumbers they find online because
         they have no way to verify quality before calling.

Problem statement: Local homeowners need a way to quickly assess
                   a plumber's trustworthiness before making contact
                   because they fear being overcharged or underdelivered.

HMW: How might we help users verify quality in under 30 seconds
     without requiring them to read through long testimonials?

Design requirement: Display 3 trust signals above the fold —
                    reviews count, years in business, license/certification badge.
```

### Design Requirements Document

```markdown
## Design Requirements — [Project Name]

### Must Have (launch blockers)
- [Requirement derived from research] — [insight that drove it]
- [e.g. "Pricing visible on homepage without form"] — [users cited hidden pricing as #1 trust barrier]

### Should Have (strong recommendations)
- [Requirement]

### Nice to Have (future consideration)
- [Requirement]

### Constraints
- [Technical, budget, or content constraints that affect design]
```

---

## 7. Post-Launch Research

Research doesn't end at launch. Claude can help the user plan ongoing feedback loops and evaluate design changes after they ship.

### Feedback Collection Strategy

**On-site micro-surveys:**
- Trigger: after a key action (form submit, checkout, 60 seconds on page)
- Length: 1–3 questions maximum
- Question types: single rating + one open-ended
- Example: "Did you find what you were looking for today? [Yes / No / Partially] — What would have made this easier? [open text]"

**NPS survey:**
- When: 7–14 days after first meaningful interaction (not immediately on signup)
- Question: "How likely are you to recommend [business] to a friend or colleague? (0–10)"
- Follow-up: "What's the main reason for your score?"
- Segment responses: Promoters (9–10), Passives (7–8), Detractors (0–6)

**Support ticket tagging:**
- Ask the client to tag support tickets by type (navigation confusion, pricing questions, checkout issues, etc.)
- Review monthly — recurring themes = design opportunities

### Release Impact Review Template

Use this to evaluate a design change after it ships:

```markdown
## Release Review — [Feature / Change Name]
**Ship date:** [date]
**Review date:** [2–4 weeks post-launch]

### What changed:
[Brief description]

### Metrics before vs after:
| Metric | Before | After | Change |
|---|---|---|---|
| [Primary metric] | | | |
| [Secondary metric] | | | |

### Qualitative signals:
- User feedback: [positive / negative themes]
- Support tickets: [increase / decrease / new types]
- Session recordings: [any new patterns]

### Decision:
[ ] Keep — the change is working
[ ] Iterate — working but needs refinement: [what to change]
[ ] Rollback — not working: [reason and next steps]

### What we learned:
[Insight that informs future design decisions]
```

### Ongoing Feedback Widget

Recommend a lightweight always-on feedback mechanism for any site that has ongoing content or features:

- A small "Was this helpful?" or thumbs up/down on key pages
- A "Report a problem" link in the footer
- A simple contact form for feedback (separate from the sales/quote form)

These surface issues between formal research cycles and cost almost nothing to implement.
