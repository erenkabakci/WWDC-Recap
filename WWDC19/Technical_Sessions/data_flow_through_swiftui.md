WWDC19
# Table of Contents
=================

   * [Data Flow Through SwiftUI - Thursday](#data-flow-through-swiftui---thursday)
      * [Tools for Data Flow](#tools-for-data-flow)
         * [@State private var](#state-private-var)
         * [@Binding Property Wrapper](#binding-property-wrapper)
      * [Working with External Data](#working-with-external-data)
         * [Combine Publisher](#combine-publisher)
         * [BindableObject Protocol A.K.A RxSwift lol](#bindableobject-protocol-aka-rxswift-lol)
         * [@EnvironmentObject](#environmentobject)
      * [Source of Truth](#source-of-truth)
      * [Building Reusable Components](#building-reusable-components)
      * [Using State Effectively](#using-state-effectively)

# Data Flow Through SwiftUI - Thursday
Session materials: https://developer.apple.com/videos/play/wwdc2019/226/

## Tools for Data Flow
- Property
- BindableObject
- `@State`
- `@Binding`
- `@Environment`

### `@State private var`
  - Indicates that this value can change over time and not leading to mutation of `self` like a normal property value
  - It is a property wrapper
  - It is a good practice to define them `private` to limit it to the specified view
  - SwiftUI can observe a change on a `@State` variable
  - Every `@State` is a source of truth for the view

### `@Binding` Property Wrapper
  - Read and write without ownership
  - Derived from `@State`
  - Allow a child component to access a state via binding
  - It's a good practice to use them to keep the source of truth to one

  ```
  struct ContentView: View {
      @State private var foo: SomeType
      var body: some View {
         Button($foo) // Passing the binding here to the child view
        }
      }
  }

  struct Button: View {
    @Binding private var foo: SomeType
      var body: some View {
        // use the binding here without ownership
        Button(action: {
            withAnimation { self.foo.toggle()}
          })
      }
  }
  ```

- Usage of `@State` and `@Binding` eliminates the need for a view controller to handle

## Working with External Data

### Combine Publisher
  - Single abstraction
  - Main thread: use `.receive(on:)`

  ```
  someStack.onReceive(some.currentPublisher) { // Rx! }
  ```

### `BindableObject` Protocol A.K.A RxSwift lol
  - Reference type
  - External
  - Pass directly with `@ObjectBinding`
  - Automatic dependency tracking

  ```
  struct MyView: View {
    @ObjectBinding var model: MyModelObject
    ....
  }

  MyView(model: modelInstance)

  class MyModel: BindableObject {}
  ```

  - Views in SwiftUI are value types but @ObjectBinding works with reference passing

### `@EnvironmentObject`
  - Similar to `@ObjectBinding` with an addition of indirect passing
    - Acts like a singleton reference to an `@ObjectBinding` which is available to be used in various SwiftUI views
  - Data applicable to an entire hierarchy
  - Convenience for indirection
  - e.g accent color, theme, right to left etc

## Source of Truth
  - `@State`
    - View-local
    - Value
    - Framework managed
  - `BindableObject`
    - External
    - Reference
    - Developer managed

## Building Reusable Components
  - Read-only: Swift property, Environment
  - Read-write: `@Binding`
    - First class reference to data
    - Use `$` to derive from source
  - Prefer immutable access

## Using State Effectively
  - Limit use if possible
  - Use derived `Binding` or value
  - Prefer `BindableObject` for persistence
  - Example: Button highlighting

- Always question state vs binding needs!
