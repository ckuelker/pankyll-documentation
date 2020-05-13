---
title: Localization
linkTitle: l10n
type: doc
TOC: True
author: Christian Külker
date: 2020-04-26
keywords:
    - Localization
    - l10n
categories:
    - Feature
features:
    - Localization
tags:
    - Theme
    - Pankyll
description: Localization feature documentation

---

The usage of the localization (l10n) feature is mandatory, even if you use just
one language (as opposed to none), as many other parts and features of
[Pankyll] depend on at least one language. Which language is up to you. It
could be 'en_US' or 'de_DE' or what ever language you prefer. A minimal
configuration snippet for `cfg.yaml` looks like this.

```yaml
# 2. Feature: Internationalization
#    at minimum you have do define 1 language (the default)
locales:
      en_US: English
```

> A configuration for two languages looks like this.

```yaml
locales:
      en_US: English
      de_DE: Deutsch
```

[Pankyll]: https://www.pankyll.org/

