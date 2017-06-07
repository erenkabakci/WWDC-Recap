WWDC 2017

# Debugging with XCode 9 * Wednesday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/404/

## Development: Unplugged
  - Wireless development over wi-fi
  - appleTV is also supported
  - iPhone, iPad, iPhone touch using iOS 11
  - Xcode, instruments, accesibility inspector, console, configurator
  - Possible to attach to a already running session. Awesome !
### Who is it for ?
  - AR, VR, and camera app devs
  - Motion-sensing and fitness app devs
  - Accessory makers
  - Developer convenience
### How to setup ?
  - XCode -> Devices & Simulators -> Connect via network (a globe icon appears next to your device)
  - Home and business networks don't require any configuration
  - More complex networks
    - Connect via IP Address (corporate workplace networks)
    - For more information wireless development docs

## Instruments and Profiling
  - Allows pinning certain processes to compare CPU, GPU usage

## Breakpoints
  - Double-click to a breakpoint for more customization
  - Code completion for breakpoint condition and action field
  - Alternative indicator for breakpoints with additional options
  - Search & filter for breakpoints

## View Controller Debugging
  - View controllers are now part of live view debugging

## SpriteKit Debugging
  - SpriteKit layers are shown in view debugging as well

## SceneKit Debugging
  - SceneKit snapshots are shown in view debugging
  - SceneKit editor is available for specific scene and different camera options

## DEBUGCEPTION
  - SceneKit allows snapshots of memory graphs which allows debugging XCode inside an XCode which is inside another XCode :D
