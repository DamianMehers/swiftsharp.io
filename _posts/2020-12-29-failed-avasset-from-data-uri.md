---
layout: post
title:  "A failed attempt to get an AVAsset from a data uri"
date:   2020-12-29 11:59:37 +0100
---

This is my attempt.  It doesn't work.  The best workaround is to [write the data to file first](https://stackoverflow.com/a/50012911/3390)

```swift
var base64 = data.base64EncodedString(options: [])

base64 = base64.replacingOccurrences(of: "=", with: "")
base64 = base64.replacingOccurrences(of: "+", with: "-")
base64 = base64.replacingOccurrences(of: "/", with: "_")

let dataURL = URL(string: "data:audio/mpeg;base64,\(base64)")!
let asset = AVAsset(url: dataURL)
let millis =  Int(CMTimeGetSeconds(asset.duration)*1000) // Returns zero
```