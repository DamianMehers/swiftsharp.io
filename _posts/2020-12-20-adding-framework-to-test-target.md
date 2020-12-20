---
layout: post
title:  "Adding a framework to a test target"
date:   2020-12-20 19:08:42 +0100
---
I wanted to add the [AnyCodable](https://github.com/Flight-School/AnyCodable) to both my iOS project, and the test project that tests it.

When I added it to just my iOS project I got the error `Undefined symbol: nominal type descriptor for AnyCodable.AnyCodable` when trying to run tests.

My solution was to remove the framework, and then re-add it, this time specifying the test target as the target into which the framework should be added.

Once I did that, I was `then` able to go to my iOS project's target, and in the `General` pane, scroll down to `Frameworks, Libraries, and Embedded Content` and add it there.
