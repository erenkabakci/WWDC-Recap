WWDC 2017

Table of Contents
=================

  * [Data Delivery with Drag &amp; Drop \- Thursday](#data-delivery-with-drag--drop---thursday)
    * [NSItemProvider](#nsitemprovider)
    * [Progress &amp; Cancellation](#progress--cancellation)
    * [Maximize Compatibility](#maximize-compatibility)
    * [NSItemProviderReading, \-Writing Protocols](#nsitemproviderreading--writing-protocols)
      * [NSItemProviderWriting](#nsitemproviderwriting)
      * [NSItemProviderReading](#nsitemproviderreading)
    * [Advanced Topics](#advanced-topics)
      * [Data Marshaling](#data-marshaling)
      * [Progress &amp; Cancellation on the Provider Side](#progress--cancellation-on-the-provider-side)
      * [Per\-Representation Visibility](#per-representation-visibility)

# Data Delivery with Drag & Drop - Thursday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/227/

## `NSItemProvider`
  - Providing data
  - `tableView performDropWith coordinator` delegate

## Progress & Cancellation
  - `progress.fractionCompleted` & `progress.isFinished` properties for UI
  - `progress.cancel()` -> propagates error in completion
  - One `Progress` object per load request

## Maximize Compatibility
  - One `NSItemProvider` = one 'thing' being dragged
  - Multiple representations
  - Fidelity order
    - Highest fidelity first
  - Use concrete uniform type identifiers
    - Abstract item
      - `public.utf8-plain-text`
      - `public.png`
      - Private type identifiers `com.yourcompany.vector-drawing`

## NSItemProviderReading, -Writing Protocols
### `NSItemProviderWriting`
  - `writableTypeIdentifiersForItemProvider` array with highest fidelity order
  - `loadData(withTypeIdentifier...)`
### `NSItemProviderReading`
  - `readableTypeIdentifiers` array in fidelity order as well
  - `public init(itemProviderData...)`

## Advanced Topics
### Data Marshaling
  - Providing
    - As `NSData`
    - As a file or folder
    - As a reference into a file provider
  - Retrieving
    - Copy as `NSData`
    - Copy as file or folder
    - Attempt to open file in place
### Progress & Cancellation on the Provider Side
  - Return your own `Progress`
### Per-Representation Visibility
  - Restrict visibility
    - To same application
    - To same team
    - To everyone
  - Team Data
    - `teamData` property up to 8 KB of metadata exclusive to your team if needed
  - Suggested Name
    - `suggestedName` property
