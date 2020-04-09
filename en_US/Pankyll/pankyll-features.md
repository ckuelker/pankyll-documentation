---
title: Pankyll Features
type: doc
author: Christian Külker
version: v0.1.0
date: 2020-04-09
categories:
  - Pankyll
tags:
  - Features
description: Pankyll Feature Documentation

---

> WORK IN PROGRESS This document describes the features of [Pankyll] in a
> comprehensive way.

| Feature                 | cfg.yaml           | Front Matter | Mandatory |
|------------------------ | ------------------ | ------------ | --------- |
| Site                    | site:              |              | yes       |
| Localization (l10n)     | l10n:, languages:  |              | yes       |
| Imprint                 | imprint:           |              | no        |
| Site Title              | site.title:        |              |           |
| Page Title              |                    | title:       |           |
| Home                    | home:              |              | no        |
| Table Of Contents       | toc:               |              |           |
| Keywords                | keywords:, ...[1]  | ...[1]       | no        |
| Navigation              | navigation:        |              | no        |
| More                    | more:              |              |           |
| Site Description        | description:       |              |           |
| Page Description        |                    | description: | no        |
| Footer                  | footer:            |              |           |
| Type                    | type:              | type:        | yes       |
| Author                  |                    | author:      | no        |
| Date                    |                    | date:        | no        |
| Version                 |                    | version:     | no        |
|                         |                    |              |           |

[1] Valid keys are defined via 'keywords:' in `cfg.yaml`.

## Feature: Site

The global site configuration in `cfg.yaml` need to have the mandatory section
'site' with some mandatory options for all themes. While not all themes have
to use all options the following options are minimal and mandatory.

```yaml
site:
  url:         /                           # URL prefix - mandatory
  title:       Pankyll Themes              # string     - mandatory (fallback)
  content_dir: content                     # directory  - mandatory
  public_dir:  public                      # directory  - mandatory
  themes_dir:  themes                      # directory  - mandatory
  theme_name:  pankyll-theme-newspaper     # directory  - mandatory
```

From this values the location of the installed theme is calculated from the
project root as follows: `themes_dir`+`theme_name`. On the project root level
there should be a content directory that is specified via the `content_dir`
option. The `public_dir` option also specifies a directory, however [Pankyll]
will create or re-create this directory. Do not place any valuables in this
directory. [Pankyll] might delete it without warning.

## Feature: Localization (l10n)

The usage of the localization feature is mandatory, even if you use just one
language (as opposed to non), as many other parts and features of [Pankyll]
depend on at least one language. Which language is up to you. It could be 'en'
or 'de' or what ever language you prefer. A minimal configuration snippet for
`cfg.yaml` looks like this.

```yaml
l10n:            # localization - mandatory
  default: en_US # default language - mandatory
  languages:
    en_US: English
```

## Feature: Imprint

Some countries demand an imprint page. It is not mandatory for [Pankyll] to
have a imprint page. This section describes the usage and non usage of an
imprint page with [Pankyll]. The imprint feature depends on the localization
feature.

### Not Using An Imprint Page

> If you do not want to use an imprint page, do not specify the keyword
> 'imprint' in `cfg.yaml`.

### Using An Imprint Page

To use an imprint page with the imprint feature add the following snippet to
your site configuration in `cfg.yaml`. Depending on your supported languages,
the snippet might look a little bit different. For the [URL] to work correctly
you should not add a prefix. The prefix of the [URL] will be added by [Pankyll]
and it depends on the site configuration in `cfg.yaml`. If you imprint link
points to a directory, you should add a slash at the end and create and index
[Markdown] file. If you prefer a named link, it should point to the [HTML] file
that either exists in static or that will be created by [Pankyll] from a
[Markdown] file. [Themes] that support the [Pankyll] imprint will add a link to
the imprint page.

```yaml
imprint:                     # enable imprint feature
    en_US:                   # at least the default language
      url:   /en_US/Imprint/ # the link target
      text:  Imprint         # the text of the link
      dir:   en_US/Imprint   # if present sets 'has_imprint=True'
    de_DE:
      url:   /de_DE/Imprint/
      text:  Impressum
      dir:   de_DE/Imprint
    ja_JP:
      url:   /ja_JP/Imprint/
      text:  インプリント
      dir:   ja_JP/Imprint
```

## Feature: Title

This feature provided by [Pankyll] in accordance to the configuration in
`cfg.yaml`. The feature provides the variable `title` to be used in templates
like `{{ title }}`. The title value is calculated as follows:

1. If `title` is set in the front matter use this as title.
2. If `home.$LANGUAGE.text` is defined in `cfg.yaml` for the language of the
   page, use it as a title.
3. Use `site.title` from `cfg.yaml` as a fallback.

## Feature: Home

The home feature is basically a feature to define the link home. As it is
recommended to use this feature, because [Pankyll] is using to calculate a
template `{{ title }}` value. (See feature title)

