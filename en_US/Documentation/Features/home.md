---
title: Home
type: doc
TOC: True
author: Christian Külker
date: 2020-04-26
keywords:
    - Home
categories:
    - Feature
tags:
    - Home
    - Pankyll
    - Themes
    - Title
description: Home feature documentation

---

The **home feature** is basically a feature to define the link home. This will
set two variables inside the template depending on the locale: `{{home_text}}`
and `{{home_url}}`. [Themes] are encouraged to use this over
`href="{{cfg.site.url}}"` and `{{cfg.site.title}}` as this will only link back
to the default language/ locale.  It is strongly recommended to use this
feature, also because [Pankyll] is using it to calculate a template `{{title}}`
value. (See feature [title])

```yaml
home:
    en_US:
        text: Pankyll Themes  # home_text
        url: en_US            # home_url
    de_DE:
        text: Pankyll Layouts
        url: de_DE
    ja_JP:
        text: パンキュル　セーム
        url: ja_JP
```

[Pankyll]: https://www.pankyll.org/
[Themes]: /en_US/Pankyll-Themes/
[Title]: /en_US/Documentation/Features/title.html

