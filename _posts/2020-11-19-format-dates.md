---
layout: post
title:  "Formatting and delta dates in Swift"
date:   2020-11-19 11:44:00 +0100
---


```swift
let dateFormatter = DateFormatter()
dateFormatter.dateFormat = "yyyy-MM-dd"
let today = dateFormatter.string(from: Date())
let monthAgo = dateFormatter.string(from: NSCalendar.current.date(byAdding: .month, value: -1, to: NSDate() as Date)!)
```