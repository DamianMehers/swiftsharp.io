---
layout: post
title:  "A generic function with a type as a parameter"
date:   2020-11-19 09:55:00 +0100
---

Pass the type of a generic parameter using `T.Type`


```swift
    var cancellables = [AnyCancellable]()
    
    fileprivate func GetData<T>(url: URL, token: String, resultType: T.Type,  callback: @escaping (T) -> Void) where T:Codable {
        var request = URLRequest(url: url)
        request.setValue("Bearer \(token)", forHTTPHeaderField: "Authorization")
        URLSession.shared.dataTaskPublisher(for: request)
            .tryMap() { element -> Data in
                // let s = String(data: element.data, encoding: .utf8)
                // print(s)
                guard let httpResponse = element.response as? HTTPURLResponse,
                      httpResponse.statusCode == 200 else {
                    throw URLError(.badServerResponse)
                }
                return element.data
            }
            .decode(type: resultType, decoder: self.decoder)
            .receive(on: DispatchQueue.main)
            .sink(receiveCompletion: { v in
                print(v)
            },
            receiveValue: { v in
                callback(v)
            })
            .store(in: &self.cancellables)
    }
```