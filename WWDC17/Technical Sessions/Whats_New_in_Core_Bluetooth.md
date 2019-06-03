WWDC 2017

Table of Contents
=================

  * [What's New in Core Bluetooth \- Thursday](#whats-new-in-core-bluetooth---thursday)
    * [Enhanced Reliability](#enhanced-reliability)
      * [State Preservation and Restoration](#state-preservation-and-restoration)
      * [Write Without Response](#write-without-response)
    * [Platform Support](#platform-support)
    * [L2CAP Channels](#l2cap-channels)
    * [Best Practises](#best-practises)
      * [Time to Discover](#time-to-discover)
      * [Reconnecting devices](#reconnecting-devices)
      * [Service Discovery Speed](#service-discovery-speed)
    * [Getting the most out of Core Bluetooth](#getting-the-most-out-of-core-bluetooth)
      * [Extended Data Length](#extended-data-length)
    * [Summary](#summary)
    * [Key Takeaways](#key-takeaways)

# What's New in Core Bluetooth - Thursday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/712/

## Enhanced Reliability
  - Backgrounded apps
    - iOS Apps can continue using Core Bluetooth in background - Finally !
  - `CBCentralManager` Restoration
    - Will look for devices to keep the connection established continuously
### State Preservation and Restoration
  - Work across device reboot or Bluetooth system events - Even after a reboot connection will be preserved
    - This is trying to ask for as few system resources as possible
### Write Without Response
  - Write without response would be dropped due to memory pressure
  - New property will tell your app if more data can be set

## Platform Support
  - watchOS 4 is now supported which will eliminate the need to bring out your phone
  - 15 ms minimum connection interval
  - State preservation and restoration on iOS
  - tvOS
    - Foreground app only
    - Central role only
    - Minimum 30 ms connection interval
  - watchOS
    - Access dictated by system runtime policies
    - Same things for tvOS applies to here
    - Supported on Apple Watch Series 2

## L2CAP Channels
  - L2CAP Channels -> stream of data between devices
    - First time we can use them
  - Peripheral side L2CAP
    - Listen for incoming L2CAP Channels

## Best Practises
### Time to Discover
  - Use the shortest advertising interval possible
  - Optimize for when users are trying to use your accessory
  - See the Bluetooth Design Guidelines for power-efficient advertising intervals
### Reconnecting devices
  - No need to scan for a peripheral for reconnect
  - Retrieve the peripheral and directly connect
### Service Discovery Speed
  - Use as few services/characteristics as possible
  - Group services by UUID size
    - Group 16 bit and 128 bit services together to get the most out of one badge in one time
  - Support GATT Caching
  - Use "Service Changed"

## Getting the most out of Core Bluetooth
  - Write without response - again
    - Use all available connection events to transmit
    - Takes advantage of larger Connection Event Length
### Extended Data Length
  - New Feature in Bluetooth 4.2
  - Much larger packets
  - Throughput (kbps) is increased from 2.5 to ~400 !!!

## Summary
  - Request a shorter connection interval
  - Update to latest BLE

## Key Takeaways
  - Check out State Restoration
  - Expand your app to tvOS and watchOS
  - Use L2CAP for stream protocols or large data transfers
