---
title: "Recursion"
date: 2021-06-30T21:23:54-07:00
draft: false
short: A function that calls itself, typically with a guard condition that prevents infinite execution.
tags:
    - computer science
    - concept
resources:
    - { url: "https://en.wikipedia.org/wiki/Recursion_(computer_science)", name: "Wikipedia" }
---

A function that calls itself, typically with a guard condition that prevents infinite execution.

Below is an example of a recursive function in javascript (a common factorial example):

```javascript

const factorial = (n) => {
  if (n == 1) {
    return 1;
  }
  return n * factorial(n - 1);
};

factorial(4); // == 24

```
