---
linkTitle: Pankyll Installation
title: Pankyll Installation
type: doc
author: Christian Külker
date: 2020-04-18
keywords:
    - Pankyll
    - Pankull Installation
categories:
    - Pankyll
    - Pankyll Installation
tags:
    - Debian 10 Buster
    - Jinja2
    - YAML
    - Pandoc

---

## Pankyll Installation

### Prerequisites

Under Debian 10 (Buster):

```bash
aptitude install python3-yaml python3-jinja2 pandoc
```

To use the PDF feature also some fonts are needed:

```shell
aptitune install fonts-noto-cjk fonts-wqy-microhei
```

### Installing from Git Repository

```bash
cd $HOME
git clone https://github.com/ckuelker/pankyll.git
export PATH=$HOME/pankyll/bin:$PATH
```
