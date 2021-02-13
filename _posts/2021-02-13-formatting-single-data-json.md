---
layout: post
title:  "Formatting a single swift date field in JSON"
date:   2021-02-13 14:57:40 +0100
---
You want to use one encoding strategy overall to encode JSON dates, but one particular field needs to be formatted using a different formatting?

Normally you'd set the encoding strategy for the whole encoding:

```swift
    let encoder = JSONEncoder()
    encoder.dateEncodingStrategy = .millisecondsSince1970 // or iso8601
    encoder.encode(myObject)
```

But what if deep down in the structure or class, one date field needs to be formatted a different way, such as the `timeStamp` field here?

```swift
    struct GeolocationState: EventBase {
        let timestamp: Date
        let coordinate: Coordinate
        let altitude: Altitude?
        let heading: Heading?
        let speed: Speed?
    }
```

My solution is to wrap the date in my own struct, and then I can control the encoding for that:

```swift
    struct GeolocationState: EventBase {
        let timestamp: ISO8601Date
        let coordinate: Coordinate
        let altitude: Altitude?
        let heading: Heading?
        let speed: Speed?
    }

    struct ISO8601Date: Encodable {
        static let formatter = ISO8601DateFormatter()
        let date: Date
        init(_ date: Date) { self.date = date }        

        enum CodingKeys: CodingKey { case date }
        
        func encode(to encoder: Encoder ) throws {
            var container = encoder.singleValueContainer()
            try container.encode(ISO8601FormattedDate.formatter.string(from: date))
        }
    }
```