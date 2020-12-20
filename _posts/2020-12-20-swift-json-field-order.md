---
layout: post
title:  "Swift does not preserve field order when encoding json"
date:   2020-12-20 09:36:22 +0100
---
Converting code from .NET to Swift I've discovered that Swift does not preserve the order in which fields are declared when encoding JSON.

There is a bug about it: [https://bugs.swift.org/browse/SR-7992](https://bugs.swift.org/browse/SR-7992)

Support forums are full of people saying the order should not matter, but the reality is that some servers, over which we have no control, require a specific ordering, and it would be nice if Swift supported specifying or even preserving the field order when encoding JSON.

My solution, in a very limited situation, was to use string interpolation to insert my values into a pre-encoded JSON string which had the correct ordering.