---
title: Feature Overview
type: doc
TOC: True
date: 2021-05-18
list: True
categories:
    - Features
tags:
    - Create PDF
    - CSS Local
    - Default
    - Home
    - Include After
    - Include Before
    - JS Local
    - Imprint
    - Keywords
    - Localization
    - Navigation
    - Pankyll
    - Website
    - Table of contents
    - Top 10
    - Word Count
description: Pankyll feature overview

---

> This document gives an overview about the features of [Pankyll]

## List of Features

| Number | Feature                 | Notes                                 |
| -------| ----------------------- | ------------------------------------- |
| 0      | [Default]               | Default Values for website cfg.yaml   |
| 1      | [Website]               | Website wide configuration cfg.yaml   |
| 2      | Internationalization    | Prepare Pankyll for [localization]    |
| 3      | [Imprint]               | URL + text for imprint page           |
| 4      | [Home]                  | URL + text for website root link      |
| 5      | [Navigation]            | URL + text for navigation bar         |
| 6      | Table of contents [TOC] | Text for Table of contents title      |
| 7      | [Keywords]              | Types of keywords (tags, ...)         |
| 8      | More Menu               | URL + text for a menu called More     |
| 9      | Website Description     | description for Home feature          |
| 10     | Footer                  | URL, text + position footer links     |
| 11     | Default Frontmatter     | Default Values for front matter       |
| 12     | [Include Before]        | Include text from cfg.yaml into doc   |
| 13     | [Include After]         | Include text from cfg.yaml into doc   |
| 14     | [Word Count]            | Count word approx. from Markdown      |
| 15     | [CSS Local]             | Copy CSS to local website             |
| 16     | [JS Local]              | Copy Javascript to local website      |
| 17     | [Create PDF]            | Crate PDF via Pandoc                  |
| 18     | [Top 10]                | Link list to 10 latest pages          |
| 19     |                         |                                       |

## Feature Scopes

| Feature                 | cfg.yaml           | Front Matter | Mandatory |
|------------------------ | ------------------ | ------------ | --------- |
| Website                 | site:              |              | yes       |
| Localization (l10n)     | l10n:, languages:  |              | yes       |
| Imprint                 | imprint:           |              | no        |
| Website Title           | site.title:        |              |           |
| Page Title              |                    | title:       |           |
| Home                    | home:              |              | no        |
| Table Of Contents       | toc:               |              |           |
| Keywords                | keywords:, ...[1]  | ...[1]       | no        |
| Navigation              | navigation:        |              | no        |
| More                    | more:              |              |           |
| Website Description     | description:       |              |           |
| Page Description        |                    | description: | no        |
| Footer                  | footer:            |              |           |
| Type                    | type:              | type:        | yes       |
| Author                  |                    | author:      | no        |
| Date                    |                    | date:        | no        |
| Version                 |                    | version:     | no        |
| Default Frontmatter     | frontmatter:       | ALL          | empty     |
| Include Before          | site:              |              | no        |
| Include After           | site:              |              | no        |
| Word Count              |                    |              | no        |
| CSS Local               |                    |              | no        |
| JS Local                |                    |              | no        |
| Top 10                  | default:           | top10:       | no        |
| Create PDF              | default:           |              | no        |
|                         |                    |              |           |

ALL: all keys can be used

empty: key has to be in cfg.yaml, but can be empty

> [1] Valid keys are defined via 'keywords:' in `cfg.yaml`.

[Create PDF]: /en_US/Documentation/Features/create-pdf.html
[CSS Local]: /en_US/Documentation/Features/css-local.html
[Default]: /en_US/Documentation/Features/default.html
[Home]: /en_US/Documentation/Features/home.html
[Imprint]: /en_US/Documentation/Features/imprint.html
[Include Before]: /en_US/Documentation/Features/body-include-before.html
[Include After]: /en_US/Documentation/Features/body-include-after.html
[JS Local]: /en_US/Documentation/Features/js-local.html
[Keywords]: /en_US/Documentation/Features/keywords.html
[Localization]: /en_US/Documentation/Features/localization.html
[Navigation]: /en_US/Documentation/Features/navigation.html
[Pankyll]: https://www.pankyll.org/
[Website]: /en_US/Documentation/Features/global-site-parameters.html
[TOC]: /en_US/Documentation/Features/toc.html
[Top 10]: /en_US/Documentation/Features/top10.html
[Word Count]: /en_US/Documentation/Features/word-count.html


