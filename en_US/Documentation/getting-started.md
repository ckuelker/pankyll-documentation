---
title: Getting Started
type: doc
author: Christian Külker
date: 2020-04-25
toc: True
keywords:
    - Pankyll
    - Pankyll Installation
categories:
    - Pankyll
    - Pankyll Installation
tags:
    - Debian 10 Buster
    - Example
    - Jinja2
    - Newspaper
    - Pandoc
    - Pankyll
    - Rankle
    - Simplicissimus
    - YAML
description: Pankyll installation on Debian via git and package manager

---

To create your first web site with [Pankyll] this guide uses two steps. The
first step is to install [Pankyll] and the second step is to use an [example]
site to kick start your site.

## Installing Pankyll

Install the [Pankyll] dependencies, like [YAML], [Jinja2], [Pandoc] and some
fonts. Depending on your system the procedure might be different. The following
instruction is for [Debian 10 Buster].

```shell
aptitude install pandoc python3-yaml python3-jinja2 fonts-noto-cjk \
fonts-wqy-microhei
```

This is the quick guide version on how to "install" and use the command line tool
of [Pankyll]. Under Linux just clone the git repository.

```shell
cd
git clone https://github.com/ckuelker/pankyll.git
```

The script `pankyll` is inside the `bin` directory. So the easiest it to
change your `PATH` lets assume you would like to use it from your home
directory.

```shell
cd
export PATH=$HOME/panlyll/bin:$PATH
```

Now when you enter `pankyll` inside the terminal it should find and execute the
`pankyll` command.

## Install An Example

To use the example easily the `make` can be used. In case it is not installed,
it can be installed on [Debian 10 Buster] like this.

```shell
aptitude install make
```

Of course you can now create your new site from scratch. However the
explanation would be quite long. For your first site it is recommended to use a
theme example. Chose one repository from the theme [example] page and clone
this repository. In the example below replace `NAME` with the name of the
example theme. For example [newspaper], [rankle] or [simplicissimus].

```shell
cd
git clone https://github.com/ckuelker/pankyll-theme-NAME-example.git
```

To test if your setup is OK either enter the example directory and execute
the `pankyll` command or execute `make build`. To see the result with your
browser you can use `make server`.

[Debian 10 Buster]: https://www.debian.org/releases/buster/
[Example]: /en_US/Example-Sites
[Jinja2]: https://palletsprojects.com/p/jinja/
[Newspaper]: /en_US/Pankyll-Themes/pankyll-theme-newspaper.html
[Pandoc]: https://pandoc.org/
[Pankyll]: https://www.pankyll.org/
[Rankle]: /en_US/Pankyll-Themes/pankyll-theme-rankle.html
[Simplicissimus]: /en_US/Pankyll-Themes/pankyll-theme-simplicissimus.html
[YAML]: https://yaml.org/

