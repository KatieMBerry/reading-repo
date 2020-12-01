// TDD Where Did It All Go Wrong //

Problems with TDD:
    - takes more time, and pressure from product managers to skip in order to have a quicker deliverable 
    - typically more test code than production code
    - tests break when you want to add features and are therefore an obstacle to change
    - when tests are broken, it's hard to undersatnd their intent
    - customers don't regard
    - devs don't see the value of their efforts

The Bigger Problem:
    - original intent of TDD is good, but we've been led astray
    - testing is meant to test behaviors (ie the "stable contract" of your software), not implementation details because those change over time
        - "behavior-driven development": "test" is misunderstood
    - triggers for new tests should only be for implementing a new feature/changing a requirement (high-level)
        - tests to cover use cases ("when, then" model)
    - tests should run in isolation of other tests
- RGR: 
    1. write a little test that doesn't work
    1. make the test pass as quickly as possible - be a duct-tape programmer for a minute
            - only trying to satisfy the behavior to understand how to implement requirements
            - speed trumos design in this moment
    1. eliminate dups and make it clean

// TDD red-green-refactor // 

see reading-01.md

// Cycles of TDD //

see reading-01.md

