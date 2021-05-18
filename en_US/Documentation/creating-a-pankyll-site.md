---
title: Creating A Pankyll Website
type: doc
TOC: True
author: Christian Külker
date: 2020-04-30
keywords:
    - Pankyll Website
Categories:
    - Documentation
Tags:
    - Creating A Website
    - Example
    - Getting started
    - Pankyll
    - Rankle
    - Theme
    - YAML
description: Creating a Pankyll website from scratch

---

The easiest way to create a website is to use an [example] repository to kick
start the website. See the [getting started] page for details. However, this
document describes in more detail how to kick start a [Pankyll] website from
scratch. For this to work it is assumed that [Pankyll] is installed.  Choose a
website name, for example '**mysite**'. We assume you use the [Rankle] [theme].

```shell
mkdir mysite
cd mysite
git init
mkdir -p content/en_US static themes

# add the Pandoc filters
export URL=https://github.com/ckuelker/pankyll-pandoc.git
git submodule add -b master $URL pandoc
git submodule init

# add the theme
export URL=https://github.com/ckuelker/pankyll-theme-rankle.git
git submodule add -b master $URL themes/pankyll-theme-rankle
git submodule init

# update the submodules of the submodules
git submodule update --remote
git submodule update --init --recursive
```

> Copy over the `log.yaml` from one of the theme example repositories.

```shell
export HOST=raw.githubusercontent.com
wget https://$HOST/ckuelker/pankyll-theme-rankle-example/master/log.yaml
```
> To kick start the configuration copy over the `cfg.yaml` and change it.

```shell
wget https://$HOST/ckuelker/pankyll-theme-rankle-example/master/cfg.yaml
```

> Change the configuration to match you website. The following is somewhat a
> minimal example for the [Rankle] theme.

```yaml
# 0: default values
default:
    page_type:         doc
    keyword_page_type: keyword
    index_list_type:   list
    l10n_locale:       en_US   # Feature 2: Localization
    pdf_create:        True

# 1. Global website parameters
site:
  url:         /                     # URL prefix - mandatory (trailing slash)
  title:       My Site               # string     - mandatory (fallback)
  content_dir: content               # directory  - mandatory
  public_dir:  public                # directory  - mandatory
  themes_dir:  themes                # directory  - mandatory
  theme_name:  pankyll-theme-rankle  # directory  - mandatory

# 2. Feature: Internationalization
locales:
      en_US: English

# 4. Feature: Home
home:
    en_US:
        text: Pankyll  # home_text
        url:  en_US    # home_url

# 5. Feature: Navigation
navigation:
    en_US:
        - link:
            text: Documentation
            url:  en_US/

# 6. Feature: Table Of Contents
toc:
    en_US:
        text: Table Of Contents # alternative: Contents

# 7. Feature: Keywords
keywords:
    - categories
    - tags

categories:
    en_US:
        text: Categories
        url:  en_US/Categories/

tags:
    en_US:
        text: Tags
        url:  en_US/Tags/

# 8. Feature: More-Menu (not used by newspaper theme)
more:
    en_US:
        - link:
            text: Categories
            url:  en_US/Categories/
        - link:
            text: Tags
            url:  en_US/Tags/

# 9.  Feature: Website Description
description:
    en_US:
        text: My Site

# 10. Feature: Footer
footer_left:
    en_US:
        1:
            tip: Mailing List
            font: fa # font awesome solid
            icon: envelope
            url:  https://example.org/mail
footer_middle:
    en_US:
        1:
            tip:  Pankyll
            font: fab
            icon: python
            url:  https://github.com/ckuelker/pankyll
footer_right:
    en_US:
        1:
            tip: Git Home # Rankle: tooltips
            font: fab
            icon: github
            url:  https://github.com/ckuelker/pankyll-theme-rankle-example
footer:
    en_US:
        - text: © 2020 by Me, All Rights Reserved
```

> The first page should go into the content directory:
> `content/en_US/index.md`.  Make sure the highest heading level is 2 (aka 2
> ##).

```markdown
---
title: Welcome to My Website
type: title
keywords:
  - My Site
categories:
  - My Site
tags:
  - Welcome
description: My new website

---

Welcome to my new website.

## Important Information
...
```

The [YAML] front matter is needed to define the default type of the page. In
this case it is `type: title`. The rest is optional. To create the website
run the `pankyll` command inside the project directory.

```shell
...
Command line starting Pankyll v0.1.0
Pankyll v0.1.0

Objects                        | Count
-------------------------------|------------
Markdown source files total    | 1
Markdown source files existing | 1
Markdown source files new      | 0
Markdown files total           | 3
Markdown files existing        | 3
Markdown files new             | 2
Pandoc WARNINGS                | 5
PDF                            | 5
PDF skipped                    | 0
PDF processed                  | 0
PDF excluded (index)           | 5
HTML                           | 5
HTML processed                 | 5
HTML skipped                   | 0
Content git repositories       | 0
```

The result inside the `public` directory should be copied to the web server.
Usually the web server needs to be configured to server the file from the
directory `en_US`. If you want to test it locally you should copy in an [HTML]
file that redirects to the default language root. You can use the following
command to fire up a local development web server.

```shell
export HOST=raw.githubusercontent.com
export REPO=pankyll-theme-rankle-example
cd public
wget https://$HOST/ckuelker/$REPO/master/static/index.html
python3 -m http.server 8000
```
[Example]: /en_US/Example-Sites
[Getting started]: /en_US/Documentation/getting-started.html
[HTML]: https://en.wikipedia.org/wiki/HTML
[Pankyll]: https://www.pankyll.org/
[Rankle]: /en_US/Pankyll-Themes/pankyll-theme-rankle.html
[Theme]: /en_US/Pankyll-Themes/
[YAML]: https://yaml.org/
