---
title: Imprint-Feature
type: doc
author: Christian Külker
date: 2020-04-19
description: Imprint feature documentation

---

Some states like Germany need to have a page as in imprint to the web site.
The 'imprint feature' provide this for theme designers to easily add a link to
an imprint page wherever they see fit.

## How It Works

[Pankyll] provides the [Jinja2] variables  `has_imprint`, `imprint_url` and
`imprint_text`. The configuration provides a directory key `url`. This is
needed, because there are cases where a git repository is used in different
cases: (a) as an example content (without imprint site) and (b) as a real
deployed site (with imprint page). Pankyll will dispatch this cases by the
existence of this file or directory. If the directory or files do not exist (or
the whole imprint configuration) the `has_imprint` will be set to `False` and
the `imprint_url` and `imprint_text` will be set (for now) to the values of the
[home feature], but should not be used by a theme.

The key `has_imprint` will be set to `True` if the site
configuration `cfg.yaml` fulfill the following criteria:

* has the key `imprint`
* the key `imprint` has the current locale key (e.g. `de_DE`)
* the current locale key has `url` key
* the current locale key has `text` key
* the directory or file of the `url` key exists

See `cfg.yaml` example below

## Site cfg.yaml Example

```yaml
imprint:
    en_US:
      url:   en_US/Imprint
      text:  Imprint
    de_DE:
      url:   de_DE/Impressum/impressum.html
      text:  Impressum
```

## Theme Jinja2 Template Example

```html
{% if has_imprint and imprint_url and imprint_text %}
  <div id='imprint'><a href="{{ imprint_url }}">{{ imprint_text }}</a></div>
{% endif %}

```

[Pankyll]: https://www.pankyll.org/
[Jinja2]:  https://palletsprojects.com/p/jinja/
[home feature]: https://www.pankyll.org/en_US/Documentation/home-feature.html


