---
layout: post
title:  "Converting an object to a raw pointer and back"
date:   2021-01-01 13:58:49 +0100
---
To a pointer

```swift
let rawPointer = unsafeBitCast(anObject, to: UnsafeMutableRawPointer.self)
```

... and back

```swift
let anObject = Unmanaged<TheClassObjectsClass>.fromOpaque(UnsafeRawPointer(rawPointer)).takeUnretainedValue()
```