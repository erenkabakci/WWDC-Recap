WWDC19
# Table of Contents
=================

   * [Advances in App Background Execution - Wednesday](#advances-in-app-background-execution---wednesday)
      * [Overview of Background Execution](#overview-of-background-execution)
         * [Why Do We Enter Background State?](#why-do-we-enter-background-state)
      * [Important Considerations for Background Execution](#important-considerations-for-background-execution)
      * [Background Execution Best Practices](#background-execution-best-practices)
         * [Example: The messaging app](#example-the-messaging-app)
      * [Deferrable Work](#deferrable-work)
         * [BackgroundTasks](#backgroundtasks)
         * [Background App Refresh Task](#background-app-refresh-task)
      * [Additional Considerations](#additional-considerations)

# Advances in App Background Execution - Wednesday
Session materials: https://developer.apple.com/videos/play/wwdc2019/707/

## Overview of Background Execution
### Why Do We Enter Background State?
- App requests
- Specific event triggers. e.g: The user entering to a specific region or an updated health data

## Important Considerations for Background Execution
- Power
  - More execution = more battery drain
- Performance
  - Smart CPU limits to minimize the impact to the user
- Privacy

## Background Execution Best Practices
### Example: The messaging app
  - Sending messages: User expects immediate completion even if they leave the app before sending a message
    - Background task completion
      - Gives app additional time to run in the background before being suspended
      - Use expiration handlers if the event is still not completed within the time frame
  - Phone Calls
    - VoIP push notifications
      - Special type of push that launches your app
      - Must report incoming call with CallKit in the callback
      - Set apns-expiration on push to 0 or something small
      - Prefer a banner? Use standard pushes
  - Muted threads: The user may have many different threads and not want alerts for the specific thread
    - Use background pushes
      - Send push with `content-available: 1` without `badge` or `sound`
      - must set `apns-priority = 5` or the app will not launch
  - Download past attachments: User signs into the account and would like to get the older content once the app is backgrounded
    - Discretionary Background URL session
      - Allows the system to defer the download until a better time
      - Batching analytics to send later is also another good candidate for this

## Deferrable Work
- Syncing
- Database cleanup
- Backups

  - ### `BackgroundTasks`
    - A new framework for scheduling bg work
    - Available on all platforms

    - Several minutes of runtime at system-friendly times
      - e.g Maintenance work or Core ML training

  - ### Background App Refresh Task
    - A new API with the same policies
      - 30 secs of runtime

- `BGProcessingTask` & `BGAppRefreshTask`
- Old UIApplication fetch API is deprecated, and not supported on Mac
- Adding capability under project settings (Signing & Capabilities)
- `requiresNetworkConnectivity: Bool` & `requiresExternalPower: Bool`
- Ability pause the debugger on simulator to simulate execution of tasks at a given time throughout the debugger!

## Additional Considerations
- Don't set `earliestBeginDate` too far into the future
- Ensure files are accessible while the device is locked
  - `FileProtectionType.completeUntilFirstUserAuthentication`
- UIScene apps should call `UIApplication.requestSceneSessionRefresh(_:)`
- Consider calling  `BGTaskScheduler.submit()` on a BG queue if submitting at launch
