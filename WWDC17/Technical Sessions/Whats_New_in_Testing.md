WWDC 2017

Table of Contents
=================

  * [What's New in Testing \- Thursday](#whats-new-in-testing---thursday)
    * [Enhancements](#enhancements)
      * [xcodebuild](#xcodebuild)
      * [XCode Server](#xcode-server)
    * [Async Testing](#async-testing)
      * [There were limitations](#there-were-limitations)
      * [XCTWaiter](#xctwaiter)
      * [XCTestExpectation](#xctestexpectation)
    * [Multi\-app Testing in UI Testing](#multi-app-testing-in-ui-testing)
    * [UI Testing Performance](#ui-testing-performance)
      * [First match vs Match Auto](#first-match-vs-match-auto)
    * [Block\-based NSPredicate](#block-based-nspredicate)
    * [Screenshot &amp; Attachments API in UI Tests](#screenshot--attachments-api-in-ui-tests)

# What's New in Testing - Thursday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/409/

## Enhancements
  - UI Testing in Xcode 8.3
    - Siri
    - UITouchBar
  - Xcode 9
    - Swift 4
    - Block-based teardown
  - UI Test speed enhancements
### xcodebuild
  - CoreSimulator without launchinf simulator app
  - Parallel device testing - YES ! with multiple `- destination`
  - Localization
### XCode Server
  - Improved provisioning workflow
  - CoreSimulator
  - Parallel Testing

## Async Testing
  - Validate calls which doesn't finish immediately
    - Opening docs
    - Work on background threads
    - Network activities
    - UI animations
  - Create expectations and fulfill
### There were limitations
  - Timeout was always a failure
  - Waiting requires test object
  - No nested Waiting
### XCTWaiter
  - Extracted logic from `XCTestCase`
  - Calls back to `XCTWaiterDelegate`

  ```
  XCTWaiter(delegate : self).wait(for: [expectation], timeout: 10)
  ```
### XCTestExpectation
  - Public initializer
    - Decoupled from `XCTestCase`
  - Multiple fulfillments
  - Ordering enforcement for expectations

## Multi-app Testing in UI Testing
  - Scenarios
    - App groups
    - Settings
    - Extensions
  - Additions to `XCUIApplication`
    - New initializers
    - Activate method `func activate()`
      - Useful for scenarios where there is no need to wipe out previous scenarios
  ```
  let readerApp = XCUIApplication(bundleIdentifier: "/////")
  let writerApp = XCUIApplication(bundleIdentifier: "/////")

  readerApp.launch()
  // Assertion to read something in the app

  writerApp.activate()
  // Write something and send via tap etc.

  // set an expectation with a predicate that readerApp is on foreground
  // wait for timeout
  ```

## UI Testing Performance
  - User interface elements
    - Buttons, labels etc.
  - Faster in XCode 9
### First match vs Match Auto

## Block-based `NSPredicate`

## Screenshot & Attachments API in UI Tests
