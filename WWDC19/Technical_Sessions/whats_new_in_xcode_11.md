WWDC19
### [Back to the Readme](./Readme.md)

# Table of Contents
=================

   * [What's New in Xcode 11 - Tuesday](#whats-new-in-xcode-11---tuesday)
      * [Workflow Updates](#workflow-updates)
         * [Assistant and Editor Splitting](#assistant-and-editor-splitting)
         * [Code Completion Improvements](#code-completion-improvements)
      * [Swift Package Manager](#swift-package-manager)
      * [Source Control Changes](#source-control-changes)
      * [Design Tools](#design-tools)
      * [Debugging](#debugging)
      * [Testing](#testing)
         * [Test Plans](#test-plans)
      * [Simulator Updates](#simulator-updates)
      * [Instruments](#instruments)
      * [SwiftUI](#swiftui)

# What's New in Xcode 11 - Tuesday
Session materials: https://developer.apple.com/videos/play/wwdc2019/401/

## Workflow Updates
### Assistant and Editor Splitting
- Option click to add a vertical editor in a selected editor
- Focus mode to enlarge a selected editor
- Existing hotkeys are compatible with the new editor shortcuts
- A smart minimap for the bird's eye view of the code
- Add documentation and refactor documentation as well
- Change bars show the diff real time

### Code Completion Improvements
- Function overloads
- Better enum completions

## Swift Package Manager
- Packager are first class
- Integrated throughout Xcode

## Source Control Changes
- Ability to stash code within Xcode
- Ability to cherry-pick a commit

## Design Tools
- Ability to localize assets as well
- Dark and light variants for the icons which is reflected immediately on Storyboards
- SF Symbols!
- Environment overrides and accessibility settings for the active simulator session

## Debugging
- The new device condition section in the devices tab
  - Network conditioner
  - Thermal changes

## Testing
### Test Plans
- Multiple localized test scenarios
- Works for iPad apps for mac and SwiftUI as well

## Simulator Updates
- The new simulator is built on top of metal
  - Metal using apps can use
  - CPU use is reduced up to %90
  - 60 FPS
  - Simulator warm boots are 2x faster
- A standalone watch simulator without the need of an iphone simulator

## Instruments
- Bunch of new lanes for instrumental tools including SwiftUI

## SwiftUI
- `UIViewRepresentable` protocol for SwiftUI previews

### [Back to the Readme](./Readme.md)
