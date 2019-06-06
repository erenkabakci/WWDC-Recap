WWDC19
# Table of Contents
=================

   * [Table of Contents](#table-of-contents)
   * [Combine in Practice - Thursday](#combine-in-practice---thursday)
         * [@Published](#published)
         * [currentValuePublisher()](#currentvaluepublisher)
         * [passThroughPublisher()](#passthroughpublisher)
         * [eraseToAnyPublisher](#erasetoanypublisher)
         * [debounce](#debounce)
         * [removeDuplicates](#removeduplicates)
         * [sink() &amp; assign()](#sink--assign)

# Combine in Practice - Thursday
Session materials: https://developer.apple.com/videos/play/wwdc2019/721/

This is an example oriented heavy code focused session. Please follow the session materials.

- Combine has a built in bakc-pressure compared to RxSwift!
- It doesn't have disposeBags and the allocation is handled automatically
  - There is also a built-in cancel mechanism to terminate an ongoing emmission

### `@Published`
  - A new property wrapper to turn properties into publishers at the same time
    - Similar to `Variable<T>` or `BehaviorRelay<T>` on RxSwift
  ```
  @Published var foo: String
  self.foo = 1
  let boo = self.foo // Immediately assigns the current value as 1

  foo.sink() {
    // subscription stream will get 1 and 2
  }

  self.foo = "2"

  ```

### `currentValuePublisher()`
  - Holds the last emitted value as `BehaviorSubject` or similar to `ReplaySubject` in RxSwift
### `passThroughPublisher()`
  - Acts like a bridge from non rx world to rx world. (Similar to `publishSubject` in RxSwift)
### `eraseToAnyPublisher`
  - casts a given chain into a publisher to be used again across the API
### `debounce`
  - debounces the emission and can schedule on a given thread
### `removeDuplicates`
  - distinctUntilChanged() on Rx

- There are more than 90 common Rx operators built into Combine!

### `sink()` & `assign()`
  - `subscribe()` & `bind()` on RxSwift to get the emitted value on a subscriber
