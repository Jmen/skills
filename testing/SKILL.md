---
name: testing
description: Use when deciding what type of testing is appropriate to verify the implementation
---

# What Makes A Good Test Suite

Normally when we talk about the desirable properties of tests, like being fast, being isolated etc, we are talking about individual tests. This document is about properties of the Test Suite as a whole.

Each property of the Test Suite is a trade off, as different types of tests have strengths and weaknesses, but overall we want to make sure that the balance between them is right.

This tries to avoid talking about unit tests, integration tests, etc as much as possible, because they don’t have common meanings, and so don’t focus as clearly on the important principles

## Test Desiderata

### Fast
- A few tests being slow is okay, as long as the whole suite is fast overall
- If slow tests cover a missing area of predictiveness, they can be worth the extra time

### Predictive of Correctness
- Does the suite passing actually prove we are safe to deploy to production?
- Are the tests representative of what actually happens in the production environment?
- Are there gaps in the test scenarios covered?
- Are there gaps in between the layers of tests?

### Cost of Ownership
- Are the tests easy to understand – use either Behaviour Driven Development or Arrange Act Assert to organise the tests
- Tests which are coupled to the implementation are hard to change - only interact with the System Under Test through its public interface, and prefer Outside-In testing to provide the largest possible opportunity for refactoring without needing to change the tests
- Tests which are Flaky undermine confidence and are not Predictive - invest extra time in figuring out these issues. If the system is flakey in the test environment, it's likely it's flakey in production as well
- Can we refactor easily, without needing to re-write every test as well?
- are test flakey?
- is it fast to write new tests?


### Supports Ongoing Development
- The tests act as documentation of the functional requirements
- The tests use the language of the domain

## Black Box vs White Box

The property of running **Fast** pushes us towards more **white box testing**

- In-memory tests with no external dependencies are the fastest to execute

The properties of **Predictiveness**, and **Cost of Ownership** push us towards **black box testing**

- Driving tests from the external public interface is the most representative of how the system is actually used, and allows the maximum amount of refactoring opportunity
