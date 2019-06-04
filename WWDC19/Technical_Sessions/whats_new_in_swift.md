WWDC19
### [Back to the Readme](./Readme.md)

# Table of Contents
=================

   * [What's New in Swift - Tuesday](#whats-new-in-swift---tuesday)
      * [Binary Frameworks](#binary-frameworks)
      * [Performance](#performance)
      * [Swift Tooling and Open Source](#swift-tooling-and-open-source)
      * [Language and Standard Library](#language-and-standard-library)

# What's New in Swift - Tuesday
Session materials: https://developer.apple.com/videos/play/wwdc2019/402/

## Binary Frameworks
- Module + ABI Stability = Binary frameworks
  - This allows working with modules compiled in a different compiler than another piece of source code

## Performance
- Reducing swift runtime overhead with shared runtime to %0 when the code is compiled with Swift 5
- %10 smaller code size, %15 when `Optimize for size` is being used
- Faster bridging between Swift and Objective-C
- Faster `NSDictionary` to `Dictionary` bridging
- 15x faster `NSString` operations when performed on bridged `NSString`s
- Native Swift Strings now interoperate with C APIs without overhead. This is possible by moving to UTF-8 from UTF-16.

## Swift Tooling and Open Source
- sourcekitd SourceKit stress tester to reproduce some known sourcekit crashes

## Language and Standard Library
- Implicit return from a single expression
- Synthesized default parameters for structs. Ability to construct with selected default parameters only
- String interpolation is 1.7x faster than Swift 4.2
  - Possibility to use interpolation while localizing a string as well
- Opaques result types, to return same concrete types of an instance but hiding them via a protocol to not expose API details to the outside
  - `var shape: some Shape { }`
  - Only possible with the new Swift 5.1
- Property Wrappers!
  - There are property implementation patterns that come up repeatedly. Rather than hardcode a fixed set of patterns into the compiler, we should provide a general "property wrapper" mechanism to allow these patterns to be defined as libraries.
  - https://github.com/DougGregor/swift-evolution/blob/property-wrappers/proposals/0258-property-wrappers.md
- Define embedded DSLs in Swift to support DSLs with custom DSL builders
  - The compiler recognizes the DSL code

### [Back to the Readme](./Readme.md)
