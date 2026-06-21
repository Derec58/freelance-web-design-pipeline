# Contributing

Thanks for your interest. This is primarily a personal system for running a solo
freelance web design business, but improvements that keep it sharp and well-scoped
are welcome.

## Ground rules

- **Never commit real client data.** No real `project.md` files, names, emails, or pricing.
  Use placeholders. See `.gitignore`.
- **Stay in lane.** Each skill owns one pipeline stage and declares a "when NOT to use"
  boundary. New material should go in the skill that owns it — don't recombine the
  pipeline back into a monolith.
- **Scope to a solo, local small-business context.** Enterprise-weight machinery
  (full MEDDIC, bulk-outbound automation, heavy build pipelines) is intentionally
  out of scope.
- **Adapt, don't paste.** If you're porting an idea from another skill or repo, rewrite
  it for this use case and credit the source in the PR.

## How to contribute

1. Open an issue describing the change (a gap, a fix, a tighter trigger, a new reference).
2. Keep PRs focused — one stage or one reference at a time.
3. For skills, follow the existing structure: a `SKILL.md` with clear metadata and a
   `references/` directory for deep, on-demand detail (progressive disclosure).
4. If you change a skill's name or its handoff, update every cross-reference and the
   `project.md` template so the pipeline stays internally consistent.

## Good first contributions

- Tighten a skill `description` for more reliable triggering.
- Add a well-scoped reference doc to an existing stage.
- Add test prompts toward the evaluation layer (see the roadmap).
