---
layout: post
title:  "Adding a font to a SwiftUI app"
date:   2020-12-06 10:09:03 +0100
---
Download and unzip the font, for example from [https://fonts.google.com/specimen/Poppins](https://fonts.google.com/specimen/Poppins)

Drag the `.ttf` (for example `Poppins-Bold.ttf`) file into your Xcode project, perhaps in a folder called `Fonts` and ensure that it is included in your project's target (select it and verify `Target Membership` in the file properties).

Edit your `info.plist` and add a top level `Fonts provided by application` node, and then a child `Item 0` node with a value of the name of your font, for example `Poppins-Bold.ttf`.

Use the font in your app:

```swift
Text("hello")
    .font(.custom("Poppins-Bold", size: 48))
```



