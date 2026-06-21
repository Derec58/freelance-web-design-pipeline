---
name: ux-research
description: UX research for web design projects — generating research reports, creating proto-personas and anti-personas, writing jobs-to-be-done statements, running competitive analysis, synthesizing findings into design requirements, and bridging research to design decisions. Use this skill when the user needs to conduct or interpret research before designing, generate a UX report from client questionnaire answers, build personas or anti-personas, analyze competitors, or translate findings into actionable design requirements. Trigger for any request involving research, personas, user goals, competitor analysis, or "what should I design and why." Do NOT use this skill for running the discovery call or sending the client questionnaire — that is client-onboarding. Do NOT use it for wireframes, visual design, or the design system — that is web-design.
---

# UX Research Skill

**Pipeline position: Step 3 of 6**

---

## Session Start Protocol

**Only run this when the user says there is an active project.**

When activated, do the following based on your environment:

**If you are in Claude Code (VS Code terminal):**
Look for `project.md` at `~/Desktop/WebsiteProjects/[client-name]/project.md`. Read it in full. Confirm which prior sections are present (ACQUISITION, ONBOARDING) and summarize what you know — business name, project type, primary conversion goal, timeline, key onboarding notes — so the user can confirm or correct before research begins.

If `project.md` does not exist, create it at the standard path using the canonical template. Prompt the user for missing context and mark unknowns as `[not captured]`.

**If you are in claude.ai chat:**
Ask the user to open `project.md` in VS Code, select all, and paste it here. Once pasted, confirm what you know and proceed. If no file exists yet, ask the user for the key context manually, output a filled-in scaffold, and tell him to save it to:
`~/Desktop/WebsiteProjects/[client-name]/project.md`

In both environments: proceed to Step 3A. Do not ask for information already in project.md.

**When complete (both environments):** After the research-to-design bridge is confirmed by the user (Step 3C), append this block — in Claude Code write it directly; in chat output it and tell the user to paste it in:

```markdown
### RESEARCH
- Mode: [A — assumption-based / B — some research / C — research done]
- Personas: [names + one-line summaries]
- Anti-personas: [who the site is explicitly NOT for]
- JTBD statements: [list]
- Competitive analysis: [done / skipped]
- Confirmed design requirements: [list 3–7]
- Key insight for design: [one sentence]
```

---

This skill picks up after `client-onboarding` is complete — the agreement is signed, the deposit is paid, and the questionnaire is filled out. Its job is to turn what the client told you into structured research that drives every design decision in `web-design`.

No guessing. No designing from aesthetics alone. Research first, design second.

**What this skill receives from `client-onboarding`:**
- Completed client questionnaire (full or fast-track)
- Discovery call notes
- Signed agreement and paid deposit confirmed
- Project type classification
- Primary conversion goal
- Client's description of their audience and goals in their own words
- Any existing brand assets or content
- Timeline and hard deadlines

**What this skill hands off to `web-design`:**
- UX research report (markdown doc)
- Research-to-design bridge (insights + design requirements + opportunity list)
- Proto-personas (1–3 depending on project type)
- JTBD statements with derived design requirements
- Competitive analysis summary (if conducted)
- Confirmed design requirements — approved by the user before design begins
- Project type classification
- Primary conversion goal
- Any brand assets received from the client (logo, colors, fonts — or "none")
- Timeline

---

## How Research Works in This Pipeline

Claude cannot interview real users. What it can do is:

1. **Synthesize** what the client told you in the questionnaire and discovery call into structured findings
2. **Generate assumptions** where real data doesn't exist — clearly labeled as assumptions, never presented as confirmed research
3. **Structure research plans** for the user to run (interview guides, surveys, usability scripts)
4. **Interpret data** the user provides (analytics, reviews, competitor observations)
5. **Bridge findings to design** — translate everything into specific, actionable design requirements

Always label assumption-based content clearly. Never present generated assumptions as confirmed user research.

---

## Step 3A — Orient and Choose the Research Mode

Before generating anything, do three things in order:

**1. Check what's already known**

If `project.md` exists and has an ONBOARDING section, you already have: the completed questionnaire answers, discovery call notes, project type, primary conversion goal, timeline, and client description of their audience. Do not ask the user to re-explain any of this. State what you know and confirm it's current.

**2. Ask only for what's missing**

Two things are not captured in `project.md` and always need to be asked:

- "Do you have any analytics, reviews, or user feedback I can work from — anything the client shared beyond the questionnaire?" *(external data sources)*
- "Do you want the standard report structure — Goals → Personas → Findings → Recommendations — or something custom for this project?"

If the ONBOARDING section is missing or incomplete, also ask: "What research, if any, has already been done, and does the client have time or budget for any additional research?"

