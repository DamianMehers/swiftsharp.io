---
layout: post
title:  "Widening Jekyll content area"
date:   2020-11-19 09:30:00 +0100
---

If your `minima` Jekyll page width is too narrow, copy the `_sass` folder from your Jekyll installation to your web site folder, and then edit `minima.scss` to update the width:

```
// Width of the content area
$content-width:    2048px !default;
```

You can find out where `minima` is installed using

```
bundle info --path minima
```