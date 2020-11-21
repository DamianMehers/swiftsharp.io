---
layout: post
title:  "Delaying execution of code in SwiftUI"
date:   2020-11-21 09:46:00 +0100
---

```swift
    ImagePicker(sourceType: .photoLibrary) { image in
        self.image = Image(uiImage: image)
        DispatchQueue.main.asyncAfter(deadline: .now() + 2) {
            self.showProgress = false
        }
    }
```