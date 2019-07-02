---
title: movingAverage() function
description: >
  The `movingAverage()` function calculates the mean of values in a defined time
  range at a specified frequency.
menu:
  v2_0_ref:
    name: movingAverage
    parent: built-in-aggregates
weight: 501
---

The `movingAverage()` function calculates the mean of values in a defined time
range at a specified frequency.

_**Function type:** Aggregate_  

```js
movingAverage(
  every: 1d,
  period: 5d,
  column="_value",
  timeSrc="_stop",
  timeDst="_time",
)
```

## Parameters

### every
The frequency of time windows.

_**Data type:** Duration_

### period
The length of each averaged time window.
_A negative duration indicates start and stop boundaries are reversed._

_**Data type:** Duration_

### column
The column used to compute the moving average.
Defaults to `"_value"`.

_**Data type:** String_

### timeSrc
The column used as the source for the aggregated time.
Defaults to `"_stop"`.

_**Data type:** String_

### timeDst
The column in which to store the aggregated time.
Defaults to `"_time"`.

_**Data type:** String_

## Examples

###### Calculate a five year moving average every year
```js
from(bucket: "example-bucket"):
  |> range(start: -7y)
  |> filter(fn: (r) =>
    r._measurement == "financial" and
    r._field == "closing_price"
  )
  |> movingAverage(every: 1y, period: 5y)
```

## Function definition
```js
movingAverage = (every, period, column="_value", timeSrc="_stop", timeDst="_time", tables=<-) =>
  tables
    |> window(every: every, period: period)
    |> mean(column: column)
    |> duplicate(column: timeSrc, as: timeDst)
    |> window(every: inf)
```

<hr style="margin-top:4rem"/>

##### Related InfluxQL functions and statements:
[MOVING_AVERAGE()](https://docs.influxdata.com/influxdb/latest/query_language/functions/#moving-average)  