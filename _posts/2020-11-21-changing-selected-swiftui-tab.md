---
layout: post
title:  "Changing the currently selected SwiftUI TabView tab"
date:   2020-11-21 09:37:00 +0100
---

```swift
struct OnboardingWizardView: View {
    @State var selectedTab = 0
    var body: some View {
        TabView(selection: $selectedTab) {
            Page1().tag(0)
            Page2().tag(1)
        }.tabViewStyle(PageTabViewStyle())
        .onAppear(perform: {
            DispatchQueue.main.asyncAfter(deadline: .now() + 2) {
                withAnimation {
                    self.selectedTab = 1
                }
            }
        })
        
    }
}
```