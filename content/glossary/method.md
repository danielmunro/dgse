---
title: "Method"
date: 2021-06-22T20:30:16-07:00
draft: false
tags:
    - language construct
    - oop
    - language design
short: A function that has been bound to a class instance.
---

A [function](/glossary/function) that has been bound to a class instance. Example:

Calling a function:

```
myFunction() // function
```

Calling a method:

```
class MyClass {
    fun myFunction() {}
}

instance = new MyClass()

instance.myFunction()
```