```yaml
home:
    en_US:
        text: Pankyll Themes  # home_text
        url: /en_US/              # home_url
    de_DE:
        text: Pankyll Layouts
        url: /de_DE/
    ja_JP:
        text: パンキュル　セーム
        url: /ja_JP/
```

## Feature: Table Of Contents

WORK IN PROGRESS

The 'table of contents' feature collects the headings from a markdown file and
creates a [HTML] table of contents that can be used by a theme to display a table
of contents. The doc is created regardless if a page is requesting not to
display it. [Themes] are recommended to obey the page wish. For the 'table of
content' feature to work [Pankyll] needs to work hand in hand wit the theme and
vice versa. Here is how it works.  1. [Pankyll] uses [Pandoc] and the [Pandoc] 
template `toc.markdown` to extract the table of content from a [Markdown] file.
2. After this step again [Pandoc] is used to convert the 'table of content' to
HTML. 3. This [HTML] snippet is than presented to the theme via the variable `{{
toc }}`. 4. Now for a theme to work [Pankyll] supports the front matter key
`toc_hide: True` or `toc_hide: False`.  If `toc_hide` is missing, it is treated
as `toc_hide: False`. A theme who displays a 'table of content' (which is
optional) just need to test if there is a `toc` content and if there is no
`toc_hide`. The following is an example from `pankyll-theme-newspaper`.

```html
{% if not frontmatter.toc_hide and toc %}
<div class="table-of-contents" id="table-of-contents-container">
    {% if cfg.toc[language].text %}
    <strong>{{ cfg.toc[language].text }}</strong>
    {% endif %}
{{ toc }}
</div>
{% endif %}
```

> If the theme uses the 'table of content' feature and you should add
> the language localization (translation) to your configuration.

```yaml
toc:
    en_US:
        text: Table Of Contents # alternative: Contents
    de_DE:
        text: Inhalt
    ja_JP:
        text: 目次
```

## Feature: Keywords

The keyword feature is optional. While A theme can have support for the keyword
feature, your local configuration in `cfg.yaml` do not have to use it. It is
total optionally. If you do not want to use keywords do not add the word
'keywords' to  `cfg.yaml` or leave this section empty. However, if you would
like to use keywords, you can so by adding keys to the section 'keywords' and
than for every defined keyword key a section with translations for that key.
Later your pages can use the keyword key inside the front matter to add
keywords. For every such entity a aggregation page is created by [Pankyll] . A
reserved word, which should **not** be used in `cfg.yaml`, but may be used (or
not) in the front matter only is the word 'keywords'. The entries inside the
'keywords' section in the front matter can be used by a theme to create HTML
meta tags in the head of the [HTML] page. Unlike other keyword entities
keywords which are assigned via front matter 'keywords:' section, no
aggregation page will be created.

**Configuration:**

```yaml
keywords:
    - categories
    - tags

categories:
    en_US:
        text: Categories
        url:  /en_US/Categories/
        dir:  Categories
    de_DE:
        text: Kategorien
        url:  /de_DE/Categories/
        dir:  Categories
    ja_JP:
        text: カテゴリー
        url:  /ja_JP/Categories/
        dir:  Categories
```

**Example front matter:**

```yaml
categories:  # aggregation page is created using cfg.yaml 'categories:' section
   - Linux
   - Free Open Source Software
   - Debian
keywords: # no aggregation page, HTML meta tags only
   - FOSS
```

## Feature: Navigation

```yaml
navigation:
    en_US:
        - link:
            text: Pankyll
            url:  /en_US/Pankyll/
        - link:
            text: Pankyll Themes
            url:  /en_US/Pankyll-Themes/
        - link:
            text: Pankyll Theme Example
            url:  /en_US/Pankyll-Theme-Example/
        - link:
            text: Categories
            url:  /en_US/Categories/
        - link:
            text: Tags
            url:  /en_US/Tags/
    de_DE:
```


[features]: /en_US/Pankyll/pankyll-features.html
[git]: https://git-scm.com/
[HTML]: https://en.wikipedia.org/wiki/HTML
[Markdown]: https://en.wikipedia.org/wiki/Markdown
[more about Pankyll]: /en_US/Pankyll/
[Newspaper]: /en_US/Pankyll-Themes/pankyll-theme-newspaper.html
[Newspaper theme example]: https://github.com/ckuelker/pankyll-theme-newspaper-example
[Pandoc]: https://pandoc.org/
[Pankyll]: https://www.pankyll.org/
[pankyll-documentation]: https://github.com/ckuelker/pankyll-documentation
[Pankyll repository]: https://github.com/ckuelker/pankyll
[PDF]: https://en.wikipedia.org/wiki/PDF
[Python]:  https://www.python.org/
[Rankle theme example]: /en_US/Pankyll-Theme-Example/pankyll-theme-rankle-example.html
[Rankle]: /en_US/Pankyll-Themes/pankyll-theme-rankle.html
[themes]: /en_US/Pankyll-Themes/
[URL]: https://en.wikipedia.org/wiki/URL/
[YAML]: https://yaml.org/


