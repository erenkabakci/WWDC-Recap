WWDC 2017

Table of Contents
=================

  * [What's New in Location Technologies \- Thursday](#whats-new-in-location-technologies---thursday)
    * [CLGeocoder Improvements](#clgeocoder-improvements)
    * [Heading (facing) / course (aiming to go)](#heading-facing--course-aiming-to-go)
    * [Indoor positioning Improvements](#indoor-positioning-improvements)
    * [Continuous Background Location](#continuous-background-location)
    * [Best practices for workout apps:](#best-practices-for-workout-apps)
    * [Authorization and Usage Reporting:](#authorization-and-usage-reporting)
    * [Motivations for Requiring Always](#motivations-for-requiring-always)
    * [Best practices](#best-practices)
    * [Location Usage Indicators](#location-usage-indicators)

# What's New in Location Technologies - Thursday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/713/
Provided by @mihriminaz

## CLGeocoder Improvements
  - Updated contacts framework
  - Geocode CNPostalAddress
  - Obtain a CNPostalAddress from a CLPlaceMark
  - Address dictionary methods are deprecated..
  - Supports geocoding with a locale overrides user preference

## Heading (facing) / course (aiming to go)
  - Better heading estimates.
  - Fully automatic
  - Use CMDeviceMotion for raw heading (for AR etc)

## Indoor positioning Improvements
  - Accuracy (>=gps quality)
  - Responsiveness - detects floors quickly
  - Availability - even venue is not covered
  - Interoperability - wireless accesories

## Continuous Background Location
  - Now available on watchOS (previously available through HealthKit)
  - Valuable specifically for navigation and fitness apps
  - Workout apps must adopt - otherwise it won’t access to user location
 (3 steps: 1. Background modes-location updates, 2. locationManager.allowsBackgroundLocationUpdates = true 3. When app Is foreground locationManager.startLocationUpdating() -will continue on background)

## Best practices for workout apps:
  - Use HKWorkoutSession
  - Use CMPedometer for pedestrian distance..

## Authorization and Usage Reporting:
  - Now
    - When-in-use or always
  - New
    - When-in-use authorization questioned to user

## Motivations for Requiring Always
  - Developer confusion
  - Pursuit of magical experiences : always
  - WhenInUse support is required!
  - `NSLocationWhenInUseUsageDescription` - otherwise always authorization won’t work as well..
  - `NSLocationAlwaysAndWhenInUseUsageDescription`

## Best practices
  1. Use all:
  ```
  NSLocationWhenInUseUsageDescription
  NSLocationAlwaysAndWhenInUseUsageDescription
  NSLocationAlwaysUsageDescription
  ```

  - Because for <11 iOS version devices to install your app
  - To give options to the user

  2. Ask for the user only the type of authorization when you need that type
  First ask when in use, than always -> can be a better transition for user

  - watchOS will ask for authorization prompt on watch itself.. NEW!!

## Location Usage Indicators
  - New arrow policy
    - Hollow arrow when requesting
    - Solid arrow when receiving
  - Blue status bar for Always apps
  - Matches user expectations
