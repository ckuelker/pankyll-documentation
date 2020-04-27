---
title:  Creating A Pankyll Theme Skeleton
author: Christian Külker
version: 0.1.2
date:   2020-04-27
type:   doc
    - Pankyll Skeleton
tags:
    - Git
    - Pankyll
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
git submodule init

# content
export URL=https://github.com/ckuelker/pankyll-documentation
git submodule add -b master $URL content
git submodule init

# theme
mkdir themes
export URL=https://github.com/ckuelker/pankyll-theme-simplicissimus
git submodule add -b master $URL themes/pankyll-theme-simplicissimus
git submodule init

mkdir static

```

> Some files need to be created:

* cfg.yaml
* log.yaml

> The `Makefile` is optional.

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
| 0.1.3   | 2020-04-27 | Christian Külker | cleanup links, git output         |
| 0.1.2   | 2020-04-21 | Christian Külker | add git output                    |
| 0.1.1   | 2020-04-09 | Christian Külker | add links                         |
| 0.1.0   | 2020-03-22 | Christian Külker | initial release                   |

[Git]: https://de.wikipedia.org/wiki/Git
[Pankyll]: https://www.pankyll.org/de_DE/

