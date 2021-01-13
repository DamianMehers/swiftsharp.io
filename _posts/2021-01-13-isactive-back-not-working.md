---
layout: post
title:  "isActive not working to go back when three levels deep"
date:   2021-01-13 18:00:31 +0100
---
In my app I am using `NavigationLink.isActive` to programatically go back by setting a bound variable to `false`.  I was doing this several levels deep, and although I could initially go back, once I pushed several views onto the stack, and then went back, I found the back button stopped working on one of the pages.

I also noticed this error:

```
2021-01-13 18:02:26.660739+0100 Resolute[6210:333764] [Assert] displayModeButtonItem is internally managed and not exposed for DoubleColumn style. Returning an empty, disconnected UIBarButtonItem to fulfill the non-null contract.
```

[This](https://stackoverflow.com/a/64752414/3390) Stack Overflow page suggested setting the `navigationViewStyle` to `StackNavigationViewStyle`:

```
NavigationView {
    ...
}
.navigationViewStyle(StackNavigationViewStyle())
```

This both got rid of the error, and the back button started working (setting the `isActive` bound variable to `false`)