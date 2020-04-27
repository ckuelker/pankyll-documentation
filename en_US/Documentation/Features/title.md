---
title: Title
type: doc
author: Christian Külker
date: 2020-04-26
keywords:
    - Title
categories:
    - Feature
tags:
    - Home
    - Title
    - Pankyll
description: Title feature documentation

---

The **title** feature is provided by [Pankyll] in accordance to the
configuration in `cfg.yaml`. The feature provides the variable `title` to be
used in templates like `{{title}}`. The title value is calculated as follows:

1. If `title` is set in the front matter use this as title.
2. If `home.$LOCALE.text` is defined via the [home] feature in `cfg.yaml` for
   the locale of the page, use it as a title.
3. Use `site.title` from `cfg.yaml` as a fallback.

## Example Page Title In Front Matter

```yaml
title: Pankyll
```

## Example Home Title

```yaml
# 4. Feature: Home
home:
    en_US:
        text: Pankyll  # home_text
        url:  en_US    # home_url
    de_DE:
        text: Pankyll
        url:  de_DE

```
## Example Site Fallback Title

```yaml
site:
    title: Pankyll
```

[Home]: /en_US/Documentation/Feature/home.html
[Pankyll]: https://www.pankyll.org/

