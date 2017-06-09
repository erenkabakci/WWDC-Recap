WWDC 2017

Table of Contents
=================

  * [Writing Energy Efficient Apps \- Friday](#writing-energy-efficient-apps---friday)
    * [Location](#location)
    * [Graphics](#graphics)
      * [macOS:](#macos)
    * [Background processing](#background-processing)
    * [Navigation background mode](#navigation-background-mode)
    * [Energy debugging tools](#energy-debugging-tools)

# Writing Energy Efficient Apps - Friday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/238/
Provided by @mihriminaz

## Location
  - Accuracy level. Be mindful about your update rate

## Graphics
  - Minimize screen updates
### macOS:
  - Minimize use of discrete GPU ( MTLCopyAllDevices - only use when animation suffers or function isn’t working)
  - If you use OpenGL NSSupportAutomaticGraphicsSwitching -info.plist
  - Minimize screen updates
  - CPU
    - Identify tasks
    - Do work quickly and efficiently
    - Avoid timers
    - Set leeway

## Background processing
  - Avoid as much as possible
  - Finish work quickly and efficiently
  - Use background app refresh for updating content
  - Use completion handler so that you complete
  - New - PushKitAPI - has completion() now.

## Navigation background mode
  - CPU limits like workout
  - Minimize Networking

## Energy debugging tools
  - Energy Gauges
  - Debug your app for
    - Launch & idle
    - Background
  - E.g: For a navigation app: debug for,
    - Search for and address
    - Get directions
    - Navigate
