---
layout: post
title:  "Detecting when state variable changes"
date:   2021-01-19 10:33:11 +0100
---
I tried using `willSet` or `didSet` on an `@State` variable, but it didn't work

```swift
@State var consumed: Bool = false {
    didSet {
        print("never called")
    }
}
```

Instead what works is to use the `onChange` event:

```swift
Toggle("My toggle", isOn: $consumed)
    .onChange(of: self.consumed) { v in
        print("is called")
    }

```