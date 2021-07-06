---
title: "Higher Order Function"
date: 2021-07-02T19:55:31-07:00
draft: false
tags:
    - concept
short: A function that operates on functions.
resources:
    - { url: https://eloquentjavascript.net/05_higher_order.html, name: "Eloquent Javascript: Higher Order Functions" }
    - { url: https://medium.com/javascript-scene/higher-order-functions-composing-software-5365cf2cbe99, name: "Eric Elliott: Higher Order Functions (Composing Software)" }
    - { url: https://en.wikipedia.org/wiki/Higher-order_function, name: Wikipedia }
---

A [function](/glossary/function) that operates on functions, either by taking one as an argument or by returning one.

[React hooks](https://reactjs.org/docs/hooks-intro.html) are examples of higher order functions:

```javascript

useEffect(() => {
  const timeout = setTimeout(() => alert('Hello!'), 1000);
  
  return () => {
    clearTimeout(timeout);
  };
}, []);

```

Other examples include map, reduce, and filter:

```javascript
collection.map((item) => ... );

collection.reduce((item) => ... );

collection.filter((item) => ... );
```
