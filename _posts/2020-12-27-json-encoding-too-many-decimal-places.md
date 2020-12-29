---
layout: post
title:  "When JSON encoding a Double there are too many decimal places"
date:   2020-12-27 10:48:40 +0100
---
If you are trying to generate JSON and a double is encoded with loads of decimal places and weird "1" at the end, like this:

```swift
struct Coordinate: Encodable {
    let latitudeInDegrees: Double
    let longitudeInDegrees: Double
    let accuracyInMeters: Double
}
let coordinate = Coordinate(latitudeInDegrees: 37.785834, longitudeInDegrees: -122.406417, accuracyInMeters: 5)
```

Generates JSON:
```json
{
    "coordinate" : {
        "accuracyInMeters" : 5,
        "latitudeInDegrees" : 37.785834000000001,
        "longitudeInDegrees" : -122.406417
    }
}
```

Change the type from `Double` to `Decimal`:

```swift
struct Coordinate: Encodable {
    let latitudeInDegrees: Decimal
    let longitudeInDegrees: Decimal
    let accuracyInMeters: Decimal
}
```