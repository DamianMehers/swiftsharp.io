---
layout: post
title:  "Making JSON have both sorted keys and pretty printed"
date:   2020-12-26 18:10:09 +0100
---
```swift
let encoder = JSONEncoder()
encoder.outputFormatting = JSONEncoder.OutputFormatting([.prettyPrinted, .sortedKeys])
````