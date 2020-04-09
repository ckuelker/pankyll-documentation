---
title:  Creating A Pankyll Theme Skeleton
author: Christian Külker
version: 0.1.0
date:   2020-03-22
type:   doc
description: Show howto use git to handle submodules

---

> This document shows how to create an example git repository for a `Pankyll`
> theme with the example of the `Pankyll` newspaper theme.

## Creating Git Submodules

```bash
mkdir project-example
cd project-example
git init
# Add pandoc filters and templates
git submodule add -b master https://github.com/ckuelker/pankyll-pandoc pandoc
git submodule init

# Add content
export URL=https://github.com/ckuelker/pankyll-example-content
git submodule add -b master $URL content
git submodule init

# Add a theme
mkdir themes
export URL=https://github.com/ckuelker/pankyll-theme-newspaper.git
git submodule add -b master $URL themes/pankyll-theme-newspaper
git submodule init
```

## Updating Git Submodules

```bash
git submodule update --init --recursive
git submodule update --remote
# replace THEME with correct value
cd themes/pankyll-theme-THEME
git submodule update --init --recursive
git submodule update --remote
```

## External Links

**Guides On Git Submodules**

* [Vogella Guide](https://www.vogella.com/tutorials/GitSubmodules/article.html)
* [git-scm Book](https://git-scm.com/book/en/v2/Git-Tools-Submodules)

## About This Document

### Changes

| Version | Date       | Author           | Notes                             |
| ------- | ---------- | ---------------- | --------------------------------- |
| 0.1.0   | 2020-03-22 | Christian Külker | initial release                   |

