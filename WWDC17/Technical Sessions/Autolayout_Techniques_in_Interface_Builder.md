WWDC 2017

Table of Contents
=================

  * [Auto Layout Techniques in Interface Builder \- Friday](#auto-layout-techniques-in-interface-builder---friday)
    * [Dynamic Type](#dynamic-type)
    * [Safe Areas](#safe-areas)
      * [Proportional Positioning](#proportional-positioning)
    * [Adaptive Layout Using Stack View](#adaptive-layout-using-stack-view)

# Auto Layout Techniques in Interface Builder - Friday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/412/

## Dynamic Type
  - Layout changes with outlets
  - Animate using transform
  - New vertical spacing baseline constraint
## Safe Areas
  - Top and bottom layout guide is deprecated
  - Safe area works under navigation bar, centralized content will always stay in center even when the orientation changes
  - Safe area layout guide checkbox
  - Property on UIView
  - iOS Storyboards
    - Constraints automatically update
    - Backwards compatible for older XCode versions
  - Attribute inspector for a constraint now shows nearby views to relate
### Proportional Positioning
  - Use spacer views when needed in IB
    - Make sure they are hidden so they are not rendered and acts just as a guide
## Adaptive Layout Using Stack View
  - Standard spacing for stack views in attribute inspector
  - Toggle on/off constraints from the right bar to check if they are the reason for the conflict
  - Size class based hidden property for views inside UIStackView. This allows to hide certain views for different orientations - WOW ! XCode9
