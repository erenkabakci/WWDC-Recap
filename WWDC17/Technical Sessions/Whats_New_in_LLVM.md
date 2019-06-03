WWDC 2017

Table of Contents
=================

  * [What's New in LLVM \- Thursday](#whats-new-in-llvm---thursday)
    * [Api availability checking](#api-availability-checking)
    * [Static Analyzer](#static-analyzer)
    * [New Warnings](#new-warnings)
    * [C\+\+ Warnings](#c-warnings)
      * [Features from C\+\+17](#features-from-c17)
      * [LTO \- Link\-time optimization](#lto---link-time-optimization)

# What's New in LLVM - Thursday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/411/
Provided by @mihriminaz

## Api availability checking
  - Base OS - deprecated functions/new parameters-functions
  - Swift 3:
    - Unified query syntax in swift `#available`
  - New Availability checking in Objective-C - NEW!!!
  - Compiler warnings
  - @available to query availability
  - If `(@ available(iOS 11, *))`  = required
  - `API_AVAILABILITY()` macro for your functions, classes to mark OS support..
  - `__builtin_available` for C and C++ for class definitions/functions

All APIs are checked in compile time..

## Static Analyzer
  - 3 new checks:
    1. NSnumber CFNumberRef
      - //No need to check for nil.
      - `self.photoCount.integerValue > 1`
      - Early return
      - Suspicious coversions NSnumber CFNumberRef = set yes aggressive -> compiler will check
    2. dispatch_once()
      - Global or static variable..
      - NSLock ->
    3. NSMutable copy properties
      - @property(copy) <= mutation detects.

## New Warnings
  1. Capturing parameters in blocks with ARC
      Opt parameter `__Strong * error`
  2. Non-prototype declarations in C and objective C
      Change () -> (void)

## C++ Warnings
  - Renaming a function, structs, constants name all over the places..
  - Turning a block of code to functions - > adds the parameters as reference typed
  - Code completion

### Features from C++17
  - auto[…] To decompose std::tuple
  - initializers in if scope, if it is used later - gives error
  - advanceDispatch -> new !! => constexpr - an alternative for compile-time dispatch
  - std::string -> Substrings are copies and can be expensive -> use std::string_view, but it is not safe (it does not have a storage - so can cause issues after free/release)

### LTO - Link-time optimization
  - Clean link, incremental link has better performances
  - Enable incremental LTO
