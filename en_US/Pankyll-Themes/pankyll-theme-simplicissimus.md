---
title: Pankyll Theme Simplicissimus
author: Christian Külker
date: 2022-05-20
type: blog
keywords:
 - Pankyll Theme Simplicissmus
tags:
    - CSS
    - HTML
    - Simplicissimus
categories:
 - Theme
description: A Simple Theme

---

> The [Simplicissimus] theme is just HTML. Nothing else. No [CSS]. No fonts.
> Just plain [HTML]. Nothing more, noting less.

* [soucre](https://github.com/ckuelker/pankyll-theme-simplicissimus/)
* [git-url](https://github.com/ckuelker/pankyll-theme-simplicissimus.git)

## Installation

> Enter your project (assuming your project is called project):

```shell
cd project
mkdir themes
export URL=https://github.com/ckuelker/pankyll-theme-simplicissimus.git
git clone --recursive $URL
```

> If your project is already a git repository:

```shell
cd project
mkdir themes
export URL=https://github.com/ckuelker/pankyll-theme-simplicissimus.git
git submodule add -b master $URL themes//pankyll-theme-simplicissimus
git submodule init
```

## Features

* Default values
* Website values
* Internationalization
* Navigation
* Keywords

## Simplification

Some features of other themes are as of now deliberately not supported:

* Javascipt (JS)
* Table of contents (TOC)
* Word count
* Imprint (might be added later)
* CSS
* PDF
* Latest (top10)

Some of the features are defined in the configuration **feature** section. The
presence of this feature in the configuration is just to speed up [Pankyll] and
setting them to `True` will make [Pankyll] run longer, but not create the links
or other snippets to include this features.

[CSS]: https://en.wikipedia.org/wiki/Cascading_Style_Sheets
[HTML]: https://en.wikipedia.org/wiki/HTML
[Simplicissimus]: /en_US/Pankyll-Themes/pankyll-theme-simplicissimus.html
[Pankyll]: https://www.pankyll.org/
