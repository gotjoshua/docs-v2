---
title: date.week() function
description: >
  The `date.week()` function returns the ISO week of the year for a specified time.
  Results range from `[1-53]`.
aliases:
  - /v2.0/reference/flux/functions/date/week/
menu:
  v2_0_ref:
    name: date.week
    parent: Date
weight: 301
---

The `date.week()` function returns the ISO week of the year for a specified time.
Results range from `[1-53]`.

_**Function type:** Transformation_  

```js
import "date"

date.week(t: 2019-07-17T12:05:21.012Z)

// Returns 29
```

## Parameters

### t
The time to operate on.

_**Data type:** Time_
