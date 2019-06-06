WWDC19
# Table of Contents
=================

   * [Table of Contents](#table-of-contents)
   * [Advances in Networking, Part1 - Thursday](#advances-in-networking-part1---thursday)
      * [Low Data Mode](#low-data-mode)
         * [URLSession &amp; Network.framework](#urlsession--networkframework)
      * [Combine in URLSession](#combine-in-urlsession)
      * [WebSocket](#websocket)
         * [URLSessionWebSocketTask](#urlsessionwebsockettask)
      * [Mobility Improvements](#mobility-improvements)
         * [Wi-Fi Assist in iOS 13](#wi-fi-assist-in-ios-13)
         * [Multipath Transports](#multipath-transports)

# Advances in Networking, Part1 - Thursday
Session materials: https://developer.apple.com/videos/play/wwdc2019/712/

## Low Data Mode
  - User preference to minimize data usage
    - Explicit signal to reduce network data use
    - Per wifi and cellular network
    - Background tasks are deferred in this mode
    - Background app refresh is also disabled

### `URLSession` & `Network.framework`
  - Try large/prefetch with `allowsConstrainedNetworkAccess = false`
  - On failure with `error.networkUnavailableReason == .constrained` try low data mode alternative here

  - Set `prohibitConstrainedPaths` on `NWParameters`
  - Check `isExpensive` in `NWPath`

## Combine in URLSession
```
.debounce()
.removeDuplicates
.filter {}
.map {}
.sink()
```

  - `DataTaskPublisher`
    - Single value publisher
    - Similar to `URLSession.dataTask`
    ```
    .tryCatch {}
    .tryMap {}
    .retry(1)
    .replaceError(with)
    .receive(on: Thread)
    .assign(to)
    ```

## WebSocket
  - Two-way communication over TLS/TCP connection
  - Works with Firewalls and CDNs
  - Proxy support

### `URLSessionWebSocketTask`
  - Compatible with URLSessionTask

- Server-> NWListener
- Client-> URLSessionWebSocketTask

- Webkit -> Javascript Websocket
- URLSession -> URLSessionWebSocketTask
  - Supports authentication and cookies
- Network.framework -> Webseocket Connection & Listener

## Mobility Improvements
### Wi-Fi Assist in iOS 13
  - Cross-layer mobility detection is built into URLSession and Network.framework

- Rethink `SCNetworkReachability` usage
- Control access with `allowsExpensiveNetworkAccess = false`

### Multipath Transports
  - Apple maps and music are now also using this technology as Siri to have a better transition between cellular & wi-fi
