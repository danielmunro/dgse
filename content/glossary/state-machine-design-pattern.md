---
title: "State Machine Design Pattern"
date: 2021-07-08T12:36:03-07:00
draft: false
resources:
    - { url: https://refactoring.guru/design-patterns/state, name: "Refactoring Guru" }
    - { url: https://en.wikipedia.org/wiki/State_pattern, name: Wikipedia }
    - { url: https://sourcemaking.com/design_patterns/state, name: "Source Making" }
tags:
    - design pattern
short: A design pattern regarding application states and transitions.
---

A [design pattern](/glossary/design-pattern) with a few conceptual aspects:

* The total number of states a system can be in are finite, and enumerable.
* State transitions are limited to predefined rules.
* The state of a system can be determined by an object's properties.

Consider the following state machine concept in Kotlin: a payment processing system.

First, let's define some statuses for the state machine:
```kotlin
enum Status {
    Requested,
    Processing,
    Approved,
    Declined,
    Error,
    Completed,
}
```

Second, we define a payment object:
```kotlin
class PaymentRequest(private val card: Card) {
    private var status: Status = Status.Requested
    
    fun getStatus(): Status {
        return status
    }
}
```

Third, we define an interface for different states:
```kotlin
interface PaymentProcessingState {
    fun process(paymentRequest: PaymentRequest): Status
}
```

And implementations for each state:
```kotlin
class RequestedPaymentProcessingState(private val userService: UserService) : PaymentProcessingState {
    fun process(paymentRequest: PaymentRequest): Status {
        if (!userService.userLoggedIn(paymentRequest)) {
            return Status.Error
        }
        ..
    }
}

class ProcessingPaymentProcessingState(private val paymentGateway: PaymentGateway) : PaymentProcessingState {
    fun process(paymentRequest: PaymentRequest): Status {
        try  {
            paymentGateway.charge(paymentRequest)
            return Status.Approved
        } catch (e: ChargeFailureException) {
            return Status.Declined
        }
    }
}

class ApprovedPaymentProcessingState : PaymentProcessingState {
    fun process(paymentRequest: PaymentRequest): Status {
        // mark a database record as approved
        return Status.Completed
    }
}

class DeclinedPaymentProcessingState : PaymentProcessingState {
    fun process(paymentRequest: PaymentRequest): Status {
        // mark a database record as declined
        ..
        // evaluate retry logic
        ..
        return Status.Completed
    }
}

class ErrorPaymentProcessingState : PaymentProcessingState {
    fun process(paymentRequest: PaymentRequest): Status {
        // mark a database record as error
        return Status.Completed
    }
}

class CompletedPaymentProcessingState : PaymentProcessingState {
    fun process(paymentRequest: PaymentRequest): Status {
        // log some analytics
        ..
        return Status.Completed
    }
}
```

Finally, we can define a payment processing service, which ties all the states together:
```kotlin
class PaymentProcessingService(private val userService, private val paymentGateway: PaymentGateway)  {
    fun processPayment(paymentRequest: PaymentRequest) {
        when (paymentRequest.getStatus()) {
            Status.Requested -> RequestedPaymentProcessingState(userService).process(paymentRequest)
            Processing -> ProcessingPaymentProcessingState(paymentGateway).process(paymentRequest)
            Approved -> ApprovedPaymentProcessingState().process(paymentRequest)
            Declined -> DeclinedPaymentProcessingState().process(paymentRequest)
            Error -> ErrorPaymentProcessingState().process(paymentRequest)
            Completed -> CompletedProcessingState().process(paymentRequest)
        }
    }
}
```
