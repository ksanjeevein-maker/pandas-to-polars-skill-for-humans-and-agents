# Pandas to Polars Skill for Humans and Agents

A migration pack for analysts and engineers moving from pandas to Polars.

The big win is not just speed. It is learning to think in expressions, lazy plans, and schema-aware transforms instead of row-wise Python.

## What makes this repo more useful now

- A stronger learning path for self-study and onboarding
- A worked example that shows the migration or debugging move end to end
- A mental-model diagram for fast orientation
- A review checklist for code review or design review
- Portable agent files for Codex, Copilot, Cursor, and Antigravity

## Learning path

- Start with Polars expressions and contexts before learning every API surface.
- Move into lazy execution and understand what `collect()` does to optimization opportunities.
- Practice group-by, joins, window functions, and typed null handling on realistic analytics flows.
- Use SQL interface and interoperability only after the expression model feels natural.

## High-signal traps

- Rebuilding pandas-style `apply` logic instead of using expressions.
- Calling `collect()` too early and throwing away lazy optimization.
- Ignoring schema mismatches on joins and patching around them later.
- Treating Polars as a drop-in pandas clone instead of a different execution model.

## Read this next

- Main portable guide: `AGENTS.md`
- Decision guide: `docs/decision-guide.md`
- Worked example: `examples/worked-example.md`
- Mental-model diagram: `docs/mental-model-map.md`
- Review checklist: `docs/review-checklist.md`
- Official references: `official-references.md`

## Agent formats

- Codex and generic portable guide: `AGENTS.md`
- Copilot repo instructions: `.github/copilot-instructions.md`
- Copilot skill: `.github/skills/pandas-polars-atlas/`
- Cursor rule: `.cursor/rules/pandas-polars-atlas.mdc`
- Antigravity-style rule: `.agent/rules/pandas-polars-atlas.md`
- Antigravity-style skill: `.agent/skills/pandas-polars-atlas/`
