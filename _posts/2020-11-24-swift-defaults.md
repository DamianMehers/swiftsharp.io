---
layout: post
title:  "Swift date in user defaults"
date:   2020-11-24 15:17:40 +0100
---
```swift
let expires = defaults.object(forKey: defaultsTokenExpiresName) as? Date
```