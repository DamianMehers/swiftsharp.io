---
layout: post
title:  "Averaging a collection of values in Swift"
date:   2020-11-25 08:56:13 +0100
--- 
```swift
let averageMinutesAsleep = itemsToConsider.reduce(0) { $0 + $1.minutesAsleep} / itemsToConsider.count
```