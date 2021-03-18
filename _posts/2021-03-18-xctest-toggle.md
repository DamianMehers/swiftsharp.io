---
layout: post
title:  "XCTest can't tap SwiftUI Toggle"
date:   2021-03-18 14:01:13 +0100
---
Using `tap` on a SwiftUI `Toggle` wasn't working for me:
```swift
    let app = XCUIApplication()
    let sw = app.switches["My SwiftUI Toggle"]
    XCTAssert(sw.value as! String == "0")
    sw.tap()
    XCTAssert(sw.value as! String == "1")
```
The above fails. I think this is because tapping the label part of the Toggle does nothing.  Instead, I try to tap the switch part of it, which works:
```swift
    let app = XCUIApplication()
    let sw = app.switches["My SwiftUI Toggle"]
    XCTAssert(sw.value as! String == "0")
    sw.coordinate(withNormalizedOffset: CGVector.zero).withOffset(CGVector(dx: sw.frame.width - 10, dy: sw.frame.height / 2)).tap()
    XCTAssert(sw.value as! String == "1")
```

Now it works - I tap in the vertical center, on the right side of the switch, minus ten points.