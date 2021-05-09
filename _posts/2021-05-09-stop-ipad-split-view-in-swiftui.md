---
layout: post
title:  "Stop iPad Split View in SwiftUI"
date:   2021-05-09 13:56:36 +0200
category: 
---

Set `navigationViewStyle` to `StackNavigationViewStyle`
```swift
NavigationView {
    TheTabView()
}
.navigationViewStyle(StackNavigationViewStyle())
```
