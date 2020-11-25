---
layout: post
title:  "Swift Localization"
date:   2020-11-25 15:39:00 +0100
---

1. Open Project properties and under `Localizations` add `French` to `Base` and `English-Development Language`
2. Add a new file called `Localizable.strings` using the `New File` dialog and filtering to `Strings File`
3. Right-click the new file, select `File Inspector` and under `Localization` check both `English` and `French`
4. Two sub-files under `Localizable.strings` should have appeared

To preview a language in SwiftUI
```swift
struct HomeView_Previews: PreviewProvider {
    static var previews: some View {
        HomeView()
            .environment(\.locale, .init(identifier: "fr"))
    }
}
```