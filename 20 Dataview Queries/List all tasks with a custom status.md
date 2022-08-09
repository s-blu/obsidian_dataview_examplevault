---
description: List all tasks that have a custom status (i.e. >)
---
#dv/task #dv/from #dv/where #dv/sort #dv/limit #dv/groupby 
# List all tasks with a custom status

## Basic 

```dataview
TASK
FROM "10 Example Data/dailys"
WHERE status = ">"
```

## Variants

Show only the most recent 5 todos grouped after their file day

> [!hint] 
> The first SORT (`SORT file.day DESC`) sorts the TASKS you're getting so you have the most recent at top. The second SORT (`rows.file.day DESC`) sorts your groups to have Feb 5 at the top instead of Jan 30 - try removing it!

```dataview
TASK
FROM "10 Example Data/dailys"
WHERE status = ">"
SORT file.day DESC
LIMIT 5
GROUP BY file.day
SORT rows.file.day DESC
```