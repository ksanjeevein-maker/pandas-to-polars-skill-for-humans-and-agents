# Pandas to Polars Skill for Humans and Agents Decision Guide

Use this when you need to choose the next move instead of reading every reference front to back.

## When to use this guide

- Use it when the user is blocked by one of these traps: Rebuilding pandas-style `apply` logic instead of using expressions., Calling `collect()` too early and throwing away lazy optimization..
- Use it when you need to decide the order of migration work, not just the target syntax.
- Use it when you need a short review path before shipping or approving code.

## Recommended sequence

### Step 1: Orient

- Focus: Start with Polars expressions and contexts before learning every API surface.
- Exit check: Does the pipeline use expressions instead of Python callbacks where possible?

### Step 2: Translate

- Focus: Move into lazy execution and understand what `collect()` does to optimization opportunities.
- Exit check: Should the flow stay lazy longer for optimization and projection pushdown?

### Step 3: Implement

- Focus: Practice group-by, joins, window functions, and typed null handling on realistic analytics flows.
- Exit check: Are join keys and output schemas explicit and correct?

### Step 4: Harden

- Focus: Use SQL interface and interoperability only after the expression model feels natural.
- Exit check: Is null handling deliberate rather than incidental?

## If the user is stuck, choose this next move

- If they are porting line by line, redirect to the mental model in `docs/mental-model-map.md` and call out: Treating Polars as a drop-in pandas clone instead of a different execution model.
- If they need proof, show `examples/worked-example.md` and explain what changed structurally.
- If they are ready to merge or publish, run the checklist in `docs/review-checklist.md`.

## Escalate when

- The implementation still violates this review check: Would a teammate understand the transformation plan from the expression chain alone?
- The chosen approach depends on preserving a source-side habit that keeps causing trouble: Rebuilding pandas-style `apply` logic instead of using expressions.
