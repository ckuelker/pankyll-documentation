---
title: Global Site Parameters
type: doc
author: Christian Külker
date: 2020-04-26
keywords:
    - Global Site Parameter Feature
categories:
    - Feature
tags:
    - Theme
description: Global site parameters feature documentation

---

The **global site parameter feature** is more a necessity than a feature.
Every site need to know the source and target directories: `content_dir:`,
`themes_dir:` and `public_dir:`. Then a fall back title is defined with
`title:` as well as the [theme] name with `theme_name:`. The theme name is the
name of the directory under `themes`. So for example if you are using a
fictional theme `star` in `themes` like so `themes/pankyl-theme-star`, then you
have the set the key `theme_name` as `theme_name: /pankyl-theme-star`. And last
but not least the `site:` section defines the `url:` key that is a prefix to
your site. Usually this is just `/`. But in principle it can be different.
The following keys are all mandatory.

```yaml
site:
  url:         /                             # URL pfx - mandatory
  title:       Pankyll Theme Example         # str     - mandatory (fallback)
  content_dir: content                       # dir     - mandatory
  public_dir:  public                        # dir     - mandatory
  themes_dir:  themes                        # dir     - mandatory
  theme_name:  pankyll-theme-newspaper       # dir     - mandatory
```

[Theme]: /en_US/Pankyll-Themes/

