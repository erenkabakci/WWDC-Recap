WWDC19
# Table of Contents
=================

   * [Introducing Combine and Advances in Foundation - Thursday](#introducing-combine-and-advances-in-foundation---thursday)
   * [Foundation Updates](#foundation-updates)
      * [Ordered Collection Diffing](#ordered-collection-diffing)
      * [Data](#data)
         * [Contiguity](#contiguity)
         * [Compression](#compression)
         * [Units](#units)
         * [Displaying a Date or Time](#displaying-a-date-or-time)
         * [List Formatter](#list-formatter)
      * [Operation Queue](#operation-queue)
         * [Progress Reporting](#progress-reporting)
   * [Swift Updates](#swift-updates)
         * [Scanner](#scanner)
         * [FileHandle](#filehandle)
   * [Introducing Combine -&gt; The replacement for Rx!](#introducing-combine---the-replacement-for-rx)
      * [Publisher](#publisher)
      * [Subscriber](#subscriber)
      * [Operator](#operator)

# Introducing Combine and Advances in Foundation - Thursday
Session materials: https://developer.apple.com/videos/play/wwdc2019/711/

# Foundation Updates
## Ordered Collection Diffing
```
let diff = bird.difference(from: bear)
let newBird = bear.applying(diff) // [b, i, r, d]
```
  - Applicable to any collection type

## Data
### Contiguity
  - `struct Data` becomes contiguous
    - `public protocol ContiguousByte`

### Compression
```
let compressed = try data.compressed(using: BUILT_IN_COMPRESSION_ALGORITHM_ENUMS)
```

### Units
  - Added new `UnitDuration`s & a new `UnitFrequency`
  - `UnitInformationStorage`

### Displaying a Date or Time
  - Relative Date Time Formatter!!!!

### List Formatter
```
let listFormatter = ListFormatter()
let dateFormatter = dateFormatter()

listFormatter.itemFormatter = dateFormatter
let string = listFormatter.string(from: dates)
```

## Operation Queue
```
queue.addBarrierBlock {
  save()
}
```
  - This guarantees that a given task is the only one running at a given particular time. Blocks the other remaining ones

### Progress Reporting
```
let queue = OperationQueue()
queue.progressCount = SomeNumber
```

- Be prepared for UWSB and SMB on iOS to take multiple and disappearing volumes into account

# Swift Updates
### Scanner
  - `scanUpToCharacters(from:) & scanString()`

### FileHandle
  - A new error-based API

- Use `DataProtocol` instead if [UIInt8]`
- Format dates and lists with `Formatter`
- Use `OperationQueue` s barrier and progress reporting

# Introducing Combine -> The replacement for Rx!
  - A unified declarative API for processing values over time
  - Generic
  - Type safe
  - Composition first
  - Request driven

## Publisher
  - Defines how values and error are produced
  - One key function: "subscribe"
  - Value type

## Subscriber
  - Reference type
  - It can receive one subscription. N inputs and one completion

## Operator
  - Like a mapper between Publisher and Subscriber
  - Adopts `Publisher`
  - `struct Map`

- Ability to chain operators exactly like RxSwift
- Chaining results in a cancellable
- Combine adopts many known Rx patterns
