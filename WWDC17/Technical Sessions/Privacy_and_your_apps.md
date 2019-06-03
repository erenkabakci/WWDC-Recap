WWDC 2017

Table of Contents
=================

  * [Privacy and Your Apps \- Monday](#privacy-and-your-apps---monday)
  * [Best practises](#best-practises)
    * [CoreLocation \- When In Use Prompts](#corelocation---when-in-use-prompts)
    * [Photos](#photos)
    * [CoreNFC](#corenfc)
    * [Microphone \- WatchOS](#microphone---watchos)
    * [MusicKit](#musickit)
    * [Safari View Controller \- iOS11](#safari-view-controller---ios11)
  * [Features](#features)
    * [On Device processing](#on-device-processing)
    * [DeviceCheck](#devicecheck)
      * [Best practises](#best-practises-1)
  * [Intelligent Tracking Prevention on Safari](#intelligent-tracking-prevention-on-safari)
  * [Differential Privacy](#differential-privacy)

# Privacy and Your Apps - Monday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/702/

# Best practises
  - UUID
  - Vendor Identifier

## CoreLocation - When In Use Prompts
  - Support when in use location authorization
    - `NSLocationWhenInUseUsageDescription`
    - `NSLocationAlwaysUsageDescription`
## Photos
  - Image picker without prompting for access
  - Write only support
    - Ability to add items to photo library
## CoreNFC
  - New api for NFC usage
## Microphone - WatchOS
  - Recording allowed in the background
  - Microphone active indicator on watch face
## MusicKit
  - New prompts for MusicKit access
## Safari View Controller - iOS11
  - Safari and other apps get their own cookies and website data
  - Clearing website data in Safari also clears the data in the app

# Features
## On Device processing
  - Allows you to operate locally rather than on server for better privacy
  - Works anywhere
  - No network latency
  - More performance
  - Frameworks that makes it easier
    - CoreML
      - Allows you to use Pre-trained neurol networks
    - VisionKit
    - ARKit
    - NLP (Natural Language Processing)
## DeviceCheck
  - Eliminates collecting unnecessary data for device <-> user pairing
  - Two bits and a timestamp assigned for determining states
  - No need for redundant entries in the keychain for states like,
    - If a user finished trial period
    - Is this user reinstalling
    - Is this device transferred to someone else using those 2 bits

  `Send device token, transaction_id, timestamp`
  `Receive the states for those two bits from apple along with the timestamp`

### Best practises
  - Use platform supported IDs
    - App ID, Vendor ID, Advertising ID

# Intelligent Tracking Prevention on Safari
  - Dynamically detects online Tracking
    - On-Device classifier
  - Hinders Tracking
    - Isolates
    - Periodically purges
  - Ensure your analytics package does not rely on third party cookies

# Differential Privacy
