---
title:  Creating A Pankyll Theme Skeleton
author: Christian Külker
version: 0.1.2
date:   2020-04-21
type:   doc
description: Create a Example Skeleton and show how to use git sub-modules

---

> This document shows how to create an example [git] repository for a [Pankyll]
> theme with the example of the [Pankyll] [Newspaper] theme.

## Creating the Simplicissimus Skeleton

```shell
cd pankyll-theme-simplicissimus-example
git init

# pandoc
git submodule add -b master https://github.com/ckuelker/pankyll-pandoc pandoc
Cloning into '/home/c/g/github.com-ckuelker/pankyll-theme-simplicissimus-example/pandoc'...
remote: Enumerating objects: 14, done.
remote: Counting objects: 100% (14/14), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 14 (delta 1), reused 14 (delta 1), pack-reused 0
Unpacking objects: 100% (14/14), done.

git submodule init

# content
export URL=https://github.com/ckuelker/pankyll-documentation
git submodule add -b master $URL content
Cloning into '/home/c/g/github.com-ckuelker/pankyll-theme-simplicissimus-example/content'...
remote: Enumerating objects: 226, done.
remote: Counting objects: 100% (226/226), done.
remote: Compressing objects: 100% (152/152), done.
remote: Total 226 (delta 132), reused 159 (delta 65), pack-reused 0
Receiving objects: 100% (226/226), 52.46 KiB | 0 bytes/s, done.
Resolving deltas: 100% (132/132), done.

git submodule init

# theme
mkdir themes
export URL=https://github.com/ckuelker/pankyll-theme-simplicissimus
git submodule add -b master $URL themes/pankyll-theme-simplicissimus
Cloning into '/home/c/g/github.com-ckuelker/pankyll-theme-simplicissimus-example/themes/pankyll-theme-simplicissimus'...
remote: Enumerating objects: 28, done.
remote: Counting objects: 100% (28/28), done.
remote: Compressing objects: 100% (19/19), done.
remote: Total 28 (delta 3), reused 28 (delta 3), pack-reused 0
Unpacking objects: 100% (28/28), done.

git submodule init

mkdir static

```
Some files need to be created:

* cfg.yaml
* log.yaml

The `Makefile` is optional.

## Updating Git Sub-Modules

```bash
git submodule update --init --recursive
git submodule update --remote
# replace THEME with correct value
cd themes/pankyll-theme-THEME
git submodule update --init --recursive
git submodule update --remote
```

## External Links

**Guides On Git Sub-Modules**

* [Vogella Guide](https://www.vogella.com/tutorials/GitSubmodules/article.html)
* [git-scm Book](https://git-scm.com/book/en/v2/Git-Tools-Submodules)

## About This Document

### Changes

| Version | Date       | Author           | Notes                             |
| ------- | ---------- | ---------------- | --------------------------------- |
| 0.1.2   | 2020-04-21 | Christian Külker | add git output                    |
| 0.1.1   | 2020-04-09 | Christian Külker | add links                         |
| 0.1.0   | 2020-03-22 | Christian Külker | initial release                   |

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
[Rankle theme example]: /en_US/Example-Sites/pankyll-theme-rankle-example.html
[Rankle]: /en_US/Pankyll-Themes/pankyll-theme-rankle.html
[themes]: /en_US/Pankyll-Themes/
[URL]: https://en.wikipedia.org/wiki/URL
[YAML]: https://yaml.org/