**3. State the research mode**

Choose one and say it explicitly before proceeding:

**Mode A — No prior research exists**
Generate structured assumptions from the questionnaire. Build proto-personas, JTBD statements, and a hypothesis list. Propose a minimum viable research plan the client could run if they want to validate. Label everything as assumption-based.

**Mode B — Some research exists**
the user has provided raw notes, a discovery call description, or an uploaded file. Synthesize whatever exists into structured findings. Ask follow-up questions to fill gaps.

**Mode C — Research has been done**
Interpret and synthesize existing research into insights and design requirements. Do not redo work already done. Extract what's useful and move to the bridge.

---

## Step 3B — Generate the Research Report

Always output as a clean markdown document. Standard structure unless a custom one is requested.

```
# UX Research Report — [Business Name]
Version: Assumption-based / Client-provided / Mixed
Date: [date]
Project type: [classification from client-onboarding]

## 1. Research Goals
## 2. Methods Used (or "Assumption-based proto-research")
## 3. User Personas & Anti-Personas
## 4. Jobs-to-Be-Done
## 5. Key Findings
## 6. Design Requirements
## 7. Recommendations
## 8. Open Questions
```

Read `references/research-generative.md` for full guidance on:
- How to build proto-personas (and anti-personas — who the site is NOT for) from questionnaire answers
- How to write JTBD statements and derive design requirements from them
- How to write interview plans, surveys, and concept test scripts
- How to run card sorting and tree testing studies
- How to structure competitive analysis

Read `references/research-evaluative.md` for full guidance on:
- Usability testing scripts and moderation
- Heuristic audits
- Analytics interpretation frameworks
- Heatmap and session recording analysis
- A/B test planning
- Post-launch research methods

---

## Step 3C — The Research-to-Design Bridge

This is the most important output of this skill. After any research phase, produce this bridge before handing off to `web-design`. Confirm with the user before proceeding.

```markdown
## Research-to-Design Bridge — [Business Name]

### Top Insights
1. [Most important finding or assumption]
2. [Second insight]
3. [Third insight]
... (3–7 total)

### Design Requirements
Derived directly from insights — specific and actionable:
1. [e.g. "Pricing must be visible on the homepage without a form"]
2. [e.g. "Portfolio must appear above the fold on mobile"]
3. [e.g. "Primary CTA must be a phone number, not a contact form"]
... (3–7 total)

### Prioritized Opportunity List
What to tackle first in the design:
1. [Highest impact opportunity]
2. [Second priority]
3. [Third priority]

### Open Questions
What we still don't know:
- [Question] → [Suggested method to answer it]
```

**Always confirm before moving on:**
> "These are the design requirements I'm working from. Do you want to add, remove, or re-order anything before I move to wireframes?"

---

## Step 3D — Competitive Analysis

Run when the client mentions competitors, when understanding the competitive landscape would sharpen the design direction, or when the user asks for it.

**What to analyze (for each competitor):**
- Site URL and business type
- What they do well (layout, trust signals, copy, speed)
- What they do poorly (mobile experience, clarity, CTAs)
- How they position themselves
- What gap exists that the client can own

**Output format:**
```markdown
## Competitive Analysis — [Business Name]

### Competitor 1: [Name]
URL: [url]
What works: [observations]
What doesn't: [observations]
Positioning: [how they describe themselves]

### Competitor 2: [Name]
...

### Key Gaps and Opportunities
- [Gap 1] — [design implication]
- [Gap 2] — [design implication]

### Differentiation Recommendation
[How the client's site should position itself relative to competitors]
```

---

## Pipeline Handoff Checklist

Before handing off to `web-design`, confirm all of the following exist:

- [ ] UX research report generated (markdown doc)
- [ ] Research mode stated (A / B / C)
- [ ] Proto-personas built (1–3 depending on project type)
- [ ] Anti-personas defined (who the site is NOT for)
- [ ] JTBD statements written with derived design requirements
- [ ] Key findings listed (3–7 insights)
- [ ] Design requirements confirmed by the user (3–7 requirements)
- [ ] Prioritized opportunity list produced
- [ ] Competitive analysis done (if relevant)
- [ ] Open questions documented
- [ ] Research-to-design bridge confirmed — [Your Name] approved before design begins

**Pass to `web-design`:**
- The full research report (markdown)
- The confirmed design requirements list
- Proto-personas
- Any brand assets received from the client
- Project type, primary conversion goal, and timeline

---

## Reference Files

| File | Read when... |
|---|---|
| `references/research-generative.md` | Building personas, JTBD, surveys, card sorting, concept testing, IA research |
| `references/research-evaluative.md` | Usability testing, heuristic audits, analytics, heatmaps, A/B testing, post-launch |
