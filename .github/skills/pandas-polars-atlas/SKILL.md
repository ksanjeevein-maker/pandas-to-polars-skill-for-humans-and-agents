---
name: pandas-polars-atlas
description: A markdown-first migration pack for analysts and engineers moving from pandas to Polars. It focuses on expression-oriented thinking, lazy execution, join patterns, aggregation, and performance-sensitive table transforms. Use when an agent needs a concise reference, migration guide, or side-by-side pattern library for this topic.
---

# Pandas to Polars Atlas

Use this skill to answer the practical question, "what is the target-platform way to do the thing I already know?"

## Quick Start

- Read `references/concepts.md` for conceptual mapping and mindset shifts.
- Read `references/patterns.md` for concrete rewrite or debugging patterns.
- Read `references/official-links.md` when official docs or source repos are needed.

## Workflow

1. Identify the source-side habit or failure mode.
2. Translate the mental model before changing code.
3. Prefer native target-platform patterns.
4. Show a small example or checklist instead of a giant transliteration.
5. Call out the main watchouts clearly.

## Output

- Start with the target-side equivalent in one sentence.
- Explain the mental shift in plain language.
- Show a concise mapping, snippet, or checklist.
- Mention 1-3 watchouts.
- Add official links only when useful.

## Guardrails

- Prefer expression APIs over Python callbacks.
- Reach for lazy execution when the pipeline has multiple filters, joins, or aggregations.
- Avoid `apply` unless the transform cannot be expressed with Polars native expressions.
- Treat schema and null behavior as explicit design choices, not afterthoughts.

## Extended references

- Read `references/decision-guide.md` when the user needs a migration path or sequence.
- Read `references/worked-example.md` when a concrete example would help.
- Read `references/review-checklist.md` when reviewing an implementation or plan.
