---
layout: post
title:  "Adding days/weeks/months to dates"
date:   2021-01-06 13:08:36 +0100
---
```swift
let today = Date()
let date = Calendar.current.date(byAdding: .day, value: 7, to: today)!

```