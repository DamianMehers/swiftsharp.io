---
layout: post
title:  "Note to self"
date:   2020-11-19 08:43:51 +0100
---
When trying to serve your site using `jekyll` and you get an error like this:

```
jekyll serve
...
/Library/Ruby/Gems/2.6.0/gems/bundler-2.1.4/lib/bundler/spec_set.rb:86:in `block in materialize': Could not find public_suffix-4.0.6 in any of the sources (Bundler::GemNotFound)
```

don't forget you need to use `bundle exec jekyll serve`