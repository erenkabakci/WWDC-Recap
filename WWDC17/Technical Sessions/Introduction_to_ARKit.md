WWDC 2017

Table of Contents
=================

  * [Introduction to ARKit \- Tuesday](#introduction-to-arkit---tuesday)
    * [ARKit](#arkit)
    * [Getting Started](#getting-started)
      * [ARSessionConfiguration](#arsessionconfiguration)
      * [ARSession](#arsession)
    * [World Tracking](#world-tracking)
      * [Content Technology](#content-technology)

# Introduction to ARKit - Tuesday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/602/

## ARKit
  - iOS (devices with A9 chip and up)
  - Tracking
  - Scene understanding
    - Plane detection,
    - Hit-testing
    - Light estimation
  - Rendering
    - Easy integration
    - Supports custom rendering with Metal template from XCode
  - Unity & Unreal will be fully supporting

## Getting Started
  - Processing -> ARKit
  - Rendering -> SceneKit, Metal, SpriteKit

  - `ARConfiguration` -> `ARSession` -> instances of `ARFrame`
### `ARSessionConfiguration`
  - Checking for availability
  - Enabling/disabling
### `ARSession`
  - Manage AR processing using `pause()` and `run()`
  - `ARAnchor`
    - Real world positioning
    - Add/remove via `ARSession`

## World Tracking
  - Add as a configuration to the session `ARWorldTrackingSessionConfiguration`

### Content Technology
  - Comes as an option while creating a new ARKit project. This defines the rendering method.
