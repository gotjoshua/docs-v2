---
title: distinct() function
description: The `distinct()` function returns the unique values for a given column.
aliases:
  - /v2.0/reference/flux/functions/transformations/selectors/distinct
  - /v2.0/reference/flux/functions/built-in/transformations/selectors/distinct/
menu:
  v2_0_ref:
    name: distinct
    parent: built-in-selectors
weight: 501
related:
  - https://docs.influxdata.com/influxdb/latest/query_language/functions/#distinct, InfluxQL – DISTINCT()
---

The `distinct()` function returns the unique values for a given column.
The `_value` of each output record is set to the distinct value in the specified column.
`null` is considered its own distinct value if it is present.

_**Function type:** Selector_  
_**Output data type:** Object_

```js
distinct(column: "host")
```

## Parameters

### column
Column on which to track unique values.

_**Data type:** string_

## Examples
```js
from(bucket: "example-bucket")
	|> range(start: -5m)
	|> filter(fn: (r) => r._measurement == "cpu")
	|> distinct(column: "host")
```
