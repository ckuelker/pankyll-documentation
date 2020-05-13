---
title: Imprint
type: doc
TOC: True
date: 2020-04-27
categories:
    - Feature
features:
    - Imprint
tags:
    - Home feature
    - HTML
    - Jinja2
    - Markdown
    - Pankyll
    - Themes
    - URL
description: Imprint feature documentation

---

Some states like Germany demand to have a page as in imprint for the web site.
The 'imprint feature' provide this for theme designers to easily add a link to
an imprint page wherever they see fit.  It is not mandatory for [Pankyll] to
have a imprint page. This section describes the usage and non usage of an
imprint page with [Pankyll]. The imprint feature depends on the localization
feature.

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

iTo use an imprint page with the imprint feature add the following snippet to
your site configuration in `cfg.yaml`. See `cfg.yaml` example below. Depending
on your supported languages, the snippet might look a little bit different.

## Site cfg.yaml Example

```yaml
imprint:                   # enable imprint feature
    en_US:                 # at least the default language
      url:   en_US/Imprint # the link target
      text:  Imprint       # the text of the link
    de_DE:
      url:   de_DE/Impressum/impressum.html
      text:  Impressum
    ja_JP:
      url:   ja_JP/Imprint
      text:  インプリント
```

For the [URL] to work correctly you should not add a prefix. The prefix of the
[URL] will be added by [Pankyll] and it depends on the site configuration in
`cfg.yaml`. If you imprint link points to a directory create an index
[Markdown] file. If you prefer a named link, it should point to the [HTML] file
that either exists in static or that will be created by [Pankyll] from a
[Markdown] file. [Themes] that support the [Pankyll] imprint will add a link to
the imprint page.

## Theme Jinja2 Template Example

```html
{% if has_imprint and imprint_url and imprint_text %}
  <div id='imprint'><a href="{{ imprint_url }}">{{ imprint_text }}</a></div>
{% endif %}

```

## Not Using An Imprint Page

> If you do not want to use an imprint page: (1) do not specify the keyword
> 'imprint' in `cfg.yaml` or (2) do not provide an imprint directory.

[Home feature]: /en_US/Documentation/Features/home.html
[HTML]: https://en.wikipedia.org/wiki/HTML
[Jinja2]: https://palletsprojects.com/p/jinja/
[Markdown]: https://en.wikipedia.org/wiki/Markdown
[Pankyll]: https://www.pankyll.org/
[Themes]: /en_US/Pankyll-Themes/
[URL]: https://en.wikipedia.org/wiki/URL
