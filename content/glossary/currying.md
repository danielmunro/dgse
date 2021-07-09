---
title: "Currying"
date: 2021-07-08T00:55:07-07:00
draft: false
resources:
    - { url: https://stackoverflow.com/questions/36314/what-is-currying, name: "Stack Overflow" }
    - { url: https://en.wikipedia.org/wiki/Currying, name: "Wikipedia" }
tags:
    - concept
    - functional programming
short: Function currying is a functional design process.
---

Function currying is a functional design process. A [function](/glossary/function) that takes multiple arguments are refactored into a function that takes a single argument. For example:

```javascript
function add(a, b, c) {
  return a + b + c;
}

add(1, 2, 3); // equals 6
```

becomes:

```javascript
function add(a) {
  return function(b) {
    return a + b;
  }
}

add(add(1)(2))(3) // equals 6
```
