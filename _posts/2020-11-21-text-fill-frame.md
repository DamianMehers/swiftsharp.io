---
layout: post
title:  "Making a SwiftUI Text fill the frame"
date:   2020-11-21 09:25:00 +0100
---

```swift
Text("Welcome")
    .font(.largeTitle)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
```