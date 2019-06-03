WWDC 2017

Table of Contents
=================

  * [Modernizing GCD Usage, How to stay on core \- Wednesday](#modernizing-gcd-usage-how-to-stay-on-core---wednesday)
    * [Parallelism: Simultaneously execution of closely related computations](#parallelism-simultaneously-execution-of-closely-related-computations)
      * [Concurrency: Composition of independently executed tasks](#concurrency-composition-of-independently-executed-tasks)
      * [Lock ownership](#lock-ownership)
    * [Using GCD for Concurrency](#using-gcd-for-concurrency)
      * [Serial Dispatch Queue](#serial-dispatch-queue)
      * [Target Queue Hierarchy](#target-queue-hierarchy)
      * [Qualitiy of Service (QoS) and Target Queue Hierarchy](#qualitiy-of-service-qos-and-target-queue-hierarchy)
      * [Event Handling on Many independent Queues](#event-handling-on-many-independent-queues)
    * [Introducing Unified Queue Identity](#introducing-unified-queue-identity)
    * [Modernizing Existing Code](#modernizing-existing-code)
    * [Summary](#summary)

# Modernizing GCD Usage, How to stay on core - Wednesday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/706/

## Parallelism: Simultaneously execution of closely related computations
  - Leverage existing system frameworks
  - Express explicit parallelism with `DispatchQueue.concurrentPerform`
### Concurrency: Composition of independently executed tasks
  - Use case: UI & Networking & Database at the same time
  - Repeatedly bouncing between contexts like network and database can become expensive. Reasons could be,
    - Repeatedly waiting for exclusive access to contented resources
      - Fair Locks: Gives a chance to every thread to run in sequence
      - Unfair Locks: Reserves thread to finish
      - Lock ownership helps resolve priority inversion
### Lock ownership
  - Single owners, no owners, multiple owners

## Using GCD for Concurrency
### Serial Dispatch Queue
  - Mutex
  - FIFO
  - Concurrent atomic enqueue
### Target Queue Hierarchy
  - Serial queues and sources can form a tree
### Qualitiy of Service (QoS) and Target Queue Hierarchy
  - priority inversion resolves waiting problems according to importance. E.g User initiated task will always come first eventhough it is queued afterwards
### Event Handling on Many independent Queues

## Introducing Unified Queue Identity
  - Unified queue identity can block certain threads for priority

## Modernizing Existing Code
  - No mutation past activation
    - Set the properties of inactive objects before activation
      - Source handlers
      - Target queues
  - Protecting the Target Queue Hierarchy
    - Build your queue hierarchy from bottom to top
    - Opt into "static queue hierarchy"

## Summary
  - Not going off core is ever more important
  - Size your work appropriately
  - Choose good granularity of concurrency
  - Modernize your GCD usage
