WWDC 2017

Table of Contents
=================

  * [Building Visually Rich User Interfaces \- Thursday](#building-visually-rich-user-interfaces---thursday)
      * [This session explicitly requires the session video to be watched and code pieces to be followed \- Sorry :/ There are many cool tips being mentioned and worth checking](#this-session-explicitly-requires-the-session-video-to-be-watched-and-code-pieces-to-be-followed---sorry--there-are-many-cool-tips-being-mentioned-and-worth-checking)
    * [Overview](#overview)
    * [UIKit Customization](#uikit-customization)
    * [Core Image](#core-image)
    * [Core Graphics](#core-graphics)
    * [Core Animation](#core-animation)
    * [SpriteKit](#spritekit)
    * [SceneKit](#scenekit)

# Building Visually Rich User Interfaces - Thursday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/235/

### This session explicitly requires the session video to be watched and code pieces to be followed - Sorry :/ There are many cool tips being mentioned and worth checking

## Overview
This sample collects several demos from the WWDC 2017 session Building Visually Rich User Experiences. It illustrates basic usage of several frameworks that can be used to enhance your user interface, from customization of UIKit controls to SceneKit.

## UIKit Customization
Many UIKit controls have properties that allow you to customize their visual appearance. In this portion of the sample, the track images of UISlider are configured to more clearly convey the slider's purpose in an appealing way.

## Core Image
Core Image is a powerful framework for manipulation of images. This demo shows how to interactively adjust the white balance of a photograph using the CITemperatureAndTint filter.

## Core Graphics
Sometimes, you need to need to draw elements of your user interface at run-time, and Core Graphics provides numerous functions for drawing graphical primitives like rectangles, curves, and text. This demo shows how to construct and fill a path using Core Graphics with the UIGraphicsImageRenderer class introduced in iOS 10.

## Core Animation
Core Animation is a fundamental framework that manages all of the graphical content of your views and composites it together into the final image on the screen on iOS. Building on the previous demo, this demo shows how to make Core Animation layers, set their contents to an image drawn with Core Graphics, and animate them in response to user action (a button press).

## SpriteKit
SpriteKit is a rendering and animation framework that includes physics simulation and event-handling, allowing you to create 2D sprite-based games. In this demo, the particle system feature of SpriteKit is used to render a large number of animated particles.

## SceneKit
SceneKit combines a high-performance rendering engine with an API for import, manipulation, and rendering of 3D assets. In this demo, a 3D model is imported, and numerous instances of the model are rendered and simulated physically.
