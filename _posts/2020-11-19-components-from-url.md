---
layout: post
title:  "Getting a # component from a URL"
date:   2020-11-19 12:01:00 +0100
---

From [https://stackoverflow.com/a/57933248/3390](https://stackoverflow.com/a/57933248/3390)

```swift
func HandleCallback(url: URL) {
    var components = URLComponents()
    components.query = url.fragment
    
    accessToken = components.queryItems?.first(where: { $0.name == "access_token"})?.value
}
```