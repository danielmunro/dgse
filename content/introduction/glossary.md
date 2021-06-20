---
title: "Glossary"
date: 2021-06-16T08:09:15-07:00
weight: 2
draft: false
---

The purpose of this document is to help to demystify the world of software engineering. Unfortunately, ours is a profession ripe with terms that are assumed to be understood. This adhoc system of knowledge, while flexible and sufficient for experienced practitioners, is obtuse to newcomers. Overall, it is the author's opinion that this opaque nature of software engineering holds the field back -- indeed significantly -- in a number of important ways.

Without clarity, precision, and shared understanding of language, the field of software engineering is limited to those who can decipher the language and culture around it.

### Existing Resources

There are volumes of books that exist to address this problem. However, there are still scare open source, high quality references.

This site aims to be open source forever, for the benefit of the field of software engineering.

## Abstraction

1. The concept of a software component, not the component itself. Contrast the two example sentences below:
   
Example 1:
 > This *writer abstraction* is flexible and backend-agnostic.

Example 2:
 > This *file system writer implementation* is flexible, but backend-specific.

The first example does not mention _what_ kind of writer the speaker is referencing. The second example, by contrast, references a specific implementation (the filesystem writer).

## Adapter Design Pattern

1. [Design pattern](#design-pattern). Attempts to solve questions like, "how do we get incompatible interfaces to work together?" To solve this problem, a layer is introduced between the interfaces ("the adapter"), which mediates incompatibilities.

1. Article. [Adapter Pattern](https://en.wikipedia.org/wiki/Adapter_pattern).

## Algorithm

1. Definition. A reusable set of instructions.

## API

1. Acronym. Application programming interface.

1. Concept. Something that provides functionality, which can be programmed against.

1. A [library](#library), module, or service that can be integrated into code.

## Bug

1. Definition. Loosely defined as a problem in code, which could be any of the following:

* A logic flaw
* A syntax or runtime error
* A memory leak
* A race condition
* A previously overlooked flaw

## Builder Design Pattern

1. [Design pattern](#design-pattern). A class, module, or other language construct for specifying how to configure and build an object before the actual object instantiation.

## Class

1. Related to object-oriented programming. A class is a language construct that allows binding data to methods.

## Cloud

1. Someone else's computer.

1. Platform. Virtualized services, used to build products and services on top of.

## CI/CD

1. Acronym. [Continuous integration](#continuous-integration) / [continuous delivery](#continuous-delivery).

1. Definition. A build and deploy system.

## Compiled Language

1. Type of programming language. Contrast to a [dynamic language](#dynamic-language). Compiled languages are identified by the fact that the code instructions are compiled into machine-readable code prior to runtime.

## Container

1. Definition. A lightweight runtime environment. Encapsulates dependencies from host environment.

1. Definition. A filesystem and a process.

1. Article. [Containers 101](https://cloud.google.com/containers).

## Continuous Integration

1. Concept. Developer workflow, involves running a suite of tests against all commits that are pushed to version control. The primary benefit here is in using tests to catch regressions as early as possible.

## Continuous Delivery

1. Concept. Developer workflow automation. The essential feature of continuous delivery is that every commit that passes its [integration](#continuous-integration) step, automatically gets deployed further to a target environment.
    
    Typically, a target environment is a test or integration environment, before final deployment out to production.

## Dependency

1. Concept. A function, class, [library](#library), module, or other logical section of code, which is external to the code under active development.

2. Concept. A service or third party API, which your code depends on to work correctly.

## Dependency Inversion

1. [SOLID](#solid) design principle. States that classes should be provided [dependencies](#dependency). This is compared to a system where class methods call external or global dependencies directly.

## Design Pattern

1. A commonly-agreed upon solution to problem that has arisen before.

1. Classifying code design challenges in ways that existing ideas can be implemented in order to solve. 

## DevOps

1. TBD

## Dynamic Language

1. Type of programming language. Contrast to a [compiled language](#compiled-language). Dynamic languages are identified by the fact that the code instructions are interpreted at runtime. The interpreter is a layer of software that runs in between a machine and the code instructions. Because of this additional layer, dynamic languages tend to be slower than compiled ones.

## Facade

1. [Design pattern](#design-pattern). An interface or class used to hide the system's underlying complexity.

## Factory

1. [Design pattern](#design-pattern). A function or class, whose primary responsibility is creating instances of another class.

## Functional Programming

1. Programming paradigm. Programs are designed using a composition of functions, which operate on data.

## IDE

1. Acronym. Integrated development environment.

1. Software. For use by programmers. Includes a combination of tools such as a text editor and language compiler. Often highly extensible and customizable.

## Integration Test

1. TBD

## Interface Segregation Principle

1. [SOLID](#solid) design principle. States that interfaces should remain small and focused. Interface implementations are then lightweight, and easy to create and maintain. Code that depends on interfaces that are small and focused in turn keep a smaller scope of responsibility.

## Library

1. Someone else's code.

1. Code that is packaged and maintained externally to the code under development.

## Liskov Substitution Principle

1. [SOLID](#solid) design principle. Relating to [types](#type). States essentially that if _X_ is a subtype of _Y_, then _X_ may be used in substitution of _Y_ without concern for correctness or task performed. 

## Method

1. A function that has been bound to a class instance. Example:

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

## Multiton

1. [Design pattern](#design-pattern). A class, module, or function that is used to handle creating or returning objects. Multitons can take parameters, and invocation is idempotent.

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

## Object-Oriented Programming

1. Programming paradigm. Language-level support for binding data to methods.

## Observer Design Pattern

1. [Design pattern](#design-pattern). Attempts to remove a hard coupling between software components. Instead of calling a function directly, which creates a hard coupling between the calling function and the callee, the pattern calls for a mediator to dispatch updates between components. Using the mediator, the calling function and the callee can avoid knowing anything about each other.  

## Open/Closed Principle

1. [SOLID](#solid) design principle. The concept states that classes should be open for extension but closed for modification.

## Open Source

1. Software licensing scheme. While each license has its own terms, the primary defining characteristic of open source licensing is that the software is free to use and inspect. Many license types exist. Well known examples include [GPL](https://en.wikipedia.org/wiki/GNU_General_Public_License), [MIT](https://opensource.org/licenses/MIT), [BSD](https://en.wikipedia.org/wiki/BSD_licenses).

## Regression

1. Definition. A code change that breaks a previously working feature.

## Sanity Check

1. Concept. Perform a check on a system. The result should immediately and unambiguously show whether the system is operating under rational expectations. A negative result would indicate the system under test is experiencing logic bugs, which make the system unusable.

## Single Responsibility Principle

1. [SOLID](#solid) design principle. A logical section of code (function, class, module), should only ever have one reason to change.

## Singleton

1. Design pattern. Software component that allows for creating a single instance of an object. Subsequent requests return the same object.

## Smoke Test

1. TBD

## SOLID

1. Programming design principles. Acronym. Stands for:

 * Single Responsibility Principle [[entry](#single-responsibility-principle)]
 * Open/Closed Principle [[entry](#openclosed-principle)]
 * Liskov Substitution Principle [[entry](#liskov-substitution-principle)]
 * Interface Segregation Principle [[entry](#interface-segregation-principle)]
 * Dependency Inversion [[entry](#dependency-inversion)]

## State Machine Design Pattern

1. Design pattern.

## Strategy Design Pattern

1. Design pattern.

## Stream

1. Concept. A flow of data from a source to one or more destinations.

## Terminal

1. Software. A program, allows interacting with computer via a command line interface (CLI).

## Test Driven Development

1. Software development methodology. Outlines a series of practices during software development that aim to focus the process and improve overall quality of the code. Behaviors consist primarily of:

 * Write a test before writing any code
 * Observe the test fail
 * Implement the minimum changes to allow the test to pass
 * Observe the test passing
 * Refactor to improve the existing code
 * Repeat

## Turing Complete

1. Criteria for a logic system. Any logic system that includes the functionality for conditionals and loops is considered Turing complete. Most (but not all) programming languages are TC.

## Type

1. TBD

## Unit Test

1. Concept. A test that exercises the smallest unit of publicly exposed code (ie a public function or API call). 

## Virtual Machine

1. A set of system components, providing an isolated OS environment (a "guest OS") on top of the host OS environment.

## Version Control System (VCS)

1. Development tool. Used to track code changes. Modern and recent examples include: [git](https://git-scm.com/), [mercurial](https://www.mercurial-scm.org/), and [subversion](https://subversion.apache.org/) to name a few.
