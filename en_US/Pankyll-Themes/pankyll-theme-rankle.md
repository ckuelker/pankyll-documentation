---
title: Pankyll Theme Rankle
author: Christian Külker
date: 2020-04-24
type: blog
TOC: True
keywords:
 - Pankyll Theme Rankle
tags:
    - Gettext
    - Jinja2
    - Pankyll
    - Python gettext
    - Rankle
categories:
    - Theme
description: A Document Oriented Theme

---

The [Rankle] theme tailors to the needs of easy to read documentation and focus
on versioned pages in git while make it still possible to add opinionated blog
pages, either separated or mixed. This page describes briefly the [Pankyll]
theme [Rankle]. It shows the prerequisites, the installation, the features and
configuration of the theme. The lightweight theme's main feature is to use
contrast colors for different information sections, that let you focus on the
distinct sections.

* [soucre](https://github.com/ckuelker/pankyll-theme-rankle/)
* [git-url](https://github.com/ckuelker/pankyll-theme-rankle.git)

## Installation

### Prerequisites

## I18n

[Pankyll] uses [Jinja2] templates with [gettext] support for i18n by using the
[Python gettext] module.

**Old - python-brace-format:**

```html
{% if wordcount and wordcount > 99 %}
<li>
  A  {{ngettext('{num} word','{num} words', wordcount).format(num=wordcount)}}
</li>
{% endif %}
```

```po
#: layouts/partials/wordcount.html:3
msgid "{num} word"
msgid_plural "{num} words"
msgstr[0] "{num} Wort"
msgstr[1] "{num} Worte"
```

**New - python-format:**

```html
{% if wordcount and wordcount > 99 %}
<li>
  B  {{ngettext("%(num)d word","%(num)d words", wordcount)}}
</li>
{% endif %}
```

```po
#: layouts/partials/wordcount.html:4
msgid "%(num)d word"
msgid_plural "%(num)d words"
msgstr[0] "%(num)d Wort"
msgstr[1] "%(num)d Worte"
```

## Feature: More-Menu

```yaml
more:
    en_US:
        - link:
            text: Categories
            url:  /en_US/Categories/
        - link:
            text: Tags
            url:  /en_US/Tags/


```

[Gettext]: https://www.gnu.org/software/gettext/
[Jinja2]: https://palletsprojects.com/p/jinja/
[Pankyll]: https://www.pankyll.org/
[Python gettext]: https://docs.python.org/3/library/gettext.html
[Rankle]: /en_US/Pankyll-Themes/pankyll-theme-rankle.html
