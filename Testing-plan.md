## Summary
if you fix a bug or add a new feature, you must write unit tests for the change. If you can, add module tests and E2E tests. These are not mandatory. 

## Why do we need to write tests?
* to reduce bugs
* to speed up development
* to confirm behaviors of QuISP

## Types of testing in QuISP
we have three types of testing to check QuISP's behavior.

### Unit Test
A unit test checks behaviors of the smallest chunk or part of our codebase. typically, we check the behavior of methods like this
* when the method is called with some arguments
    * it should return some value
    * it should change the class member to some value
    * it should change the component state
    * it should call another method with some arguments

We're using [GoogleTest](https://google.github.io/googletest/) framework for unit testing.
If there's a class that depends on another class, we often use ["mock"](https://google.github.io/googletest/gmock_for_dummies.html) to keep the scope of the test narrow. "mock" behaves like the actual instance in the test program, and it provides the more valuable feature to check the mock's method called or not. So we can prove our code works with other classes well. 

### (OMNeT++'s) Module Test
this checks a OMNeT++ module(inherits `omnetpp::cModule`) communicates with other modules. 
module test is not an ordinary one, and it's OMNeT++ specific.
We're using the [`opp_test`](https://doc.omnetpp.org/omnetpp/manual/#cha:testing) tool to run module tests.
Module tests have a minimum network to test the behavior of the target module.

### E2E(end-to-end) Test
E2E test checks the results of simulations. 

## Test Targets


## Test Process

## When should we write tests?
If you change the code, you should write unit tests for the corresponding part. 

For example, [PR#307](https://github.com/sfc-aqua/quisp/pull/307) added new class: RuleSetStore that contains RuleSets and provides a interface to manage RuleSets. I added new unit tests for RuleSetStore to check it can store, find, iterate and erase a RuleSet. And also, RuleSetStore is used inside RuleEngine, so I added more unit tests for the methods in RuleEngine not to break the current behavior.

Thus we can refactor our codebase safely and confidently.

## How and What should we write tests?
You should check the values changed and the methods called in your change. If you added a new method that returns some value, you should test the returned value. If you change the method that already exists, you should test the variable the method will modify. The important point is your tests should cover all the effects of your change. 

## How and what should we review tests?
A reviewer must check the tests cover all the changes. Ideally, the tests should cover all cases like both "if" and "else" cases in a conditional clause. 
 
## TDD
We encourage you to develop with the ["Test Driven Development"](https://en.wikipedia.org/wiki/Test-driven_development) style.
The process is simple: write a test first, implement it, and refactor it.
This process is also called "red/green/refactor."  
This cycle enforces us to write modular and maintainable code because writing tests is difficult if the code is messy and complex. Moreover, we would consider how to break down the methods and classes. If we write a huge method, writing tests becomes harder, and writing a test first makes the coding process easier.
