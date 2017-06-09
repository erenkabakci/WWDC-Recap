WWDC 2017

Table of Contents
=================

  * [Engineering for Testability \- Friday](#engineering-for-testability---friday)
  * [Testable App Code](#testable-app-code)
    * [Structure of a Unit Test](#structure-of-a-unit-test)
    * [Characteristics of Testable Code](#characteristics-of-testable-code)
    * [Protocols and Parameterization](#protocols-and-parameterization)
    * [Seperating Logic and Effects](#seperating-logic-and-effects)
  * [Scalable Test Code](#scalable-test-code)
    * [Balance Between UI &amp; Unit Tests](#balance-between-ui--unit-tests)
    * [Code to help UI Tests Scale](#code-to-help-ui-tests-scale)
      * [Abstracting UI element queries](#abstracting-ui-element-queries)
      * [Creating objects and utility functions](#creating-objects-and-utility-functions)
      * [Utilizing Keyboard Shortcuts](#utilizing-keyboard-shortcuts)
  * [Treat your test code with the same amount of care as your app code](#treat-your-test-code-with-the-same-amount-of-care-as-your-app-code)
      * [Quality of Test Code](#quality-of-test-code)

# Engineering for Testability - Friday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/414/
This is the best session !

# Testable App Code
## Structure of a Unit Test
  - Prepare input
  - Run the code being tested
  - Verify output

## Characteristics of Testable Code
  - Control over inputs
  - Visibility into outputs

## Protocols and Parameterization
  - Reduce references to shared instances
  - Accept parameterized input
  - Introduce a protocol
  - Create a testing implementation (mocks)

## Seperating Logic and Effects
  - Extract algorithms into separate types, away from the code using side effects
  - Functional style with value types. Input -> Outputs
  - Thin layer on top to execute effects

# Scalable Test Code
## Balance Between UI & Unit Tests
  - Testing pyramid -> UI, Integration Tests, Unit Tests

## Code to help UI Tests Scale
### Abstracting UI element queries
  - Store part of queries in a variable
  - Wrap complex queries in utility methods
  - Reduces noise and clutter in UI tests
### Creating objects and utility functions
  - Encapsulate common testing workflows
  - Cross-platform code sharing
  - Improves maintainability
### Utilizing Keyboard Shortcuts
  - Avoid working through menu bar for macOS
  - Make code more compact

# Treat your test code with the same amount of care as your app code
  - Important to consider even though it isn't shipping
  - Test code should support the evolution of your app
  - Coding principles should apply to tests as well
  - Code reviews for test code, not code reviews with test code

### Quality of Test Code
