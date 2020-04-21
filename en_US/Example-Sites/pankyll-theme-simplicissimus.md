---
title: Pankyll Theme Simplicissimus Example
author: Christian Külker
date: 2020-04-21 
type: doc

---

This [Pankyll] [theme] [example] is a template that shows how to configure a
site with the theme [Simplicissimus] and can be used to kick start once own site.

## Test The Example

Get the [example]:

```bash
export URL=https://github.com/ckuelker/pankyll-theme-simplicissimus-example.git
git clone --recursive $URL
cd pankyll-theme-simplicissimus-example
```

Run `pankyll` manually to populate the public directory or use the `Makefile`:

```bash
make realclean
make submodule-update
make build
make server
```

Point your browser to the [URL] given

## Resources

* [Simplicissimus theme example repository]
* [Simplicissimus theme example repository URL]
* [Simplicissimus theme documentation]

[example]: /en_US/Pankyll-Theme-Examples
[Pankyll]: https://www.pankyll.org/
[Simplicissimus]: /en_US/Pankyll-Themes/pankyll-theme-simplicissimus.html
[Simplicissimus theme example]: /en_US/Pankyll-Theme-Examples/pankyll-theme-simplicissimus-example.html
[Simplicissimus theme example repository]: https://github.com/ckuelker/pankyll-theme-simplicissimus-example/
[Simplicissimus theme example repository URL]: https://github.com/ckuelker/pankyll-theme-simplicissimus-example.git
[Simplicissimus theme documentation]: /en_US/Pankyll-Themes/pankyll-theme-simplicissimus.html
[theme]: /en_US/Pankyll-Themes/
[URL]: https://en.wikipedia.org/wiki/URL

