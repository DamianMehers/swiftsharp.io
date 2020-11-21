---
layout: post
title:  "Stopping SwiftUI Text from being clipped"
date:   2020-11-21 11:40:00 +0100
---

```swift
Text("You've been getting an average of 7 hours and 23 minutes of sleep each night over the last month, which is great.  Keep it up!")
    .fixedSize(horizontal: false, vertical: true)
    .padding()
```

From [Reddit](https://www.reddit.com/r/SwiftUI/comments/ehawu7/swiftui_text_gets_cut_off_with_in_my_view/)