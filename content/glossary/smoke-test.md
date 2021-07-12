---
title: "Smoke Test"
date: 2021-07-11T04:35:21-07:00
draft: false
short: Simple set of manual tests that will quickly expose fatal errors.
tags:
    - concept
    - testing
resources:
    - { url: https://en.wikipedia.org/wiki/Smoke_testing_(software), name: Wikipedia }
---

Synonymous to [sanity test](/glossary/sanity-test). Also called build acceptance testing, the idea is to run a simple set of tests that will quickly expose any major fatal flaws. A smoke test is not meant to be exhaustive, for that typically [integration tests](/glossary/integration-test) are used, which are automated and much more likely to catch [regressions](/glossary/regression).
