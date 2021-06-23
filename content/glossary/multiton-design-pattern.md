---
title: "Multiton Design Pattern"
date: 2021-06-22T20:30:55-07:00
draft: false
---

[Design pattern](#design-pattern). A class, module, or function that is used to handle creating or returning objects. Multitons can take parameters, and invocation is idempotent.

Example:

```
multiton = (a) => {
    if (a == 1) {
        return Class1()
    }
    if (a == 2) {
        return Class2()
    }
    return Class3()
}

multiton(1) // Class1
multiton(2) // Class2
multiton(3) // Class3
```

