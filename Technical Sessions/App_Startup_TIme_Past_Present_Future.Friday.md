WWDC 2017

Table of Contents
=================

  * [App Startup Time: Past, Present, and Future \- Friday](#app-startup-time-past-present-and-future---friday)
    * [Improving App Startup Time](#improving-app-startup-time)
    * [dyld 3](#dyld-3)
      * [Why ?](#why-)
      * [How ?](#how-)

# App Startup Time: Past, Present, and Future - Friday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/413/

## Improving App Startup Time
  - Do less !
    - Embed fewer dylibs
    - Declare fewer classes/methods
    - Use fewer initializers
  - Use more Swift !!!!
    - Swift avoids most of the pitfalls
    - Swift size improvements
  - Static initializer tool from instruments to check app startup time

## dyld 3
### Why ?
  - Performance
  - Security
  - Reliability
### How ?
  - Move complex operations out of process
  - Make the rest of dyld as small as possible
    - Speeds up launch
    - Reduces attack surface
