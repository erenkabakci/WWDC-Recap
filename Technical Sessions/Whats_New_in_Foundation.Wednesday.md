WWDC 2017

Table of Contents
=================

  * [What's New in Foundation \- Wednesday](#whats-new-in-foundation---wednesday)
  * [New Api highlights](#new-api-highlights)
    * [Foundation](#foundation)
    * [Key paths and KVO](#key-paths-and-kvo)
    * [Encoding &amp; Decoding](#encoding--decoding)
      * [Definitely check here for more info about this <a href="https://developer\.apple\.com/documentation/foundation/archives\_and\_serialization/encoding\_and\_decoding\_custom\_types">https://developer\.apple\.com/documentation/foundation/archives\_and\_serialization/encoding\_and\_decoding\_custom\_types</a>](#definitely-check-here-for-more-info-about-this-httpsdeveloperapplecomdocumentationfoundationarchives_and_serializationencoding_and_decoding_custom_types)
      * [The Philosophy Behind](#the-philosophy-behind)

# What's New in Foundation - Wednesday
Provided by @mihriminaz
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/212/

# New Api highlights
## Foundation
  - `FileProvider` communication
  - Improved `String` <-> `NSString` range conversion
  - Discrete NSProgress support in NSXPCConnection
  - Copy-on-write in `NSArray`, `NSDictionary`, `NSSet`
  - Data inlining
  - Faster bridging from `NSNumber` to `String`

## Key paths and KVO
  - Swift 3 had string keypaths `#keypath` to reach a class's property - @objcMembers
    - No type information
    - Had to be type of `Any`
    - Wasn't type safe
    - Wasn't fast
  - Swift 4
    - With a backslash directly reach the keypath
    ```
    \Kid.age
    \Kid.nickname
    \Kid.friends[0]
    ```

    Reference type examples
    ```
    let age = ben[keyPath: \Kid.age]
    ben[keyPath: \Kid.nickname] = “Ben”
    ```

    Value type example
    ```
    bensParty[keyPath: \.theme] = “Ninja”
    ```
  - `WritableKeypath` write directly into value type base
  - `ReferenceWritableKeypath` write into a reference type base

## Encoding & Decoding
  - `Codable` supports different types like `Date`, `URL` Json data, lousy types
  - `Codable` is both encodable and decodable
  - Supports nested types
  - Supports collections with `Codable` types
  - Coding protocols:
    - CodingKey protocol -> comment_count for different mapping options
  - Encoding or Decoding Exclusively. Conform to only `Encodable` or `Decodable`
  - Rename Properties Using Coding Keys
  ```
  struct Landmark: Codable {
    var name: String
    var foundingYear: Int
    var location: Coordinate
    var vantagePoints: [Coordinate]

    enum CodingKeys: String, CodingKey {
        case name = "title"
        case foundingYear = "founding_date"

        case location
        case vantagePoints
    }
}
  ```
### Definitely check here for more info about this https://developer.apple.com/documentation/foundation/archives_and_serialization/encoding_and_decoding_custom_types

### The Philosophy Behind
  - No fatal errors -only for developer mistakes
  - Avoid possible errors on decoding(type mismatch, missing key, missing value, data corruption -during decoding data)/encoding (invalid value)
  - Beyond basic error handling: domain specific validation (like url has to be https - you set a rule!), graph value validation
