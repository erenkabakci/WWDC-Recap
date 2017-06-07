WWDC 2017

# Advance in Networking, Part 1 *
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/707/

## Explicit congestion notification (ECN)

Bottleneck - packet transfer is cancelled:

  - Mark packet as congestion experiences.. <-less destructive
    - Reduce Retransmissions
    - Reduce delay
    - Improve UX

  - Smart queue management

### iPv6
  - Networking stack changes
  - New network extension facilities
  - Multipath protocols

### NAT64
  - for providers which does not support iPv6

NEW: TCP/IPv6 in User Space not in Kernel space

## Network Extension Framework

### NEHotspotConfiguration:
  - Setting networks from the app itself..
  - Can be temporary or permanent (You can even set only when this app is used -network settings-)

### NEDNSProxyProvider;
  - DNS over TLS/HTTP

## Multipath Protocols For Mobile devices:

Wifi-Assist since iOS 9

### Multipath TCP: (new)

When you leave home or on poor wifi - > wifi to Cellular link..

  - Improve reliability and UX..
  - Switch between smoothly

#### Public app in iOS 11 to enable MPTCP

##### Handover mode

  - Wifi to cellular vice versa.
  - Minimize cell usage, reliable for persistent connection)
  - Use it for important call which do not use so much data (avoid cellular data over usage)

##### Interactive mode (upcoming beta):

Low latency for low-volume interactive flows.. (wifi-cellular switch)

##### Aggregation mode (upcoming beta):

  It is just a developer mode: (not for customer’s device)
  - Combines link capabilities
  - Available through developer settings
