---
layout: post
title:  "Making a SwiftUI Text fill the frame"
date:   2020-11-20 10:40:00 +0100
---

To make a SwiftUI Text fill the frame:

```swift
Text("Welcome")
    .font(.largeTitle)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
```