---
title: increase() function
description: >
  The `increase()` function calculates the cumulative sum of **non-negative** differences
  between subsequent values.
aliases:
  - /v2.0/reference/flux/functions/transformations/aggregates/increase
  - /v2.0/reference/flux/functions/built-in/transformations/aggregates/increase/
menu:
  v2_0_ref:
    name: increase
    parent: built-in-aggregates
weight: 501
related:
  - /v2.0/query-data/flux/increase/
---

The `increase()` function calculates the cumulative sum of **non-negative** differences
between subsequent values.
A main use case is tracking changes in counter values which may wrap over time
when they hit a threshold or are reset.
In the case of a wrap/reset, we can assume that the absolute delta between two
points will be at least their non-negative difference.

_**Function type:** Aggregate_  
_**Output data type:** Float_

```js
increase(columns: ["_value"])
```

## Parameters

### columns
The columns to use in the operation.
Defaults to `["_value"]`.

_**Data type:** Array of strings_

## Examples
```js
from(bucket: "example-bucket")
  |> range(start: -24h)
  |> filter(fn: (r) =>
    r._measurement == "system" and
    r._field == "n_users"
  )
  |> increase()
```

Given the following input table:

| _time | _value |
| ----- | ------ |
| 00001 | 1      |
| 00002 | 5      |
| 00003 | 3      |
| 00004 | 4      |

`increase()` produces the following table:

| _time | _value |
| ----- | ------ |
| 00002 | 4      |
| 00003 | 4      |
| 00004 | 5      |

## Function definition
```js
increase = (tables=<-, column="_value") =>
	tables
		|> difference(nonNegative: true, column:column)
		|> cumulativeSum()
```
