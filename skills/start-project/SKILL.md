---
name: start-project
description: The single entry point for the freelance web design pipeline — use this to start a new client project. Triggers on "start a new project", "new client", "kick off the pipeline", "start the pipeline", "begin a new website project", "new website client", or "/start-project". This skill creates the project.md handoff file from the canonical template, orients the user to the six stages, and routes to the correct stage to begin (normally client-acquisition). Use this FIRST to start a project instead of waiting for an individual stage skill to self-activate.
---

# Start Project — Pipeline Orchestrator

This is the **one command to start the pipeline**. Run it to begin a new client project; it sets up the shared handoff file and launches the right stage. Use it instead of relying on each stage skill to detect an active project on its own.

The pipeline has six stages, each owned by its own skill:

```
1 client-acquisition → 2 client-onboarding → 3 ux-research →
4 web-design → 5 web-development → 6 post-launch
```

They pass context through a single file, `project.md`, that each stage reads and appends to. This skill creates that file and points the user at the right starting stage.

---

## What this skill does

1. Captures the minimum to start (the client / business name).
2. Creates `project.md` from the canonical template.
3. Asks where the user is with this client and routes to the matching stage (state-aware — a brand-new lead starts at stage 1; an already-signed client jumps ahead).
4. Hands off to that stage's skill to begin the real work.

---

## Step 1 — Capture the basics

Ask for just enough to open a project. Don't over-collect — each stage gathers its own detail.

- **Client / business name** (required) — used for the project folder and the file header.
- Anything the user already knows is welcome (business type, how they found the lead), but optional.

## Step 2 — Create `project.md`

Create the handoff file from the **canonical template** at `docs/project-md-template.md` (copy the whole template, set the project name and date in the header).

- **In Claude Code:** create the file directly at `~/Desktop/WebsiteProjects/[client-name]/project.md` (or the user's chosen projects folder). Confirm the path.
- **In the Claude.ai / desktop app:** output the filled-in header + empty blocks and tell the user to save it to that path. They'll paste it in and out as they move between stages.

> If `docs/project-md-template.md` isn't available in the current context, reproduce the six-block structure: `ACQUISITION → ONBOARDING → RESEARCH → DESIGN → DEVELOPMENT → BUSINESS`.

## Step 3 — Where are you with this client? (state-aware routing)

Most projects start at stage 1. But if the user already has a client further along, skip ahead — don't make them walk through stages that are already done. Ask which best fits, then route:

| Situation | Start at | Skill |
|---|---|---|
| Brand-new lead — haven't contacted them yet | Stage 1 | `client-acquisition` |
| They've responded / agreed to a call | Stage 2 | `client-onboarding` |
| Signed + deposit paid — ready to plan | Stage 3 | `ux-research` |
| Research done — ready to design | Stage 4 | `web-design` |
| Design approved — ready to build | Stage 5 | `web-development` |
| Site delivered — closing out & growing | Stage 6 | `post-launch` |

If the user isn't sure, default to **Stage 1 (`client-acquisition`)**.

## Step 4 — Hand off

State which stage is starting and why, then continue into that stage's skill and begin its work. From there, each stage hands off to the next through `project.md` until the project is delivered and closed.

---

## The pipeline at a glance

| # | Stage | Skill | Outcome |
|---|-------|-------|---------|
| 1 | Find work | `client-acquisition` | A qualified lead who agreed to talk |
| 2 | Win work | `client-onboarding` | Signed agreement + deposit |
| 3 | Decide what to build | `ux-research` | Confirmed design requirements |
| 4 | Design it | `web-design` | Approved design + design system |
| 5 | Build & ship it | `web-development` | Live site + clean handoff |
| 6 | Get paid & grow | `post-launch` | Final payment, maintenance, referral, case study |

The loop closes: `post-launch` produces the case studies and referrals that feed the next `client-acquisition`.
