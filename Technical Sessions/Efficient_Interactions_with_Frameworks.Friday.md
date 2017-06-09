WWDC 2017

Table of Contents
=================

  * [Efficient Interactions with Frameworks](#efficient-interactions-with-frameworks)
    * [Improvements in Foundation](#improvements-in-foundation)
    * [Data](#data)
    * [Bridges and how they affect your app](#bridges-and-how-they-affect-your-app)
    * [Strings, range, and text](#strings-range-and-text)
    * [Best practices &amp; tips](#best-practices--tips)

# Efficient Interactions with Frameworks
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/244/

## Improvements in Foundation
  - NSCalendar
  - Internet locking improvements
  - `NSOperation` and `NSOperationQueue`
  - Copy on write collections - return copy NSMutableArray as NSArray

## Data
  - Subscripting Data is faster - indices
  - malloc/free is not needed Data(count:250) implements
  - ranges -subdata

## Bridges and how they affect your app
  - Toll-free bridging
    - From a CF type to a NS Type
    - From a NS type to a CF Type
    - Zero cost at cast
    - Extra cost at usage
  - Swift bridging
  - Costs are on the usage
  - CFArrayGetCount((CFArrayRef(array))

## Strings, range, and text
  - `NSTextStorage` -> NSMutableAttirutedString
  ```
  var text = textView.textStorage.string // cost of copy
  var text = textView.textStorage.mutableString // NO cost of copy <— USE THIS ONE FOR NOW (apple is working on a solution for future)
  ```
  - NSAttributedString- NSRange without casting String - NSString
  - NSRegularExpression - Range for UTF16-UTF8 without casting

## Best practices & tips
  - Autolayout practices
  - Set rendering for attributed strings
  - Specify alignment and writing direction if known.
  - `baseWritingDirection = .leftToRight`
  - Use clip line breaking mode
