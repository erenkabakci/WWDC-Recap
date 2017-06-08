WWDC 2017

Table of Contents
=================

  * [Finding Bugs Using XCode Runtime Tools](#finding-bugs-using-xcode-runtime-tools)
    * [Main Thread Checker](#main-thread-checker)
      * [Designing asynchronous APIs](#designing-asynchronous-apis)
    * [Address Sanitizer](#address-sanitizer)
    * [Thread Sanitizer](#thread-sanitizer)
      * [Data Races](#data-races)
      * [Races on Collections](#races-on-collections)
      * [Key Points](#key-points)
    * [Undefined Behaviour Sanitizer](#undefined-behaviour-sanitizer)
      * [Integer Overflow](#integer-overflow)
      * [Alignment Violation](#alignment-violation)
      * [Nonnull Return Value Violation](#nonnull-return-value-violation)
    * [Using Runtime Tools Effectively (Important)](#using-runtime-tools-effectively-important)

# Finding Bugs Using XCode Runtime Tools
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/406/

## Main Thread Checker
  - Detects misuses of common APIs
  - Available in the diagnostics tab of a scheme, under "Run"
    - Also can pause on issues for a better understanding
  - Supports AppKit, UIKit, WebKit
  - Swift and C languages
  - Does not require recompilations
  - Enabled by default on XCode 9
### Designing asynchronous APIs
  - Good APIs should also provide queue as a parameter to specify where the code will be running

## Address Sanitizer
  - Detects use-after-scope
  - Detects use-after-return
  - These both prevents access to the pointers created in previous scopes to prevent leaks and crashes
  - Better to use if there is a C & Obj-C mixed project with pointers

## Thread Sanitizer
  - Detects multithreading issues
  - Find races even if they did not manifest
  - Only on 64 bit macOS and simulators
### Data Races
  - Unsync access to shared mutable vars
  ```
  class EventLog {
    private var lastEventSource: LogSource?

    func log(source: LogSource, message: String) {
      print(message)
      lastEventSource = source
    }
  }

  // Thread 1
  eventlog.log()...

  // Thread 2
  eventlog.log()...

  /// This is a data race, solve it by dispatch queues so func() runs asynchronously in a GCD Queue
  ```
  - Associate your data with serial dispatch queues
### Races on Collections
  - Swift and Obj-C collection races are also detected
### Key Points
  - Use GCD to synchronize access to the data

## Undefined Behaviour Sanitizer
  - Runtime bug finder
  - Checks unsafe constructs in the C language family
  - Compatible with other runtime tools
### Integer Overflow
  - Detects a possible integer overflow
### Alignment Violation
  - Unaligned load or store
  - Causes crashes in Release builds
### `Nonnull` Return Value Violation

* Undefined Behaviour Sanitizer is available under build settings

## Using Runtime Tools Effectively (Important)
  - Exercise more code
    - Use runtime tools for daily development
    - Use them before every release
    - Use CI with these tools turned on (WWDC 2015 -> CI and Code Coverage Session)
  - Combine different tools

* Turning these tools on can cause execution and memory overhead up to 10x times
