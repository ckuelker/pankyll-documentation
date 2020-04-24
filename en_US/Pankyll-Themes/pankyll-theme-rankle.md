---
title: Pankyll Theme Rankle
author: Christian Külker
date: 2020-04-24
type: blog
keywords:
 - Pankyll Theme Rankle
tags:
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

[example]: /en_US/Example-Sites
[features]: /en_US/Pankyll/pankyll-features.html
[gettext]: https://www.gnu.org/software/gettext/
[git]: https://git-scm.com/
[HTML]: https://en.wikipedia.org/wiki/HTML
[Jinja2]: https://jinja.palletsprojects.com/en/2.11.x/
[Markdown]: https://en.wikipedia.org/wiki/Markdown
[more about Pankyll]: /en_US/Pankyll/
[Newspaper]: /en_US/Pankyll-Themes/pankyll-theme-newspaper.html
[Newspaper theme example]: https://github.com/ckuelker/pankyll-theme-newspaper-example
[Newspaper theme example repository]: https://github.com/ckuelker/pankyll-theme-newspaper-example/
[Newspaper theme example repository URL]: https://github.com/ckuelker/pankyll-theme-newspaper-example.git
[Newspaper theme documentation]: /en_US/Pankyll-Themes/pankyll-theme-newspaper.html
[Pandoc]: https://pandoc.org/
[Pankyll]: https://www.pankyll.org/
[pankyll-documentation]: https://github.com/ckuelker/pankyll-documentation
[Pankyll repository]: https://github.com/ckuelker/pankyll
[PDF]: https://en.wikipedia.org/wiki/PDF
[Python]:  https://www.python.org/
[Python gettext]: https://docs.python.org/3/library/gettext.html
[Rankle theme example]: /en_US/Example-Sites/pankyll-theme-rankle-example.html
[Rankle theme example repository]: https://github.com/ckuelker/pankyll-theme-rankle-example/
[Rankle theme example repository URL]: https://github.com/ckuelker/pankyll-theme-rankle-example.git
[Rankle theme documentation]: /en_US/Pankyll-Themes/pankyll-theme-rankle.html
[Rankle]: /en_US/Pankyll-Themes/pankyll-theme-rankle.html
[theme]: /en_US/Pankyll-Themes/
[themes]: /en_US/Pankyll-Themes/
[URL]: https://en.wikipedia.org/wiki/URL
[YAML]: https://yaml.org/

