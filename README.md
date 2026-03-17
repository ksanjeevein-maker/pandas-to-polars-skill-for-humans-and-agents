# Pandas to Polars Skill for Humans and Agents

A markdown-first migration pack for analysts and engineers moving from pandas to Polars. It focuses on expression-oriented thinking, lazy execution, join patterns, aggregation, and performance-sensitive table transforms.

The goal is not to transliterate pandas one-liners. The goal is to help people stop writing row-wise Python in a columnar, expression-driven system.

## Best use

- rewriting pandas notebooks into faster Polars pipelines
- teaching teams when to choose eager vs lazy Polars
- mapping `assign`, `groupby`, `merge`, and window logic into Polars expressions
- reviewing pull requests where pandas muscle memory is hurting Polars performance

## Core topics

- expression-oriented transforms instead of row-wise mutation
- lazy plans, projection pushdown, and query optimization
- grouping, joins, sorting, and window functions
- schema strictness, null handling, and conditional columns
- SQL interface and interoperability patterns

## Questions this pack should answer well

- What is the Polars equivalent of `assign` plus `query`?
- How should I translate a pandas `groupby().agg()` chain?
- When should I use `LazyFrame` instead of `DataFrame`?
- How do I stop writing `apply` for work Polars expressions can vectorize?

## When not to use this pack

- tiny one-off CSV scripts where pandas is already fine
- full Spark-scale distributed pipeline design
- deep Arrow internals or Polars engine implementation details

## Agent formats

- Codex and generic portable guide: `AGENTS.md`
- Copilot repo instructions: `.github/copilot-instructions.md`
- Copilot skill: `.github/skills/pandas-polars-atlas/`
- Cursor rule: `.cursor/rules/pandas-polars-atlas.mdc`
- Antigravity-style rule: `.agent/rules/pandas-polars-atlas.md`
- Antigravity-style skill: `.agent/skills/pandas-polars-atlas/`

## Source policy

- Prefer official framework and library docs first.
- Prefer official GitHub org repos second.
- Re-check official docs when framework behavior may have changed.
