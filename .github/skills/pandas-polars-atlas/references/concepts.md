# Pandas to Polars Concepts

## Expression mindset

- pandas habit: mutate columns step by step, often through intermediate frames.
- Polars equivalent: build expressions with `select`, `with_columns`, and `when/then/otherwise`.
- Mental shift: write column logic declaratively so the engine can optimize it.
- Watchouts:
  - `apply` often throws away the performance advantage you came for.
  - Expression contexts matter; the same expression can behave differently in `select` and `group_by`.

## Eager vs lazy execution

- pandas habit: everything executes immediately.
- Polars equivalent: use `LazyFrame` when the query has enough steps for optimization to matter.
- Mental shift: treat the pipeline as a query plan first and a materialized table second.
- Watchouts:
  - Do not call `collect()` too early.
  - A lazy plan is only useful if you keep the work inside the lazy pipeline.

## Column creation and conditional logic

- pandas habit: use `assign`, chained indexing, or `np.where`.
- Polars equivalent: use `with_columns` plus expressions such as `pl.when(...).then(...).otherwise(...)`.
- Mental shift: conditional logic belongs inside expressions, not Python loops.
- Watchouts:
  - Chained assignment habits do not map cleanly.
  - Be explicit about casting when branch outputs differ.

## Grouping and aggregation

- pandas habit: `groupby` followed by a mixture of named aggregations and post-processing.
- Polars equivalent: `group_by(...).agg(...)` with named expressions.
- Mental shift: aggregations are easier to read when every output column is declared deliberately.
- Watchouts:
  - Ordering after aggregation is a separate operation.
  - Window functions can replace some awkward groupby-plus-merge patterns.

## Joins and reshaping

- pandas habit: use `merge` everywhere and trust object dtype to smooth rough edges.
- Polars equivalent: use `join`, `concat`, `pivot`, and explicit key typing.
- Mental shift: typed joins make mistakes more visible earlier.
- Watchouts:
  - Join keys with mismatched types should be fixed, not hand-waved.
  - Use lazy joins when the surrounding pipeline is already lazy.
