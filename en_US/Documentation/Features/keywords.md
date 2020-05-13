---
title: Keywords
type: doc
TOC: True
date: 2020-04-26
keywords:
    - Keywords
categories:
    - Feature
tags:
    - HTML
    - Keywords
    - Pankyll
description: Keywords feature documentation

---

## Meta Keyword

The keyword feature is optional and references some different concepts: (A) The
keywords referenced in the [HTML] head meta section of the page invisible to
the user but usable by search engines to rate the page. The first step is to
define keywords in the front matter section of a page. Then secondly the
template iterates over all keywords and creates meta tags in the [HTML] head
section. The following tree section show the different aspects for a keyword
`example`.  The keyword feature is always available regardless of the
`cfg.yaml` site configuration.

### Page Front Matter Keyword

```yaml
keywords:
    - example
```

### Meta Keyword Template

```html
{% if keywords %}{% for keyword in keywords %}
        <meta name="keyword" content="{{ keyword }}">
{% endfor %}{% endif %}
```

### Meta Keyword HTML Rendered

```html
        <meta name="keyword" content="example">
```

## User Keywords

And (B), in addition to the above meaning of **keyword feature** the site
author can create sets of additional keyword classes for different kind of
keyword.  This kind of keywords should **not** be called `keyword` or
`keywords`. Let's have an example to clarify this. Assuming the site should
provide keywords by the author of a page, the site administrator could call
them `tags` and add two configuration sections, one is called `keywords:` (a
reserved word for this purpose) and the other one is called `tags:` to
`cfg.yaml` like this.

```yaml
keywords:
    - tags

tags:
    en_US:
        text: Tags
        url:  en_US/Tag
```

Of course this additional keyword can be called differently and also it is
possible to add more than one keyword kind.  While A theme can have support for
the **keyword feature**, your local configuration in `cfg.yaml` do not have to
use it. It is total optionally. If you do not want to use keywords do not add
the word 'keywords' to  `cfg.yaml` or leave this section empty. However, if you
would like to use keywords, you can so by adding keys to the section
'`keywords:` and then for every defined keyword key a section with translations
for that key.  Later your pages can use the keyword key inside the front matter
to add keywords. For every such entity a aggregation page is created by
[Pankyll] . A reserved word, which should **not** be used in `cfg.yaml`, but
may be used (or not) in the front matter only is the word 'keywords'. The
entries inside the 'keywords' section in the front matter can be used by a
theme to create [HTML] meta tags in the head of the [HTML] page as described
above. Unlike other keyword entities keywords which are assigned via front
matter 'keywords:' section, no aggregation page will be created. Let's see an
example, where we have to different kind of keywords: `apple` and `color`.

## Page Front Matter Of An English Page

```yaml
apple:
    - Golden Delicious
color:
    - Yellow
```

### Configuration

```yaml
keywords:
    - apple
    - color
apple:
    en_US:
        text: Apples
        url:  en_US/Apples
    de_DE:
        text: Äpfel
        url: de_DE/Apples
    ja_JP:
        text: りんご
        url: ja_JP/Apples
```

When running the `pankyll` command line tool or using the Makefile command
`make build` the following pages are created, assuming similar front matter at
the other languages pages. The `index.html` pages will give a list of keywords
where each keyword page, like `Golden Delicious.html` list all pages that
reference the keyword.

```
public/en_US/Apples/index.md
public/en_US/Apples/index.html
public/en_US/Apples/Golden Delicious.md
public/en_US/Apples/Golden Delicious.html
public/en_US/Color/index.md
public/en_US/Color/index.html
public/en_US/Apples/Yellow.md
public/en_US/Apples/Yellow.html
public/de_DE/Apples/index.md
public/de_DE/Apples/index.html
public/de_DE/Apples/Golden Delicious.md
public/de_DE/Apples/Golden Delicious.html
public/de_DE/Color/index.md
public/de_DE/Color/index.html
public/de_DE/Apples/Gelb.md
public/de_DE/Apples/Gelb.html
public/ja_JP/Apples/index.md
public/ja_JP/Apples/index.html
public/ja_JP/Apples/ゴールデンデリシャス.md
public/ja_JP/Apples/ゴールデンデリシャス.html
public/ja_JP/Color/index.md
public/ja_JP/Color/index.html
public/ja_JP/Apples/黄色.md
public/ja_JP/Apples/黄色.html
```

[HTML]: https://en.wikipedia.org/wiki/HTML
[Pankyll]: https://www.pankyll.org/

