---
title: Pankyll Theme Rankle Example
author: Christian Külker
date: 2020-04-08
type: blog
TOC: True
keywords:
    - Pankyll Theme Rankle Example
tags:
    - Example
    - Pankyll
    - Rankle
    - Rankle theme documentation
    - Rankle theme example repository
    - Rankle theme example repository URL
    - URL
categories:
    - Theme
description: A Rankle theme example

---

> This [Pankyll] [theme] [example] is a template that shows how to configure a
> site with the theme [Rankle] and can be used to kick start once own site.

## Test The Example

> Get the [example]:

```bash
export URL=https://github.com/ckuelker/pankyll-theme-rankle-example.git
git clone --recursive $URL
cd pankyll-theme-rankle-example
```

> Run `pankyll` manually to populate the public directory or use the
> `Makefile`:

```bash
make realclean
make submodule-update
make submoduleclean
make submodule-pull
make build
make server
```

> Point your browser to the [URL] given

## Resources

* [Rankle theme example repository]
* [Rankle theme example repository URL]
* [Rankle theme documentation]

[example]: /en_US/Example-Sites/
[Pankyll]: https://www.pankyll.org/
[theme]: /en_US/Pankyll-Themes/
[Rankle]: /en_US/Pankyll-Themes/pankyll-theme-rankle.html
[Rankle theme example]: /en_US/Example-Sites/pankyll-theme-rankle-example.html
[Rankle theme example repository]: https://github.com/ckuelker/pankyll-theme-rankle-example/
[Rankle theme example repository URL]: https://github.com/ckuelker/pankyll-theme-rankle-example.git
[Rankle theme documentation]: /en_US/Pankyll-Themes/pankyll-theme-rankle.html
