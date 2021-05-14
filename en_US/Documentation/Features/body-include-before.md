---
title: Include Before
type: doc
TOC: True
author: Christian Külker
date: 2020-10-21
keywords:
    - Include Before
categories:
    - Feature
features:
    - Include Before
tags:
    - Rankle
    - Include Before
    - Pankyll
description: Include Before feature documentation

---

The **body include before** feature is provided by the theme [Rankle] for the
page type `doc` and is set via the configuration in `cfg.yaml`.  It will
include text before the content, but after the menu on all pages of the type
`doc`.

## Example Configuration

Add this to the `site:` section of the configuration, for example in
`cfg.yaml`:

```yaml
site:
  body_include_before:  INSERT THIS AFTER THE MENU BAR AND BEFORE THE CONTENT
```

[Pankyll]: https://www.pankyll.org/
[Rankle]:  https://www.pankyll.org/en_US/Pankyll-Themes/pankyll-theme-rankle.html

