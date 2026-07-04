---
name: tdd-slices
description: Plan and execute work using Test Driven Design in vertical slices
---

# Preparation

- before starting, check if there are any refactoring(s) that would make the change simpler to implement
- "make the change easy, then make the easy change"

# Slicing

- slice the work vertically, test and implement each slice of functionality end to end, starting from the external interface
- prefer keeping the code in a work state as much as possible at each stage
- any shared fundational work can be added onto the first slice to keep in interfaces client driven
- any shared infrastructure could be added as an extra step at the end

e.g. for adding a new resource which requires CRUD operations the slices could be

1. Create new widget
2. Get new widget
3. Update widget
4. Delete widget

The order is important too - Create is first, as then there is potential some data to read, then Get to read back what we expect to have been written. Update should be very similar to the Create action, and finally Delete which is normally an optional extra.

Each of these are external operations which can be tested, reviewed, and deployed end-to-end independently

# Testing

Follow the guidance for building a test suite in https://github.com/Jmen/skills/blob/main/testing/SKILL.MD

##Test Driven Development**

- Write a list of test cases
- Pick one test to start with
- Write a failing test
- Write the functional code until the test passes
- Refactor both new and old code to make it well structured
- Pick the next test from the list

- use emojis to make the current stage clear 
- - Tests Failing 🟥
- - Test Passing 🟩
- - Refactoring 🟦

- look for opportunities to add to existing tests rather than adding a new test everytime
- we want to keep the tests consice, and minimise how long they take to run

**Deployment Risk**

- evaluate the deployment risk of this change in term of backward compatibility
- recommend if feature toggles might be useful, or a certain deployment order of updates
