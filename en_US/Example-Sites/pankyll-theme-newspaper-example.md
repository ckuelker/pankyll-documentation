---
title: Pankyll Theme Newspaper Example
author: Christian Külker
date: 2020-04-08
type: blog
keywords:
 - Pankyll Theme Newspaper Example
tags:
    - Example
    - Newspaper
    - Newspaper theme documentation
    - Newspaper theme example repository
    - Newspaper theme example repository URL
    - Pankyll
    - URL
categories:
    - Theme
description: A Newspaper theme example

---

> This [Pankyll] [theme] [example] is a template that shows how to configure a
> site with the theme [Newspaper] and can be used to kick start once own site.

## Test The Example

> Get the [example]:

```bash
export URL=https://github.com/ckuelker/pankyll-theme-newspaper-example.git
git clone --recursive $URL
cd pankyll-theme-newspaper-example
```

> Run `pankyll` manually to populate the public directory or use the `Makefile`:

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

* [Newspaper theme example repository]
* [Newspaper theme example repository URL]
* [Newspaper theme documentation]

[Example]: /en_US/Example-Sites
[Newspaper]: /en_US/Pankyll-Themes/pankyll-theme-newspaper.html
[Newspaper theme documentation]: /en_US/Pankyll-Themes/pankyll-theme-newspaper.html
[Newspaper theme example repository]: https://github.com/ckuelker/pankyll-theme-newspaper-example/
[Newspaper theme example repository URL]: https://github.com/ckuelker/pankyll-theme-newspaper-example.git
[Pankyll]: https://www.pankyll.org/
[URL]: https://en.wikipedia.org/wiki/URL
