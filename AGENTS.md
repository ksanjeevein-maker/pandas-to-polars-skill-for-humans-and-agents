# Pandas to Polars Skill for Humans and Agents Codex and Agent Guide

Use this repository when you need a higher-signal explanation, migration pattern, or review aid for this topic.

## Preferred workflow

1. Read `docs/decision-guide.md` when the user needs a migration path, tradeoff call, or phased plan.
2. Read `docs/mental-model-map.md` when the user needs the big picture first.
3. Read `examples/worked-example.md` when the user would benefit from an end-to-end example.
4. Read `docs/review-checklist.md` when reviewing a migration, implementation, or design.
5. Read `official-references.md` when the user wants citations or deeper study.
6. Use the repo-local skill folders when the agent environment supports them.

## Primary local references

- Decision guide: `docs/decision-guide.md`
- Worked example: `examples/worked-example.md`
- Mental-model diagram: `docs/mental-model-map.md`
- Review checklist: `docs/review-checklist.md`
- Official reference pack: `official-references.md`
- Copilot skill entrypoint: `.github/skills/pandas-polars-atlas/SKILL.md`
- Antigravity skill entrypoint: `.agent/skills/pandas-polars-atlas/SKILL.md`

## Output shape

- Start with the target-side or corrected approach in one sentence.
- Explain the mental shift in plain language.
- Use the worked example or checklist when it sharpens the answer.
- Call out the biggest traps explicitly.
- Add official links only when useful.

## Guardrails

- Rebuilding pandas-style `apply` logic instead of using expressions.
- Calling `collect()` too early and throwing away lazy optimization.
- Ignoring schema mismatches on joins and patching around them later.
- Treating Polars as a drop-in pandas clone instead of a different execution model.
