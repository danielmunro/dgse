---
title: "Interface"
date: 2021-07-05T11:00:57-07:00
draft: false
resources:
    - { url: https://en.wikipedia.org/wiki/Interface_(computing), name: Wikipedia }
---

An [abstraction](/glossary/abstraction). Used when there are interchangeable [classes](/glossary/class) that provide similar functionality to the calling code. 

Let's start with a simple interface:

```kotlin
interface Logger {
    fun writeBuffer(data: String)
}
```

And use the example below:

```kotlin
fun handleLoopUpdate(updates: List<Update>, logger: Logger) {
    updates.forEach { update ->
        logger.writeBuffer(update.summary)
    }   
}
```

With the two code samples above, the below hypothetical writers are possible:

```kotlin
handleLoopUpdates(DebugPrintLogger())
```

```kotlin
handleLoopUpdates(LocalFileLogger())
```

```kotlin
handleLoopUpdates(RemoteServiceLogger())
```

```kotlin
handleLoopUpdates(OhShitLogger())
```

Note how `handleLoopUpdates` does not know or care what kind of logger it receives. The only thing `handleLoopUpdates` knows about is the `Logger` interface, and what the interface defines.
