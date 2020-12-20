---
layout: post
title:  "Indexing into a string"
date:   2020-12-15 08:25:27 +0100
---
```Swift
// [3] = (key = "Content-Type", value = "multipart/related; boundary=------abcde123; type=application/json")
let boundaryKey = "boundary="
guard let contentType = headers["Content-Type"] else {
    logE("opened", "No content type header)")
    return 
}

let contentTypeParts = contentType.split(separator: ";").map {$0.trimmingCharacters(in: .whitespaces) }
guard let boundaryPart = contentTypeParts.first(where: {  $0.starts(with: boundaryKey)}) else {
    logE("opened", "Can't find boundary in \(contentType)")
    return
}

let boundary = String(boundaryPart[boundaryPart.index(boundaryPart.startIndex, offsetBy: boundaryKey.count)...])

```