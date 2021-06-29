---
title: "Dependency Inversion"
date: 2021-06-21T08:02:22-07:00
draft: false
tags:
    - SOLID
    - design principle
short: Classes should be provided their dependencies.
resources:
    - { url: https://en.wikipedia.org/wiki/Dependency_inversion_principle, name: Wikipedia }
---

[Classes](/glossary/class) should be provided their [dependencies](/glossary/dependency). Below is a trivial example of dependency inversion, using Kotlin:

```kotlin
class EmailService(private val emailClient: EmailClient) {
    fun sendEmail() {
        emailClient.send()
    }
}
```

This is compared to a system where class methods call external or global dependencies directly:

```kotlin
class EmailService {
    fun sendEmail() {
        EmailClient().send()
    }
}
```

There are a few benefits to dependency inversion. One primary benefit is that the class at hand is easier to test, because its dependencies can be mocked. Another benefit is that the calling code can substitute an `EmailClient` which is configured differently than the hard coded example. Finally, in terms of design, `EmailService` has fewer responsibilities using dependency inversion, which is always desirable.
