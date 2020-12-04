---
layout: post
title:  "SwiftUI navigating"
date:   2020-11-27 10:22:24 +0100
---
```swift
var body: some View {
    NavigationView {
        VStack {
            Spacer()
            Image("someimage")
                .resizable()
                .aspectRatio(contentMode: .fit)
            Spacer()
        }
        .navigationBarTitle("Welcome!")
        .navigationBarItems(trailing:
                                NavigationLink("Next", destination: AnotherView(), isActive: $moveNext)
        )
        .onAppear(perform: {
            DispatchQueue.main.asyncAfter(deadline: .now() + 2) {
                withAnimation {
                    self.moveNext = true
                }
            }
        })

    }
    
}
```