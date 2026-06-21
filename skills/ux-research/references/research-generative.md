# UX Research — Generative Reference

This file covers all early-stage and generative research methods: discovery, proto-personas, jobs-to-be-done, survey design, IA research, card sorting, tree testing, concept testing, and research planning. Read this file during Step 1 (Discover) of the Double Diamond.

For evaluative research (usability testing, heuristic audits, analytics, synthesis, post-launch), read `references/research-evaluative.md`.

---

## Table of Contents
1. [Research Phase — How to Open Every Project](#1-research-phase--how-to-open-every-project)
2. [Research Plan Template](#2-research-plan-template)
3. [Discovery Research](#3-discovery-research)
4. [Proto-Personas](#4-proto-personas)
5. [Jobs-to-Be-Done (JTBD)](#5-jobs-to-be-done-jtbd)
6. [Survey Design](#6-survey-design)
7. [IA and Navigation Research](#7-ia-and-navigation-research)
8. [Concept Testing](#8-concept-testing)
9. [Research-to-Design Bridge](#9-research-to-design-bridge)

---

## 1. Research Phase — How to Open Every Project

Always proactively suggest a research phase before designing — even for simple small business sites. The research phase has three possible modes depending on what exists:

**Mode A — No research exists**
Generate structured assumptions, build proto-personas, write JTBD statements, and propose a minimum viable research plan. Label everything clearly as assumptions.

**Mode B — Some research exists**
the user may provide raw notes, a description of a discovery call, or an uploaded file. Synthesize whatever exists into structured findings before proceeding. Ask follow-up questions to fill gaps.

**Mode C — Research has been done**
Interpret and synthesize the existing research into insights and design requirements. Do not redo work that's already been done.

**Before starting, check `project.md` first.** If the ONBOARDING section exists, you already have the questionnaire answers, discovery call notes, project type, primary conversion goal, timeline, and client audience description. Don't ask the user to re-explain any of this.

Ask only for what's not already in `project.md`:
- "Do you have any analytics, reviews, or user feedback I can work from — anything beyond the questionnaire?"
- "Do you want the standard report structure — Goals → Personas → Findings → Recommendations — or something custom?"

If the ONBOARDING section is missing, also ask: "What research has already been done, and does the client have time or budget for additional research?"

**Standard report structure (default):**
```
1. Research Goals
2. Methods Used
3. User Personas
4. Jobs-to-Be-Done
5. Key Findings
6. Design Requirements
7. Recommendations
8. Open Questions
```

Always output research as a clean markdown doc. Label all assumptions clearly — never present generated assumptions as if they are confirmed user research.

---

## 2. Research Plan Template

Use this one-pager at the start of any project where research will be conducted or generated. Output as part of the research markdown doc.

```markdown
# Research Plan — [Project Name]

## Objectives
What decisions will this research inform?
- [Decision 1]
- [Decision 2]

## Research Questions
What do we need to learn?
- [Question 1]
- [Question 2]

## Methods
| Method | Purpose | Who | When |
|---|---|---|---|
| [e.g. User interviews] | [e.g. Understand current pain points] | [e.g. 3–5 current customers] | [e.g. Week 1] |

## What We Already Know
- [Existing data, analytics, client knowledge]

## Assumptions We're Testing
- [Assumption 1]
- [Assumption 2]

## Success Criteria
How will we know the research answered our questions?
- [e.g. Clear picture of top 3 user goals]

## Constraints
- Timeline: [x weeks]
- Budget: [x hours / $x]
- Access to users: [yes/no/limited]
```

---

## 3. Discovery Research

### Interview Plans and Scripts

When writing discussion guides for user interviews, always include:

**Screener questions** (to confirm the right participant):
- Role/context relevant to the product
- Frequency of relevant behavior
- Familiarity with alternatives/competitors

**Interview structure (60-minute format):**
```
0–5 min    — Warm-up: introduce yourself, explain recording/notes, make them comfortable
5–15 min   — Background: their role, context, how they currently handle the problem
15–35 min  — Core exploration: goals, behaviors, pains, current workarounds
35–50 min  — Reaction to concepts (if applicable): show wireframe/prototype, ask open questions
50–60 min  — Wrap-up: anything else, who else should we talk to
```

**Question writing rules:**
- Turn business goals into behavioral questions: "How do you currently find a plumber?" not "Would you use our booking feature?"
- Ask about past behavior, not hypothetical future behavior
- Use "tell me about a time when..." to get concrete stories
- Never ask leading questions: "Don't you find it frustrating when..." is invalid
- Follow-up prompts: "Can you tell me more about that?" / "What happened next?" / "Why did you do it that way?"

**Question bank by topic:**

*Goals and motivations:*
- "What are you trying to accomplish when you [relevant task]?"
- "What does success look like for you?"
- "What's most important to you when choosing [product/service]?"

*Current behavior and workarounds:*
- "Walk me through how you currently handle [problem]."
- "What tools or services do you use today?"
- "What do you like about what you're using now? What frustrates you?"

*Pain points and objections:*
- "What's the hardest part of [relevant process]?"
- "What would make you not use a service like this?"
- "What would you need to see before you trusted [type of business]?"

*Decision making:*
- "How do you decide between options when [relevant decision]?"
- "Who else is involved in making this decision?"
- "What would make you choose one provider over another?"

---

## 4. Proto-Personas

When no real user research exists, generate proto-personas based on client-provided information and reasonable assumptions. Always label them as proto-personas (assumption-based), not validated personas.

### Proto-Persona Template

```markdown
## Proto-Persona: [Name]
*⚠️ This is an assumption-based proto-persona, not a validated research persona.*

**Role / Context:** [Who they are and what they do]
**Age range:** [approximate]
**Technical comfort:** [Low / Medium / High]
**Device primary:** [Mobile / Desktop / Both]

### Goals
- [Primary goal related to this product]
- [Secondary goal]
- [Tertiary goal]

### Frustrations
- [Main pain point]
- [Secondary frustration]

### Key Questions They Have
- [Question they'd ask before trusting/buying]
- [Question about the process]

### What Builds Trust for Them
- [e.g. Reviews from people like them]
- [e.g. Clear pricing upfront]
- [e.g. Local presence]

### Typical Journey
[New visitor] → [Understands what's offered] → [Checks proof/trust signals] → [Contacts or books]

### Design Implications
- [Specific UI/UX consequence of this persona's needs]
- [e.g. "Needs pricing visible early — don't hide it behind a form"]
```

### Number of Personas
- Simple small business sites: 1–2 personas
- Marketing sites: 2–3 personas
- SaaS / web apps: 2–4 personas (include different user roles if applicable)
- E-commerce: 2–3 personas

### Persona Anti-Patterns to Avoid
- Do not give personas fake demographic details that don't affect design decisions (Myers-Briggs type, favorite movie, etc.)
- Do not make personas so broad they describe everyone ("anyone who uses the internet")
- Do not treat proto-personas as confirmed — always flag that they need validation

### Anti-Personas — Who the Site Is NOT For

Not to be confused with the anti-patterns above (those are persona-writing mistakes). An **anti-persona** is a deliberate decision about who you are *not* designing for. Naming them keeps a small-business site focused and stops it from trying to please everyone — which is the fastest route to a vague, low-converting site and to scope creep mid-project.

For most local-business projects, one or two anti-personas is plenty. Keep them short.

```markdown
## Anti-Persona: [Short label]
*Who this site is intentionally NOT optimized for.*

- **Who:** [e.g. Bargain-hunters collecting five quotes to find the absolute cheapest]
- **Why we're not designing for them:** [e.g. The client wins on trust and quality of work, not price — chasing this group would mean leading with discounts and cheapening the brand]
- **What this means for the design:** [e.g. Don't lead with price or "cheapest in town" — lead with proof, reviews, and quality of work]
```

**Common anti-personas for local-business sites:**
- The price-only shopper — when the client competes on quality and trust, not cost
- The DIYer who will never hire out — don't spend hero space trying to convert them
- Out-of-area visitors — when the business only serves a specific radius
- Wrong-service seekers — someone after a service the client doesn't actually offer

Each anti-persona should produce at least one "what NOT to do" that protects the focus of the site. Feed those into the design requirements alongside the positive personas.

---

## 5. Jobs-to-Be-Done (JTBD)

JTBD statements translate user goals into design drivers. They're more useful than personas alone because they focus on what the user is trying to accomplish, not who they are.

### JTBD Statement Format

```
When [situation/trigger],
I want to [motivation/goal],
So I can [expected outcome].
```

**Example — local plumber site:**
```
When my kitchen sink starts leaking on a weekend,
I want to quickly find a reliable local plumber with clear pricing,
So I can get it fixed without taking time off work or worrying about getting overcharged.
```

### Writing Good JTBD Statements

- The "when" should be a specific, real-life trigger — not a vague state
- The "I want to" should be a concrete action, not a feeling
- The "so I can" is the real outcome they care about — dig past the surface answer
- Generate 3–5 JTBD statements per project, covering the main user types

### JTBD → Design Requirements

For each JTBD statement, immediately derive 1–2 design requirements:

```
JTBD: When I land on a plumber's site, I want to see pricing upfront so I can
      decide quickly if they're in my budget.

Design requirement: Pricing or price range must be visible on the homepage
                   without requiring a form submission or phone call.
```

---

## 6. Survey Design

Use surveys to validate assumptions about value props, pricing clarity, content priorities, and trust signals. Claude can draft short, focused surveys — not multi-page market research instruments.

### Survey Design Rules
- Maximum 5–8 questions for unsolicited surveys (e.g. on-site popup)
- Maximum 10–15 questions for opt-in surveys (e.g. email to existing customers)
- Mix question types: don't use all Likert scales or all open-ended
- No leading questions — neutral wording only
- Always include one open-ended question for unexpected insights
- Test the survey yourself before sending — time it, catch confusing wording

### Question Type Guide

| Type | Best for | Example |
|---|---|---|
| Multiple choice (single) | Categorical data, behavior | "How did you find us?" |
| Multiple choice (multi-select) | What applies, all that apply | "Which of these matter most when choosing a contractor?" |
| Likert scale (1–5 or 1–7) | Attitude, satisfaction, agreement | "How easy was it to find what you were looking for?" |
| Ranking | Priority order | "Rank these in order of importance to you" |
| Open-ended | Unexpected insights, verbatim language | "What almost stopped you from contacting us?" |
| NPS (0–10) | Overall satisfaction, loyalty signal | "How likely are you to recommend us?" |

### Survey Template — New Visitor Validation

```
1. What best describes why you visited this site today?
   [ ] I'm looking for [service] for the first time
   [ ] I'm comparing options
   [ ] I've used a service like this before and am looking for a new provider
   [ ] Other: ___

2. Did you find what you were looking for?
   [ ] Yes, easily
   [ ] Yes, but it took some searching
   [ ] Partially
   [ ] No

3. What almost stopped you from [primary action — contacting/booking/buying]?
   [Open text]

4. How would you describe this site to a friend?
   [Open text]

5. What's one thing we could add or change to make this more useful?
   [Open text]
```

---

## 7. IA and Navigation Research

### Card Sorting

Card sorting helps determine how users mentally group content — use it to validate navigation labels and structure before building.

**Open card sort** (user creates their own groups):
- Use when: IA is undefined, you want to discover natural groupings
- Output: common groupings and unexpected associations
- Minimum participants: 15–20 for statistical patterns; even 5–8 gives directional signal

**Closed card sort** (user sorts into predefined categories):
- Use when: you have a proposed IA and want to validate it
- Output: which items are misplaced, which labels are confusing
- Minimum participants: same as open

**Card sort study template:**
```markdown
## Card Sort Study — [Project Name]

### Cards to sort (content items):
[List 20–40 items — page names, features, content types]

### Categories (closed sort only):
[List proposed nav labels]

### Task instruction for participants:
"Please sort these cards into groups that make sense to you.
You can create as many groups as you like and name them whatever feels natural."

### What we're looking for:
- Which items do users consistently group together?
- Which labels do users create that differ from ours?
- Which items cause confusion (sorted differently by most people)?

### How to interpret results:
- Items sorted together by 70%+ of participants → strong signal, keep them together
- Items with no clear pattern → may need to be renamed or reconsidered
- User-created label names that differ from yours → consider adopting their language
```

### Tree Testing

Tree testing validates findability — can users find the right page in a stripped-down nav structure?

**Tree test template:**
```markdown
## Tree Test — [Project Name]

### Navigation tree to test:
[Paste the proposed sitemap as a text tree]

### Tasks:
1. "You want to get a quote for [service]. Where would you go?"
2. "You want to see examples of past work. Where would you go?"
3. "You want to find out how much it costs. Where would you go?"

### Success criteria per task:
- Success: user clicks the correct destination on first try
- Partial success: user finds it eventually after backtracking
- Failure: user gives up or lands on the wrong page

### What to fix:
- Tasks with <70% direct success rate → relabel or restructure that branch
- Common wrong-first-clicks → those labels are being mistaken for something else
```

### First-Click Testing

**Script template:**
```
Show participant a screenshot of the homepage (or a specific page).
Ask: "If you wanted to [complete task], where would you click first?"
Record: where they click and how confident they feel (1–5).
```

**5-second test:**
```
Show participant the homepage for 5 seconds, then hide it.
Ask:
1. "What do you remember about what you just saw?"
2. "What does this business do?"
3. "Who is this for?"
4. "What would you do next if this were a real site?"
```

**Interpreting results:**
- If users can't say what the business does after 5 seconds → H1 is failing
- If users click the wrong element first → CTA placement or label needs work
- If users feel uncertain about where to click → visual hierarchy is weak

---

## 8. Concept Testing

Use concept testing to validate early wireframes or layout directions before going high-fidelity.

### Concept Test Script Template

```markdown
## Concept Test — [Project Name]

### What we're testing:
[Brief description of the wireframe/concept being shown]

### Setup:
"I'm going to show you an early draft of a website. Nothing is clickable —
I just want your honest first impressions. There are no right or wrong answers.
You're helping us improve the design, not the other way around."

### Questions:
1. "Just looking at this — what does this business do?"
2. "Who do you think this is for?"
3. "What stands out most to you?"
4. "What's confusing or unclear?"
5. "If this were a real website, what would you do next?"
6. "What would make you more or less likely to contact them?"

### Success signals to look for:
- User correctly identifies what the business does without prompting
- User identifies the primary CTA without being told where to look
- User's "what I'd do next" matches the intended conversion goal

### What to change based on results:
- Business purpose unclear → strengthen H1 and hero subheading
- CTA not noticed → move above fold, increase visual weight
- Confusion about a section → simplify copy or restructure hierarchy
```

---

## 9. Research-to-Design Bridge

After any research phase (real or assumption-based), always produce this bridge before moving to Step 2 (Define). This is the connective tissue between research and design decisions.

### Output Format

```markdown
## Research-to-Design Bridge — [Project Name]

### Top Insights
1. [Most important thing we learned or are assuming]
2. [Second insight]
3. [Third insight]
... (3–7 total)

### Design Requirements
Derived directly from insights above:
1. [Specific, actionable design requirement — e.g. "Pricing must be visible on homepage"]
2. [e.g. "Portfolio/work samples must appear above the fold on mobile"]
3. [e.g. "Primary CTA must be a phone number, not a form"]
... (3–7 total)

### Prioritized Opportunity List
What to tackle first in the design, in order:
1. [Highest impact opportunity]
2. [Second priority]
3. [Third priority]

### Open Questions
What we still don't know and how we might find out:
- [Question] → [Suggested method to answer it]
```

Always ask the user to confirm before proceeding: "These are the design requirements I'm working from. Do you want to add, remove, or re-order anything before I move to wireframes?"
