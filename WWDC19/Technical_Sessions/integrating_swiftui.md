WWDC19
# Table of Contents
=================

   * [Integrating SwiftUI - Thursday](#integrating-swiftui---thursday)
      * [Hosting Controller](#hosting-controller)
      * [Embedding Existing Views into SWiftUI](#embedding-existing-views-into-swiftui)

# Integrating SwiftUI - Thursday
Session materials: https://developer.apple.com/videos/play/wwdc2019/231/

## Hosting Controller
  - Wraps swiftUI hierarchy into a view controller
  - Subclass of `UIViewController`
  - `rootView` property represents a SwiftUI view
  - `let hostingController = UIHostingViewController(rootView: A_SWIFTUI_VIEW)`

- `setNeedsBodyUpdate()` & `updateBodyIfNeeded()`

## Embedding Existing Views into SWiftUI
  - `Representable` Protocol
    - Wraps UIKit/AppKit views
    - make -> update -> dismantle views

    ![Image](./representable_protocol.png)

## Integrating Your Data Model
  - Use `@BindableObject` protocol in the custom model to pass it to the SWiftUI

## `NSItemProviders`
