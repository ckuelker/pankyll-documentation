---
title: Navigation
type: doc
TOC: True
date: 2020-04-26
keywords:
    - Navigation
categories:
    - Feature
tags:
    - Navigation
    - Pankyll
    - Theme
    - Themes
    - URL
    - YAML
description: Navigation feature documentation

---

The **navigation** feature is optional, however it comes quite handy for
[themes] that support it. Usually the [theme] will create a top menu bar from
it or left/ right site navigation pane. The configuration for the
**navigation** feature in `cfg.yaml` basically provides a link list for every
language of your site. Since the order of the links are important the shape of
the configuration is a [YAML] list. For every link the [URL] and the link text
need to be provided. See the example below.

```yaml
navigation:
    en_US:
        - link:
            text: Pankyll
            url:  en_US/Pankyll
        - link:
            text: Pankyll Themes
            url:  en_US/Pankyll-Themes
        - link:
            text: Pankyll Theme Example
            url:  en_US/Example-Sites
        - link:
            text: Categories
            url:  en_US/Categories
        - link:
            text: Tags
            url:  en_US/Tags
```

[Theme]: /en_US/Pankyll-Themes/
[Themes]: /en_US/Pankyll-Themes/
[URL]: https://en.wikipedia.org/wiki/URL
[YAML]: https://yaml.org/
