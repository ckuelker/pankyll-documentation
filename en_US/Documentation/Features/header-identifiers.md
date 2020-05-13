---
title: Header Identifiers
type: doc
TOC: True
author: Christian Külker
date: 2020-04-26
keywords:
    - Header Identifiers Feature
categories:
    - Feature
features:
    - Header Identifier
tags:
    - Auto Identifiers
    - Headings And Sections
    - Pandoc
    - Pankyll
description: Default feature documentation

---

This feature derives from the power of [Pandoc] and is not a specific [Pankyll]
feature. The **header identifiers feature** allows a user to create links to
section inside the same document. The feature is described in detail in the
[Pandoc] manual under [Headings and sections] with the [auto_identifiers]
extension. Assuming there is a section `### MyTest`, then the author can
easily create a link by:

```markdown
[some text](#MyTest)
```

[Auto_identifiers]: https://pandoc.org/MANUAL.html#header-identifiers-in-html-latex-and-context
[Headings and sections]: https://pandoc.org/MANUAL.html#header-identifiers-in-html-latex-and-context
[Pandoc]: https://pandoc.org/
[Pankyll]: https://www.pankyll.org/
