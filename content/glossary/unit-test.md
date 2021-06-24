---
title: "Unit Test"
date: 2021-06-22T20:38:19-07:00
draft: false
tags:
    - concept
    - testing
---

A test that exercises the smallest unit of publicly exposed code. 

"Smallest unit of publicly exposed code" depends on a few factors. For a [library](/glossary/library), this could be a public method in the library. For a [REST API](/glossary/rest), the unit in question is (or at least should be) a REST call.

## Why Not Lower Level Testing?

The reason why testing does not occur below this level (the "unit"), is because of subtle issues that cascade problems later on. When digging deeper into code for testing purposes, it becomes easy to start testing implementation, rather than the feature itself.

When this happens, any subsequent change in implementation will require refactoring unit tests. This is a [smell](/glossary/smell). The most well-written unit tests allow the implementation to change without breaking the test.
