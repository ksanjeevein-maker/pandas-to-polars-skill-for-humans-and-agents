# Pandas to Polars Atlas Codex and Agent Guide

Use this repository when a task involves:

- rewriting pandas notebooks into faster Polars pipelines
- teaching teams when to choose eager vs lazy Polars
- mapping `assign`, `groupby`, `merge`, and window logic into Polars expressions
- reviewing pull requests where pandas muscle memory is hurting Polars performance

## Preferred workflow

1. Identify the source habit, framework concept, or failure mode first.
2. Translate the mental model before jumping to code.
3. Use the local skill references instead of inventing mappings from memory.
4. Prefer native target-platform patterns over transliteration.
5. Add official links when the user wants citations or deeper study.

## Primary local references

- Skill entrypoint: `.github/skills/pandas-polars-atlas/SKILL.md`
- Antigravity-style skill entrypoint: `.agent/skills/pandas-polars-atlas/SKILL.md`
- Concept mappings: `.github/skills/pandas-polars-atlas/references/concepts.md`
- Rewrite patterns: `.github/skills/pandas-polars-atlas/references/patterns.md`
- Official links: `.github/skills/pandas-polars-atlas/references/official-links.md`
- Human reference pack: `official-references.md`

## Output shape

- Start with the target-side equivalent in one sentence.
- Explain the mental shift in plain language.
- Show a concise mapping, pattern, or checklist.
- Call out 1-3 practical watchouts.
- Add official links only when useful.

## Guardrails

- Prefer expression APIs over Python callbacks.
- Reach for lazy execution when the pipeline has multiple filters, joins, or aggregations.
- Avoid `apply` unless the transform cannot be expressed with Polars native expressions.
- Treat schema and null behavior as explicit design choices, not afterthoughts.

## Source preference

1. Official docs
2. Official organization repos
3. Local reference files in this repository
