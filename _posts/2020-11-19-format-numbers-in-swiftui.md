---
layout: post
title:  "Formatting numbers in SwiftUI"
date:   2020-11-19 10:36:00 +0100
---


```swift
Text("\(food.loggedFood.amount, specifier: "%.1f") \(food.loggedFood.unit.plural)")
```
