WWDC19
### [Back to the Readme](./Readme.md)

# Table of Contents
=================

   * [Introducing iPad Apps for Mac - Tuesday](#introducing-ipad-apps-for-mac---tuesday)
      * [Leverage Our Shared Technology Stack](#leverage-our-shared-technology-stack)
         * [When to Consider iPad Apps for Mac?](#when-to-consider-ipad-apps-for-mac)
         * [Goals](#goals)
         * [Things You Get for Free](#things-you-get-for-free)
         * [Features to Adopt](#features-to-adopt)
         * [Mouse and Touch Events](#mouse-and-touch-events)
      * [Unavailable APIs](#unavailable-apis)
      * [API Availability](#api-availability)
      * [Conditionalizing Code](#conditionalizing-code)
      * [Bundle Format](#bundle-format)

# Introducing iPad Apps for Mac - Tuesday
Session materials: https://developer.apple.com/videos/play/wwdc2019/205/

## Leverage Our Shared Technology Stack
- Unified layers for AppKit apps and UIKit Apps like Core Graphics, Core Location, Foundation, lower level services etc.

### When to Consider iPad Apps for Mac?
- Make iPad app available on the Mac
- Bring older Mac app to feature parity with iPad app
- Replace Mac app built on non-native technology

- Not all apps are candidates like iphone-only apps or apps that are built around mobile features

### Goals
- Easy to get started
- One project, one source base, one target
- iPad app on the inside
- Mac app on the outside

### Things You Get for Free
- Default Menu Bar with the menu items normally mac users expect
- Window management
- Dark mode compatibility
- Scroll behaviors
- Automatic mapping from iOS Settings app entries from the app to the mac app preferences
- Touch Bar
- Document pickers
- Custom views stay the same
- Text sizes: 17 pt default baseline for iOS apps is scaled to 13 pt
- Copy & paste
- Printing
- Multiple windows
- Application lifecycle

### Features to Adopt
- Mac icon
- Custom menus
- Toolbars
- Touch bars

### Mouse and Touch Events
- Hover with `UIHoverGestureRecognizer`
- Single-finger touch tracking
- Standard gestures
- Custom multi-touch codes are not automatically mapped to macOS and requires an alternative way when the app is being ported to the macOS

## Unavailable APIs
- Deprecated frameworks
- iOS specific frameworks
  - Classkit
  - Healthkit
  - Homekit
- Hardware specific frameworks
- Framework differences
  - Core Location
    - Macs don't have GPS for example
  - Core Motion
    - No motion sensors on the mac
  - Media Player
    - No playback support
  - Metal
    - Some advanced metal features are not available

## API Availability
- Defined by clear annotations

## Conditionalizing Code
- Possible with static checks `if available uiKitForMac`

## Bundle Format
- NSBundle will be adapting different hierarchies

- Various extensions are not available on macOS as expected

### [Back to the Readme](./Readme.md)
