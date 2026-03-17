# Worked example: sales summary pipeline

This example translates a small pandas reporting flow into a Polars pipeline that keeps the work columnar and optimization-friendly.

## Pandas

```python
summary = (
    df[df["status"] == "paid"]
    .assign(avg_ticket=lambda x: x["revenue"] / x["orders"])
    .groupby("region", as_index=False)
    .agg(total_revenue=("revenue", "sum"), avg_ticket=("avg_ticket", "mean"))
)
```

## Polars

```python
summary = (
    df.lazy()
    .filter(pl.col("status") == "paid")
    .with_columns((pl.col("revenue") / pl.col("orders")).alias("avg_ticket"))
    .group_by("region")
    .agg(
        pl.col("revenue").sum().alias("total_revenue"),
        pl.col("avg_ticket").mean().alias("avg_ticket"),
    )
    .collect()
)
```

## What to notice

- The derived column stays inside an expression context.
- Aggregation names live next to the expressions that create them.
- Lazy execution leaves room for optimizer improvements.
