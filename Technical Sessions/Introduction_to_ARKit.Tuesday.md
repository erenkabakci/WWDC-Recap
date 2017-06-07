WWDC 2017

# Introduction to ARKit * Tuesday

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
