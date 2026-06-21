# Claude Code — Next Steps Plan

A step-by-step plan for taking this pipeline live, validating it, and leveling it up — all from Claude Code on your machine. Work top to bottom; each phase is self-contained.

---

## Phase 0 — Prerequisites

- **Claude Code** installed and signed in (`claude` in your terminal, or the desktop app).
- **git** installed (`git --version`).
- **GitHub CLI** (`gh`) installed and authed (`gh auth login`) — optional but makes Phase 1 a one-liner.
- This repo extracted somewhere sensible, e.g. `~/dev/freelance-web-design-pipeline`.

> The downloadable bundle already contains an initialized git repo with a clean initial
> commit, so you can skip straight to "add remote + push." A from-scratch path is included
> below in case you'd rather start fresh.

---

## Phase 1 — Get the repo live (create + push)

### Option A — GitHub CLI (fastest)
```bash
cd ~/dev/freelance-web-design-pipeline
gh repo create freelance-web-design-pipeline --public --source=. --remote=origin --push
```
That creates the GitHub repo, wires up `origin`, and pushes in one shot.

### Option B — Manual
1. Create an empty repo on GitHub (no README/license — this repo already has them).
2. Then:
```bash
cd ~/dev/freelance-web-design-pipeline
git remote add origin https://github.com/<your-username>/freelance-web-design-pipeline.git
git branch -M main
git push -u origin main
```

### Option C — Start the git history from scratch (if you didn't use the bundle's `.git`)
```bash
cd ~/dev/freelance-web-design-pipeline
git init -b main
git add .
git commit -m "Initial commit: six-stage freelance web design pipeline (Claude Skills)"
gh repo create freelance-web-design-pipeline --public --source=. --remote=origin --push
```

### Let Claude Code do it
Open Claude Code in the repo folder and paste:
> "Create a public GitHub repo named `freelance-web-design-pipeline` from this directory and push it. The repo already has a README, LICENSE, and an initial commit — just create the remote, set `origin`, and push `main`."

### After pushing — polish the repo page
- Add a **description** and **topics** on GitHub: `claude-skills`, `agent-skills`, `freelance`, `web-design`, `prompt-engineering`.
- Confirm the README renders (the Mermaid diagram and badges should display).
- Optionally enable Issues and add the roadmap items below as issues.

---

## Phase 2 — Install & smoke-test the skills

1. **Install** the skills where Claude Code looks for them:
   ```bash
   cp -r skills/* ~/.claude/skills/
   ```
   (Confirm the current skills path in the Claude docs — it can change.)

2. **Triggering check.** Start fresh sessions and give each a natural prompt; confirm the *right* skill activates and the others stay quiet:
   - "I found a plumber in Manteca with no website — help me reach out." → `client-acquisition`
   - "A prospect agreed to a call, let's prep the discovery + proposal." → `client-onboarding`
   - "I have the questionnaire back — build personas and design requirements." → `ux-research`
   - "Research is done, let's design the site." → `web-design`
   - "Design is approved, build it." → `web-development`
   - "Site's delivered — invoice and close out." → `post-launch`

3. **Boundary check.** Confirm the "when NOT to use" lines hold — e.g. asking `web-design` to write production code should defer to `web-development`.

4. **Full dry run.** Run a fictional client (e.g. "Reyes Landscaping") through all six stages and watch `project.md` accumulate its blocks end-to-end. Fix any handoff that drops context.

---

## Phase 3 — Wire in the canonical `project.md` template

Each skill's Session Start Protocol currently says *"create it using the canonical template"* but doesn't point anywhere. Close that loop:

1. In each `SKILL.md`, update that line to reference **`docs/project-md-template.md`** as the source of truth.
2. Confirm the block each skill appends matches the template exactly (they were generated from the live skills, so they should — but re-check after any edits).

Paste into Claude Code:
> "In every `skills/*/SKILL.md`, update the Session Start Protocol so 'create it using the canonical template' points to `docs/project-md-template.md`. Don't change the block contents — just add the reference."

---

## Phase 4 — Build the evaluation layer (the reliability lever)

This is the highest-value upgrade. Right now there's no way to *measure* whether a skill triggers correctly or produces good output.

1. **Use `skill-creator`.** It can scaffold test prompts and (in Claude Code) optimize a skill's `description` against a held-out set. Install it from `anthropics/skills` and run it against each skill.
2. **Write a small eval set per skill** — a handful of prompts that *should* trigger it, plus near-miss prompts that should *not*. Track trigger accuracy.
3. **Optimize descriptions** with the eval loop (e.g. `run_loop.py`-style description tuning) to reduce both under-triggering and mis-triggering.
4. **Consider `task-observer`** — a community meta-skill that builds and improves your other skills — as an ongoing improvement loop.

Aim: each stage triggers when it should, defers when it shouldn't, and the handoff never drops a field.

---

## Phase 5 — Future enhancements (optional, in priority order)

1. **State-aware kickoff** — let `client-acquisition` detect where a returning lead already is and route to the right stage, instead of always starting at the top.
2. **Deterministic scripts** — small Python helpers where exactness matters: a PDF proposal/report generator, and a persona-from-data script for the rare project with real analytics.
3. **Case-study → AEO loop** — publish case studies as answer-engine-friendly pages (FAQ blocks, schema) so they pull double duty as social proof *and* search visibility.
4. **New stage skills** — only if a real gap keeps recurring (e.g. a live discovery-call note-taker).

---

## Phase 6 — Maintenance & versioning

- Add a `CHANGELOG.md` and tag releases (`v1.0.0`) as you make meaningful changes.
- **Keep SEO/AEO fresh** — answer-engine optimization shifts fast; re-check `seo-basics.md` a couple of times a year.
- Re-run the Phase 2 smoke test after any rename or structural change, and re-verify there are no stale cross-references across skills.
- Retire prototypes deliberately (as was done with `senior-web-designer`) rather than letting dead skills linger and mis-trigger.

---

### Quick reference — the whole flow

```
acquisition → onboarding → research → design → development → post-launch
     ▲                                                            │
     └──────────────── case studies · referrals · rate raises ────┘
```
