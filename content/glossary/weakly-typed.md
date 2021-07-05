---
title: "Weakly Typed"
date: 2021-06-23T21:38:04-07:00
draft: false
tags:
    - types
    - language design
short: Method of type enforcement at a language level.
resources:
    - { url: "https://archive.org/details/wat_destroyallsoftware", name: WAT }
---

Method of type enforcement at a language level. Specifically, weakly typed languages have few or no restrictions when performing operations on values of different types.

This does not mean results of operations with mixed types are rational, expected, or reasonable. Often, this flexibility is actually the source of pernicious and difficult to debug issues.

Compare to [strongly typed](/glossary/strongly-typed) languages.
