---
layout: post
title:  "A VS Code Snippet to create Jekyll blog post frontmatter"
date:   2020-11-22 17:47:25 +0100
---


```json
"entry": {
    "scope": "markdown",
    "prefix": "en",
    "body": [
        "---",
"layout: post",
"title:  \"${1:title}\"",
"date:   $CURRENT_YEAR-$CURRENT_MONTH-$CURRENT_DATE $CURRENT_HOUR:$CURRENT_MINUTE:$CURRENT_SECOND +0100",
"---",
"${2:body}"
    ],
    "description": "post"
}
```

Create/update a root-level `settings.json` to enable tab-completion:

```json
{
    "editor.tabCompletion": "on"
}
```