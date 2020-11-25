---
layout: post
title:  "Rounding the rectangle of a view background"
date:   2020-11-25 10:56:13 +0100
---
```swift
VStack {
    Label("text", systemImage: "pills.fill")
        .foregroundColor(.orange)
        .font(.title3)
}
.background(RoundedRectangle(cornerRadius: .foregroundColor(.orange).opacity(0.05))
```