WWDC19
# Table of Contents
=================

   * [SwiftUI Essentials - Wednesday](#swiftui-essentials---wednesday)
      * [Views and Modifiers](#views-and-modifiers)
         * [Binding Syntax](#binding-syntax)
      * [Building Custom Views](#building-custom-views)
      * [Composing Controls](#composing-controls)
      * [Adaptive Controls](#adaptive-controls)
         * [Toggle](#toggle)
         * [Picker](#picker)
      * [Control Modifiers](#control-modifiers)
         * [Environment Variables](#environment-variables)
      * [Navigating Between Screens](#navigating-between-screens)

# SwiftUI Essentials - Wednesday
Session materials: https://developer.apple.com/videos/play/wwdc2019/216/

## Views and Modifiers
- View Container Syntax
  ```
  Container {
    content
    content
    content
  }
  ```
- ### Binding Syntax
  - `@state private var` can contain bindable custom types to a SwiftUI to pass dynamic values
  - `$` sign binds the values

- The execution and declaration of the code is sequential. The order of chaining determines the final UI.
  - e.g applying a background before and after a padding results in different UIs

## Building Custom Views
- A view defines a piece of UI by combining lightweight UIs
```
struct Foo: View {
    var body: some View {
    }
}
```
compared to

```
class Foo: UIView {}
```
- `View` is a protocol instead of `UIView` subclass. Every view is conforming to this declarative protocol to define their own specific roles liek having bgColor, or font etc.
- Try to push conditions into a single UI rather than adding and removing views on different conditions

## Composing Controls
```
Form {
  Section
    content
    content
  Section
    content
}
```

for form styled views with specific sections which has their own set of cells automatically

```
Button(action: action) {
  VStack {
    content
    content
  }
}
```
 to have a highly customized button with vertically aligned content

## Adaptive Controls
- Describe their purpose, not visuals
- Smarter default behaviors
- Highly reusable components

### Toggle
- `isOn` & `label`
  ```
  Toggle(isOn: $BINDING_HERE) {
    Text()
    // to make custom views accessible
    CustomShape().accessibility(label: Text())
  }
  ```
### Picker
```
Picker(selection: $BINDING, label: Text()) {
  Text().tag()
  Text()
}.pickerStyle(.radioGroup)
```
- Pickers inside sections become selectable lists automatically and pops back upon selection!

## Control Modifiers
```
Form {
  Section {
    Toggle(isOn)
    .disabled()
  }
}
.accentColor() // Form wide accent color
.disabled() // Form wide disabling rather than single disabling
```
### Environment Variables
- These environment variables are applicable to any content
`@environment var`

## Navigating Between Screens
```
struct ContentView: View {
    var body: some View {
      NavigationView { // Standard navigation
       OrderForm()
      }
    }
}

struct OrderForm: View {
    var body: some View {
      NavigationButton(destination: ANOTHER_VIEW)
    }
}
```
