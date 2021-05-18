---
title: Top 10
type: doc
TOC: True
author: Christian Külker
date: 2021-05-18
keywords:
    - Top 10
categories:
    - Feature
features:
    - Top 10
tags:
    - Rankle
    - Top 10
    - Pankyll
description: Top 10 feature documentation

---

The **Top 10** feature is provided by [pankyll] and supported by the theme
[Rankle]. It provides a link list to the 10 latest pages.

## Pankyll Theme Rankle

To use the feature it has to be enabled via the project configuration.
Depending on your setup this can be `cfg.yaml` or `rankle.yaml` via the
`default` section:

~~~
default:
    top10: True
~~~

The __top 10__ feature can be used on the left or right side of a page.

### Left Site

{{% pageinfo %}}

At the moment the left side __top 10__ feature is only available for title
pages. To set a page as title page use the front matter `type: title`.

{{% /pageinfo %}}

To use the __top 10__ feature on the left page side (indented for `index.md`
pages for example), you have to enable the feature in the project
configuration:

~~~
default:
   top10: True
~~~

In addition to this you can use the left side in two ways:

**a)**

Use the left side only for a very limited number of pages, like `index.md`
pages. To enable __top 10__ for a page explicitly add the following front
matter:

~~~
top10: True
~~~

**b)**

To use the left side __top 10__ feature on all sides add the following to your
project configuration:

~~~
default:
    top10: True
    top10_left: True
~~~

### Right Site

To use the __top 10__ feature on the right side of the page, you have to enable
right side variant in the default project configuration:

~~~
default:
    top10: True
    top10_right: True
~~~

This will add a menu entry "Latest" with the list when clicked on it on all
pages.


[Pandoc]:  https://pandoc.org/
[Pankyll]: https://www.pankyll.org/
[Rankle]:  https://www.pankyll.org/en_US/Pankyll-Themes/pankyll-theme-rankle.html

