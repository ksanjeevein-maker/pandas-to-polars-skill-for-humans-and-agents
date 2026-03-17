# Pandas to Polars Patterns

## Filter then derive a new column

Pandas:

```python
result = (
    df[df["region"] == "west"]
    .assign(revenue_per_user=lambda x: x["revenue"] / x["users"])
)
```

Polars:

```python
result = (
    df.filter(pl.col("region") == "west")
    .with_columns((pl.col("revenue") / pl.col("users")).alias("revenue_per_user"))
)
```

## Group and aggregate with named outputs

Pandas:

```python
summary = df.groupby("team").agg(
    avg_score=("score", "mean"),
    total_sales=("sales", "sum"),
)
```

Polars:

```python
summary = df.group_by("team").agg(
    pl.col("score").mean().alias("avg_score"),
    pl.col("sales").sum().alias("total_sales"),
)
```

## Conditional bucketing

Pandas:

```python
df["segment"] = np.where(df["spend"] > 1000, "high", "standard")
```

Polars:

```python
df = df.with_columns(
    pl.when(pl.col("spend") > 1000)
    .then(pl.lit("high"))
    .otherwise(pl.lit("standard"))
    .alias("segment")
)
```

## Join two tables

Pandas:

```python
merged = orders.merge(customers, on="customer_id", how="left")
```

Polars:

```python
merged = orders.join(customers, on="customer_id", how="left")
```
