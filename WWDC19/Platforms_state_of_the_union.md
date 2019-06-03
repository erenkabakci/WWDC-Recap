WWDC19

# Table of Contents
=================

   * [Table of Contents](#table-of-contents)
   * [Platforms State of The Union - Monday](#platforms-state-of-the-union---monday)
      * [SwiftUI](#swiftui)
      * [Swift and XCode 11 updates](#swift-and-xcode-11-updates)
         * [Test Plans](#test-plans)
         * [Device Conditions](#device-conditions)
         * [Feedback](#feedback)
      * [macOS Catalina](#macos-catalina)
         * [Project Catalyst iPad -&gt; macOS](#project-catalyst-ipad---macos)
      * [watchOS](#watchos)
      * [iOS 13](#ios-13)
         * [Dark Mode](#dark-mode)
         * [Cards](#cards)
         * [Symbols](#symbols)
      * [iPadOS](#ipados)
         * [Multitasking](#multitasking)
         * [Productivity Gestures](#productivity-gestures)
      * [Accessibility](#accessibility)
         * [Discoverability](#discoverability)
         * [Voice Control](#voice-control)
      * [Privacy](#privacy)
         * [Sign in with Apple](#sign-in-with-apple)
      * [ML](#ml)
         * [CreateML](#createml)
      * [Siri](#siri)
      * [AR](#ar)
         * [Reality Composer](#reality-composer)
         * [RealityKit](#realitykit)
         * [ARKit3](#arkit3)
      * [Metal](#metal)

# Platforms State of The Union - Monday

## SwiftUI
  A brand-new UI framework!

  - Declarative
    - Writing code like declaring something in a normal sentence. One liner code pieces to define whole UI elements with fonts and colors etc.
  - Automatic functionality wherever possible
    - One line of code animations
    - Transitions with offsets and simple parameters
  - Compositional
    - Compose multiple smaller pieces together
  - Consistent
    - Automatic data source updates anytime the data changes
    - Mutable states with `@State` to apply to variables

  - Live development experience
  - Interactive SwiftUI documentation
  - Can be mixed with the existing code

## Swift and XCode 11 updates
  - Github support for swift packages in github packages registry
  - Swift packages are finally available for all apple platforms

  - Editors in XCode
    - Minimap on the right pane
      - `MARK` is now visible on the minimap and holding down the cmd key shows methed and variable names for easy navigation
    - Refactor and rename now applies to documentation as well
    - Live comparison of the diff with the previous commit
    - Related content
      - Visible when needed, hidden when there is no content

    - ### Test Plans
      - Combination of tests, with different tools & devices runs in a laned style

    - ### Device Conditions
      - Simulations like network and device temperature

    - Result bundles to see the details of a test suite

    - ### Feedback
      - App metrics
        - Anonymized metrics for device statuses like battery, memory usage etc.
      - Integrated feedback in testflight
        - Getting a screenshot brings a feedback form for testflight users

## macOS Catalina
  - ### Project Catalyst iPad -> macOS
    - 1. Click the checbox in XCode 11 for mac
    - 2. Make your iPad better by adapting larger layouts and keyboard behaviors
    - 3. Refine the implementation for macOS specific features

  - Dedicated read-only system volume to enhance security by limiting the access control
    - User data & apps
    - Operating system

## watchOS
  - Independent experience by running standalone on the watch exclusively
    - Supports running without iOS app (this is a checkbox in the target settings)
  - Self-care, mindfulness, physical therapy, smart alarms APIs
  - SwiftUI to build easy watch app features
  - Direct download and smaller bundles

## iOS 13
  - ### Dark Mode
    - Minimal chrome
    - Content focused
    - Semantic colors
      - Lighter layers above to enhance focus in the dark mode
    - Adaptive materials

  - ### Cards
    - Default presentation style now rather than a fullscreen modal
    - Dismissable easily by swiping down

  - ### Symbols
    - SF Symbols with more than 1500 symbols to scale along with the text when the font sizes change

## iPadOS
  - ### Multitasking
    - `UIWindowScene` API
    - A new `SceneDelegate` object separate from `AppDelegate` to handle multitasking scenes
    - A new state restoration system using the `NSUserActivity` API

  - PencilKit

  - ### Productivity Gestures
    - Using `NSUndoManager`, pinches and swipes for undo & copy & paste

## Accessibility
  - ### Discoverability
    - Quick start
    - Easier customizability in the settings app

  - ### Voice Control
    - Comprehensive
    - Text editing
    - Awareness
    - Spoken gestures

## Privacy
  - Design for privacy
    - Process on device
    - Ask first
    - Use random identifiers
    - Encrypt

  - Allow once
  - Two staged location access for, only when in use and always allow

  - ### Sign in with Apple
    - Fast, easy signing without all the tracking
    - Streamlined account setup
    - Verified email addresses
    - Built-in security with always on 2FA
    - Available on Android and Web as well!

## ML
  - 5 trillion operation per second capable neural chip
  - Text recognition from an image
  - Image saliency to define a heat map on an image to find focus areas on a given picture
  - On-device speech
  - Speech saliency to understand the pronunciation, pitch and cadence of a speech

  - ### CreateML
    - Now a macOS app which lets a user build an ML model with zero
    - Realtime feedback on model training
    - Get to experiment and preview models

## Siri
  - Shortcut app
    - Automations to have combined scenarios for specific app actions

## AR
  - ### Reality Composer
    - Layout AR experiences in 3D
    - macOS, iOS and iPadOS
    - Guaranteed to look great
  - ### RealityKit
    - Modern real-time 3d engine
  - ### ARKit3
    - Simultaneous use of front and back camera
    - People occlusion
    - Motion capture

## Metal
  - Easy to use
  - Powerful compute
  - Built for pros

  - Metal support in iOS simulator
  - Metal memory debugger
