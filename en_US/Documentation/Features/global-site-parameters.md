---
title: Global Website Parameters
type: doc
TOC: True
author: Christian Külker
date: 2020-04-26
keywords:
    - Global Website Parameter Feature
categories:
    - Feature
features:
    - Global Website Parameter
tags:
    - Theme
    - Pankyll
description: Global website parameters feature documentation

---

The **global website parameter feature** is more a necessity than a feature.
The global website configuration in `cfg.yaml` need to have the mandatory
section 'site' with some mandatory options for all themes.  Every website need
to know the source and target directories: `content_dir:`, `themes_dir:` and
`public_dir:`.  Then a fall back title is defined with `title:` as well as the
[theme] name with `theme_name:`. The theme name is the name of the directory
under `themes`.  So for example if you are using a fictional theme `star` in
`themes` like so `themes/pankyl-theme-star`, then you have the set the key
`theme_name` as `theme_name: /pankyl-theme-star`. And last but not least the
`site:` section defines the `url:` key that is a prefix to your website.
Usually this is just `/`.  But in principle it can be different.  While not all
themes have to use all options the following options are minimal and mandatory.


```yaml
site:
  url:         /                             # URL pfx - mandatory
  title:       Pankyll Theme Example         # str     - mandatory (fallback)
  content_dir: content                       # dir     - mandatory
  public_dir:  public                        # dir     - mandatory
  themes_dir:  themes                        # dir     - mandatory
  theme_name:  pankyll-theme-newspaper       # dir     - mandatory
```

This values are used from the project root to calculate what to include and
what not. On the project root level there should be a content directory that is
specified via the `content_dir:` option. This will be copied verbatim.  The
`public_dir:` option also specifies a directory, however [Pankyll] will create
or re-create this directory. Do not place any valuables in this directory.
[Pankyll] or the project Makefile might delete it without warning.

[Pankyll]: https://www.pankyll.org/
[Theme]: /en_US/Pankyll-Themes/

