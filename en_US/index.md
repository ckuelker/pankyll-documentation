---
title: Pankyll Documentation and Themes
author: Christian Külker
date: 2020-04-09
type: title
keywords:
  - Pankyll
  - Pankyll Documentation
  - Pankyll Themes
categories:
  - documentation
tags:
  - Pankyll
  - Pankyll themes
  - Pankyll themes examples
description: Site providing Pankyll documentation and collecting themes

---

[Pankyll] is is a static [HTML] site generator written in [Python] using
[Pandoc] to generate easy to deploy [HTML] sites including [PDF] conversion.
This site provides user documentation about installing and using the static
site generator [Pankyll] for your site and it collects unique layouts, called
themes, that you can use. The latest version of the documentation can be found
at the [Pankyll] web page and it can be cloned via the git repository
[pankyll-documentation]. If you have written a [Pankyll] theme and would like
to share it with the world and be promoted via this page, consider to fork the
repository and make a pull request.

## Pankyll

[Pankyll] is a small [Python] program that iterates a given content directory
and converts all [Markdown] files to [HTML]. It also converts some documents to
[PDF] and adds a download link. Further more it collects all table of contents
and provide them if the theme needs them. It also calculates all [git] commit
information and provide links to the original repository. With the capability
of theming the content the output and design can be very innovative and
flexible. All this can be paired with the localization (the translation) of the
theme as well as the content. [more about Pankyll]

## The Latest Themes

[Pankyll] supports [themes]. Themes are custom layout that displays the
given content data without altering the content. Some web sites focus on
documentation, while other are news or blog posts. Each goal require its
own layout. With [Pankyll] [themes] it is possible the display the content
in a flexible and innovative way.

* [Rankle]
* [Newspaper]

## The Latest Theme Examples

A guide to install a theme is straight forward and is provided by most
[themes].  However a different approach is to install [Pankyll] and a theme
example that is fully configured and comes with an example content. In most
cases it is easier to just clone everything, delete the unwanted parts and
replace the example content with once own content, run the command `pankyll`
and publish the static content.

Technically speaking, a theme example is basically a file skeleton with [git]
sub-modules, already with [Pandoc] filters, [Pandoc] templates, a theme,
example content, a `Makefile` for easy task repetition and a configuration
`cfg.yaml` in form of a [YAML] file.

* [Rankle theme example]
* [Newspaper theme example]

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
[Rankle theme example]: /en_US/Pankyll-Theme-Examples/pankyll-theme-rankle-example.html
[Rankle]: /en_US/Pankyll-Themes/pankyll-theme-rankle.html
[themes]: /en_US/Pankyll-Themes/
[URL]: https://en.wikipedia.org/wiki/URL
[YAML]: https://yaml.org/

