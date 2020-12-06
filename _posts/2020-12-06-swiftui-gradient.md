---
layout: post
title:  "SwiftUI Radial Gradient with hex"
date:   2020-12-06 09:13:15 +0100
---

```
background: linear-gradient(197.54deg, #D0A0C3 0%, #D94E42 52.73%, #FAEF64 100%);
```

```swift
struct Hello: View {
    var body: some View {
        VStack() {
            Text("hello")
        }
        .frame(maxWidth: .infinity, maxHeight: .infinity)
        .foregroundColor(.white)
        .background(LinearGradient(gradient: Gradient(colors: [
            Color(red: 0xD0/255.0, green: 0xA0/255.0, blue: 0xC3/255.0),
            Color(red: 0xD9/255.0, green: 0x4E/255.0, blue: 0x42/255.0),
            Color(red: 0xFA/255.0, green: 0xEF/255.0, blue: 0x64/255.0),
        ]),
        startPoint: .topTrailing, endPoint: .bottomLeading))
    }
}
```

![Image of gradient](media/2020-12-06-gradient.png)