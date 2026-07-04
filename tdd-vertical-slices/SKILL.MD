---
name: tdd-vertical-slices
description: Use when implementing a change with guidance on how to break the work down into smaller simpler changes
---

# Preparation

- before starting, check if there are any refactoring(s) that would make the change simpler to implement
- "make the change easy, then make the easy change"

# Slicing

- slice the work vertically, test and implement each slice of functionality end to end, starting from the external interface
- prefer keeping the code in a work state as much as possible at each stage
- any shared fundational work can be added onto the first slice to keep in interfaces client driven
- any shared infrastructure could be added as an extra step at the end

E.G. for adding a new resource which requires CRUD operations the slices could be

1. Create new widget
2. Get new widget
3. Update widget
4. Delete widget

The order is important too - Create is first, as then there is potential some data to read, then Get to read back what we expect to have been written. Update should be very similar to the Create action, and finally Delete which is normally an optional extra.

Each of these are external operations which can be tested, reviewed, and deployed end-to-end independently

# Testing

Follow the guidance for building a test suite in ./testing/SKILL.md

## Test Driven Development

- Write a list of test cases
- Pick one test to start with
- Write a failing test
- Write the functional code until the test passes
- Refactor the implementation to be consistent with the target architecture
- Refactor the tests towards a Given, When, Then structure when it would help readability
- Pick the next test from the list

# Status Updates

## Test Cases

- output the test cases at the begining of the slice in concise bullet points

E.G.

- updates profile image
- validates username
- rejects unauthenticated user
- database error

## Cycle

- use emojis to make the current stage clear
  - Red 🟥
  - Green 🟩
  - Refactor 🟦
