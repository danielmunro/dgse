---
title: "Class"
date: 2021-06-20T21:37:46-07:00
draft: false
tags:
  - language construct
short: Related to object-oriented programming.
resources:
    - { url: https://simple.wikipedia.org/wiki/Class_(programming), name: Wikipedia }
    - { url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes, name: MDN }
---

Related to [object-oriented programming](/glossary/object-oriented-programming). A class is a language construct that allows binding data to methods.

## Example

Here is an example class in Javascript:

```javascript
class LoggerWriter {
  constructor(textToLog) {
    this.textToLog = textToLog;
  }
  
  log() {
    console.log(this.textToLog);
  }
}
```

Here is another example class, this time with Python:

```python
class TrapezoidAreaCalculator:
    def __init__(self, base1, base2, height):
        self.base1 = base1
        self.base2 = base2
        self.height = height
    
    def getArea(self):
        return ((self.base1 + self.base2) * self.height) / 2
```
