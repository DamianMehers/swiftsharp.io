---
layout: post
title:  "Launching processes in Swift"
date:   2021-05-05 11:05:27 +0200
category: 
---

Launching multiple commands in Swift

```swift
        do {
            try writePost()
            let add = Process()
            add.currentDirectoryPath = root
            add.executableURL = URL(fileURLWithPath: git)
            add.arguments = ["add", "."]
            try add.run()
            
            let commit = Process()
            commit.currentDirectoryPath = root
            commit.executableURL = URL(fileURLWithPath: git)
            commit.arguments = ["commit","-m", "\"title\""]
            try commit.run()
            commit.waitUntilExit()
            
            let push = Process()
            push.currentDirectoryPath = root
            push.executableURL = URL(fileURLWithPath: git)
            push.arguments = ["push"]
            try push.run()
            push.waitUntilExit()
            
        } catch {
            errorMessage =  "Error: \(error)"
        }
```