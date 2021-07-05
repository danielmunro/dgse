---
title: "Function"
date: 2021-06-23T16:19:05-07:00
draft: false
tags:
  - language construct
  - language design
short: A series of instructions that are grouped and callable by a name.
resources:
    - { url: https://www.cs.utah.edu/~germain/PPS/Topics/functions.html, name: "Jim's computer science topics: functions" }
---

A series of instructions that are grouped and callable by a name. The primary components of a function are its:

* name
* parameter(s)
* return value

These three things together are called a function's _signature_.

## Example

Below is an example Javascript function that adds two numbers:

```javascript
function addValues(a, b) {
    return a + b;
}
```

Here is an example Kotlin function that finds the smallest value in a list:

```kotlin
fun smallestValue(value: List<Int>): Int {
    var smallest = value.first()
    value.forEach {
        if (it < smallest) {
            smallest = it
        }
    }
    return smallest
}
```

## A Note on Go

Go, the programming language created by Google, permits multiple return values.
