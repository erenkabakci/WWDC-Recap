WWDC 2017

# What's New in Swift
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/402/

### General Announcements
  - Toolchain support for more refactors in XCode
  - Swift Package Manager
    - New Manifest API

## Access Control
  - Expand the scope of private needs, meaning that `private` flag will expose variables to the same file for `extensions`. No need to use `fileprivate` anymore

## Composing Classes & Protocols
  - Usage of things like `[UIControl & SomeProtocol]`. Allowing to compose certain classes with certain protocols rather than trying to conform to `UIControl` and make them conform to `SomeProtocol`

## Source Compatibility
  - Swift 3.2 allows Swift 3 syntax that has changed in Swift 4
  - Smoother migration to Swift 4
  - Per-target Swift compiler option `Swift 3.2` or `Swift 4.0`

## New Build System
  - Project Settings -> Shared Project Settings -> Build System -> New Build System
  - Precompiled bridging headers speed up the build process
  - Shared build for coverage testing
    - No additional build on top to generate coverage
  - Indexing while building
    - Build process now updates the index
    - Small overhead on the build time

## Predictable Performance
  _Good to watch understanding swift performance from the last year_
  - Large values are allocated in the heap and heap allocation is slow, costly
  - COW (Copy on write) optimizes large chunks of value types and allow to use same buffer if no modification is done (read only operation)
  - Stack allocation for generic buffers and unspecialized generic code

## Smaller Binaries
  - Compiler level optimization for unused code pieces
  - Swift 3 automatically infers `@objc` if there is an instance of `NSObject`. This does some autogeneration for obj-c specific signatures. These methods are not detected if they are not even used.
  - `@objc` marking is suggested on extensions and specific functions.
  - Migrator for minimal inference
    - Migrator will mark inferred obj-c chunks as deprecated
    - Check the console for these kind of warnings (`@objc`)
  - Change Swift 3 `@objc` inference to default after your refactor and optimization is done
### Symbol Size
  - Swift symbols take a lot of space
  - Symbol Stripping (reduces app size)
    - `Strip Swift Symbols` is `Yes` by default
    - View symbols with `xcrun dyldinfo --` (TBD)

## Strings
  - Unicode correctness by default
    - In Swift a `Character` is a grapheme meaning that every character is a single representation `.count = 1`
  - In Swift 4, strings are collection of characters
    - `somestring.{}` rather than `somestring.characters.{}`
  - String Slicing
    ```
    let s = "one, two, three"
    s.split(seperator: ",") -> ["one", "two", "three"] : [Substring]
    ```
    - `Substring` is a new type to avoid memory leaks. E.g: Prevent holding the whole buffer for a small part of a huge string. Wrap this into a `String` again after the operation is done.
  - Multi-line String Literals
    - Triple Quoted Strings `"""`
    ```
    let test = """
              Bla
              Bla
              Bla
              """
    ```

## New Generics Features
  - `associatedtype` extensions for protocols to avoid `Iterator.element` and use `Element`
  - Generic Subscripts

## Exclusive Access to memory
  - Ownership
  - Multi-threaded Enforcement
    - Threat sanitizer cathes these errors
  - This will be a warning in Swift 3.2, will be an error in future releases
### Taking Advantage of Exclusive Access
  - More reliable performance
  - Lots of optimization in libraries, compiler lvl etc.

## Enforcement in the Developer Preview
  - Compile time enforcement is enabled by default
