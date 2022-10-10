# Kotlin Essentials

- Kotlin is a strongly statically typed general-propose Programming Language that runs on JVM
- It is an Open Source Programming Language that combines object-oriented Programming and functional Programming

## Features of Kotlin

- Kotlin is compatible with Java - every Java File is fully interoperable with Kotlin
- Kotlin can be used on multiple Platforms (like Linux, Windows and JavaScript which reduces the Afford to maintain it
  on different Platforms
- It does not depend on the Virtual Machine of the Target Platform
- Kotlin has the following Features:
    - Null Safety which resolves Problems that are associated with the Null Exception,
    - Lambda Functions which are Anonymous Functions and
    - Smart Casts are used to track Conditions inside Expression
- It provides Extensions that allows the Addition of new Functionality to Classes without inheriting from Super Classes
  or any Decorative Pattern
- Functions can be passed as Parameters to the Function, also known as Higher-order Functions
- In Higher-order Functions the passed Functions act as a Variable and can be returned
- Kotlin provides a Data Class that avoids the Implementation of Methods within the Class
- Data Classes provide self-generated Code

## Variables

- `var` is the Variable whose Value can be reassigned - it is mutable
- `val` is the Variable whose Value can not be reassigned, changed or modified - it is immutable
- In Kotlin, it is not necessary to specify the Type of Variable because it uses Type Inference
- Type Inference is the automatic Detection of the Type of Expression in a Formal Language
- In Kotlin, it is also possible to specify the Type

## String Templates

- In Kotlin, String Templates allow to include an Expression or Variable Reference inside a String
- Variable References in a String start with a `$` Sign

## Statements

- The `if else` Statement can also bs used as Expression that means it returns a Value
    - `if` is used when a Block of Code must be executed based on the Condition to be true
    - `else` is used when a Block of Code must be executed if the same Condition is false
    - `else if` is used to specify a new Condition if the previous Condition is false
- The `when` Statement is similar to the `switch` Statement in Java

## Null Safety

- Null Safety solves the Problem of Null Pointer Exceptions
- To define a Variable which can hold a `null` Value, a `?` is putting in the End of a Type
- For example: `var name: String?=null`
- By Default Variables in Kotlin are not null Safety

## Threads

- A Program is a Set of Instructions to execute Operations
- When a Program runs, a Process is created which contains Threads
- Threads work in a sequential Manner
- Whenever a Thread gets stuck while running an Instruction, the other Thread executes the of the Instructions

## Coroutines

- Coroutines are lightweight Threads that help to write simplified asynchronous Code that keeps the Application
  responsive while maintaining heavy Tasks like Network Calls
- A Coroutine is executed in a Thread, and it is suspendable
- Suspendable that a Coroutine can be stopped, and then continue again from the stopping Point
- Coroutines provide the following Features:
    - lightweight Threads because they can be stopped and continued,
    - less Memory Leaks because of structured Concurrency that allow to launch a new Coroutine inside an existing
      Coroutine (this set the Lifespan for new Coroutines),
    - built-in Cancellation Support (a Coroutine can not be canceled if it is in Computation)

- __Launch__ is a Coroutine Builder to launch a new Coroutine concurrently that works independently (without Blocking
  the current Thread)
- __Delay__ is a suspending Function which is used to suspend a Coroutine for a particular Time and resumes it after
  that Time
- It allows other Coroutines to run and use the underlying Thread
- __Run Blocking__ is a Coroutine Builder that runs a new Coroutine and block the current Thread until it is completed

```kotlin
fun main() = runBlocking {
    launch {
        delay(4200L)
        println("Michael")
    }
    println("Name is ")
}
```

### Scope Builder

- The Coroutine Scope is used to declare an own Scope
- Unlike `unBlocking`, it just suspends and releases the underlying Threads

### Explicit Job

- A Job Object is returned by the __Launch Coroutine Builder__, whose Task is to explicitly wait for the Child Coroutine
  Completion
- Jobs act as a Handler to the Coroutine in the Queue

### Suspending Functions

- Suspending Functions are those Functions that can be paused and then continued later
- They can be used inside the Coroutines and can use other suspending Functions