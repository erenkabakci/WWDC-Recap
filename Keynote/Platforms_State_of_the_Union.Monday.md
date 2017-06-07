WWDC 2017

Table of Contents
=================

  * [Platforms State of the Union \- Monday 14:30 \-&gt; 16:00](#platforms-state-of-the-union---monday-1430---1600)
    * [Swift Playgrounds 1\.5](#swift-playgrounds-15)
    * [Swift Playgrounds 2](#swift-playgrounds-2)
  * [Tools Updates](#tools-updates)
    * [XCode 9](#xcode-9)
    * [String](#string)
    * [Codable](#codable)
    * [Swift 3\.2 &amp; 4\.0](#swift-32--40)
    * [Obj\-C &amp; Swift interoperability](#obj-c--swift-interoperability)
    * [New indexer](#new-indexer)
    * [New build system](#new-build-system)
    * [Github integration to XCode 9](#github-integration-to-xcode-9)
    * [Sanitizers](#sanitizers)
    * [CI &amp; Testing](#ci--testing)
    * [Wireless Development](#wireless-development)
  * [New APIs](#new-apis)
    * [Drag &amp; Drop](#drag--drop)
    * [Auto resizing table view cells](#auto-resizing-table-view-cells)
    * [Files](#files)
    * [SiriKit](#sirikit)
    * [MusicKit](#musickit)
      * [Built in QR\-Code support from the camera](#built-in-qr-code-support-from-the-camera)
    * [Depth API for Camera and Images](#depth-api-for-camera-and-images)
    * [Vision](#vision)
      * [Face &amp; Landmark Detection](#face--landmark-detection)
      * [Object Tracking](#object-tracking)
      * [Vision &lt;\-&gt; Core ML](#vision---core-ml)
    * [CoreML](#coreml)
    * [Metal 2](#metal-2)
    * [ARKit](#arkit)

# Platforms State of the Union - Monday 14:30 -> 16:00
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/102/

## Swift Playgrounds 1.5
## Swift Playgrounds 2

# Tools Updates

## XCode 9
  - Complete redesign on source editor
    - Markdown editor
    - Smart fix, smart warnings
    - Autogenerate code for protocols
    - Create logic wrappers (available ios)
    - Scrolling faster at 60 fps, 3x faster file opening, 50x faster jump to line
    - Major refactors, includes swift, obj-c, storyboards
      - Extract variables, functions
      - rename refactoring
      - show usages
    - cmd + for zooming
    - Physical file & folder moving
## String
## Codable
  - Encode & decode out of the box
## Swift 3.2 & 4.0
  - Mix and match
## Obj-C & Swift interoperability
  - Increased build time (%40 faster)
  - 2x faster with WMO
## New indexer
  - Index in the background while building
  - Much faster
## New build system
  - Layers atop `llbuild`
  - 2.5x faster build
## Github integration to XCode 9
  - Directly clone in XCode
  - Manage branches & tags etc.
## Sanitizers
  - Main thread API checker
  - Undefined behaviour sanitizers
## CI & Testing
  - Built in XCode server
  - Parallelized `- destination` from CLI
  - Multiple instances of simulators
## Wireless Development
  - Ethernet, wireless, usb

# New APIs

## Drag & Drop
  - New delegate support
    - One for drag
    - One for drop
  - Interact with other apps using same API
  - Available on iPhone BUT, only moving files within the same file is supported

## Auto resizing table view cells

## Files
  - Type filterin
  - Document creation
  - `NSDocument` support

## SiriKit
  - Simulator support
## MusicKit

### Built in QR-Code support from the camera

## Depth API for Camera and Images

## Vision
### Face & Landmark Detection
### Object Tracking
### Vision <-> Core ML
  - Detect custom patterns with machine learning

## CoreML
  - Some complicated shit
  - Hardware optimization
  - Pre-trained models for ML

## Metal 2
  - Support for accelerated ML
  - VR - Steam VR beta support
  - Built-in XCode profilers

## ARKit
  - iPhone 6s & later , iPad Pro & later
  - Camera positioning using Gyro&Accelerometer and leaving the CPU and GPU empty for processing
  - `ARSessionDelegate` & `ARSession` to access data
  - Open sourced plugin from EPIC & Unity for ARKit integration
