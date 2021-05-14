---
title: Include After
type: doc
TOC: True
author: Christian Külker
date: 2020-10-21
keywords:
    - Include After
categories:
    - Feature
features:
    - Include After
tags:
    - Rankle
    - Include After
    - Pankyll
description: Include After feature documentation

---

The **body include after** feature is provided by the theme [Rankle] for
the page type `doc` and is set via the configuration in `cfg.yaml`.
It will include text after the footer on all pages of the type `doc`.

## Example Configuration

Add this to the `site:` section of the configuration, for example in
`cfg.yaml`:

```yaml
site:
  body_include_after:  INSERT THIS AFTER THE FOOTER
```

[Pankyll]: https://www.pankyll.org/
[Rankle]:  https://www.pankyll.org/en_US/Pankyll-Themes/pankyll-theme-rankle.html

