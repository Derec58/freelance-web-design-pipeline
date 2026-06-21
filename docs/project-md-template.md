# `project.md` — Canonical Template

`project.md` is the connective tissue of the pipeline. One file per client lives at
`~/Desktop/WebsiteProjects/[client-name]/project.md` (or wherever you keep client work).
Each skill **reads** the file when it starts and **appends its own block** when it finishes,
so context flows from cold lead all the way through to post-launch without ever being
re-explained.

This is the single source of truth for that file. When a skill says *"create it using the
canonical template,"* this is the template it means. Copy the whole thing into a new
client's `project.md` at kickoff, then let each stage fill in its block.

> **Privacy:** real `project.md` files contain client names, contact details, and pricing.
> Keep them out of this repo and out of version control — see `.gitignore`. This template
> is the only `project.md` that belongs in the repo.

---

```markdown
# Project: [Client / Business Name]
_Started: [date] · Status: [active / delivered / closed]_

### ACQUISITION
- Business name:
- Owner name:
- Contact info:
- Channel: [email / DM / cold call / in-person / referral]
- What got the response: [what you said or sent that worked]
- Context they gave: [anything about their site or needs]
- Qualification / fit: [green / yellow — Need, Budget signal, Authority, Timeline notes]
- Social proof used: [which example you referenced, if any]
- Scheduled call: [date and time]

### ONBOARDING
- Project type: [marketing site / small business / landing page / e-commerce / blog / redesign / SaaS]
- Primary conversion goal: [one sentence — call / form / booking / purchase]
- Deposit paid: [yes — $amount / date]
- Contract signed: [yes / date]
- Whose paper: [my agreement / client's contract — if client's, note anything negotiated]
- Timeline: [start date — target delivery date]
- Hard deadline: [date or none]
- Key notes: [anything unusual about scope, client, or constraints]

### RESEARCH
- Mode: [A — assumption-based / B — some research / C — research done]
- Personas: [names + one-line summaries]
- Anti-personas: [who the site is explicitly NOT for]
- JTBD statements: [list]
- Competitive analysis: [done / skipped]
- Confirmed design requirements: [list 3–7]
- Key insight for design: [one sentence]

### DESIGN
- Visual direction chosen: [name of chosen direction]
- Color tokens: [primary, secondary, accent — OKLCH values]
- Typography: [display font / body font]
- Key layout decisions: [1–3 sentences]
- Wireframes: [done / in Figma at URL / described in chat]
- Design system output: [linked or noted]
- Anti-pattern check: [passed / flagged items]

### DEVELOPMENT
- Stack: [HTML/CSS/JS / Astro / Next.js / etc.]
- Hosting: [Netlify / Vercel / other]
- Repo: [GitHub URL or local]
- Live URL: [URL or "not yet live"]
- Site delivered: [yes / date]
- Delivery method: [ZIP / GitHub / Netlify deploy]
- Post-launch issues: [none / description]
- README: [included / pending]

### BUSINESS
- Final invoice: [sent / paid — $amount / date]
- Maintenance plan: [offered / accepted $X/month / declined]
- Google review: [requested / received]
- Referral ask: [yes / no / referral received from]
- Case study: [written / pending / published at URL]
```

---

## How each stage uses it

| Stage | Skill | Reads | Appends |
|---|---|---|---|
| 1 | `client-acquisition` | — (creates the file) | `ACQUISITION` |
| 2 | `client-onboarding` | `ACQUISITION` | `ONBOARDING` |
| 3 | `ux-research` | `ACQUISITION`, `ONBOARDING` | `RESEARCH` |
| 4 | `web-design` | through `RESEARCH` | `DESIGN` |
| 5 | `web-development` | through `DESIGN` | `DEVELOPMENT` |
| 6 | `post-launch` | through `DEVELOPMENT` | `BUSINESS` |

In **Claude Code**, the active skill writes its block to the file directly. In the
**Claude.ai / desktop app**, paste the file in at the start of a stage and paste the
updated version back out at the end.
