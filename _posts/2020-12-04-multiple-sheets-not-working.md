---
layout: post
title:  "Multiple Sheets not working in SwiftUI"
date:   2020-12-04 08:58:31 +0100
---
You don't use multiple sheets ... instead use a single sheet with an enum.  [https://stackoverflow.com/a/63181811/3390](https://stackoverflow.com/a/63181811/3390)

``` swift
    @State var activeSheet: ActiveSheet? = .showGarminExplanation
    
    enum ActiveSheet: Identifiable {
        case fitbitLogin, showGarminExplanation, showXaiomiExplanation, showOuraExplanation
        
        var id: Int {
            hashValue
        }
    }

...
        .sheet(item: $activeSheet)  { item in
            switch item {
            case .fitbitLogin:
                SafariView(url: fitbit.url!)
            case .showGarminExplanation:
                GarminExplanationView()
            case .showXaiomiExplanation:
                GarminExplanationView()
            case .showOuraExplanation:
                GarminExplanationView()
            }
        }

```