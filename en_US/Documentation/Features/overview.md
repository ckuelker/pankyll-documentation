---
title: Feature Overview
type: doc
date: 2020-04-26
list: True
categories:
    - Features
tags:
    - Default
    - Home
    - Imprint
    - Keywords
    - Localization
    - Navigation
    - Pankyll
    - Site
    - Table of contents
description: Pankyll feature overview

---

> This document gives an overview about the features of [Pankyll]

## List of Features

| Number | Feature                 | Notes                                 |
| -------| ----------------------- | ------------------------------------- |
| 0      | [Default]               | Default Values for site cfg.yaml      |
| 1      | [Site]                  | Site wide configuration in cfg.yaml   |
| 2      | Internationalization    | Prepare Pankyll for [localization]    |
| 3      | [Imprint]               | URL + text for imprint page           |
| 4      | [Home]                  | URL + text for site root link         |
| 5      | [Navigation]            | URL + text for navigation bar         |
| 6      | Table of contents [TOC] | Text for Table of contents title      |
| 7      | [Keywords]              | Types of keywords (tags, ...)         |
| 8      | More Menu               | URL + text for a menu called More     |
| 9      | Site Description        | description for Home feature          |
| 10     | Footer                  | URL, text + position footer links     |

## Feature Scopes

| Feature                 | cfg.yaml           | Front Matter | Mandatory |
|------------------------ | ------------------ | ------------ | --------- |
| Site                    | site:              |              | yes       |
| Localization (l10n)     | l10n:, languages:  |              | yes       |
| Imprint                 | imprint:           |              | no        |
| Site Title              | site.title:        |              |           |
| Page Title              |                    | title:       |           |
| Home                    | home:              |              | no        |
| Table Of Contents       | toc:               |              |           |
| Keywords                | keywords:, ...[1]  | ...[1]       | no        |
| Navigation              | navigation:        |              | no        |
| More                    | more:              |              |           |
| Site Description        | description:       |              |           |
| Page Description        |                    | description: | no        |
| Footer                  | footer:            |              |           |
| Type                    | type:              | type:        | yes       |
| Author                  |                    | author:      | no        |
| Date                    |                    | date:        | no        |
| Version                 |                    | version:     | no        |
|                         |                    |              |           |

> [1] Valid keys are defined via 'keywords:' in `cfg.yaml`.

[Default]: /en_US/Documentation/Features/default.html
[Home]: /en_US/Documentation/Features/home.html
[Imprint]: /en_US/Documentation/Features/imprint-feature.html
[Keywords]: /en_US/Documentation/Features/keywords.html
[Localization]: /en_US/Documentation/Features/localization.html
[Navigation]: /en_US/Documentation/Features/navigation.html
[Pankyll]: https://www.pankyll.org/
[Site]: /en_US/Documentation/Features/site.html
[TOC]: /en_US/Documentation/Features/toc.html

