# Pandas to Polars Skill for Humans and Agents Review Checklist

Use this checklist during code review, design review, or migration planning.

- Does the pipeline use expressions instead of Python callbacks where possible?
- Should the flow stay lazy longer for optimization and projection pushdown?
- Are join keys and output schemas explicit and correct?
- Is null handling deliberate rather than incidental?
- Would a teammate understand the transformation plan from the expression chain alone?
