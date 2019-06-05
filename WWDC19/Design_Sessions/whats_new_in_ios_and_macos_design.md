WWDC19
# Table of Contents
=================

   * [What's New in iOS and macOS Design - Tuesday](#whats-new-in-ios-and-macos-design---tuesday)
      * [What's New in iOS Design](#whats-new-in-ios-design)
         * [Colors in Dark Mode](#colors-in-dark-mode)
         * [Semantic Colors](#semantic-colors)
         * [Modal Presentations](#modal-presentations)
         * [Contextual Menus](#contextual-menus)
      * [Designing iPad Apps for Mac](#designing-ipad-apps-for-mac)
         * [Architecture](#architecture)
         * [Toolbars](#toolbars)
      * [Layout](#layout)
      * [Type](#type)
      * [Colors](#colors)
      * [Gestures](#gestures)
      * [App Icons](#app-icons)
      * [Contextual Menus](#contextual-menus-1)
      * [Menu Bars](#menu-bars)

# What's New in iOS and macOS Design - Tuesday
Session materials: https://developer.apple.com/videos/play/wwdc2019/801/

## What's New in iOS Design
- Dark mode
- New card style modal presentation
- Contextual menus

### Colors in Dark Mode
  - ### Semantic Colors
    - Primary, secondary, tertiary, quantinary -> Title, subtitle, placeholder text, disabled text
    - Switching between light and dark mode is not just inverting colors, uses semantic colors to emphasize elements in the same way

- Full color palette under human interface guidelines
- Tint colors get lighter in dark mode, darker in light mode
- Base and elevated colors helps directing the focus of the user on desired areas

### Modal Presentations
- Modals are for switching modes, don't use them just for animations
  - e.g creating or editing events in the calendar app
  - A continuation of the event started in the parent view
- Scrolling the card away is automatic but can be prevented as well for mandatory content focus
- Having buttons like close is still ok =) (they actually suggest this)

### Contextual Menus
- Works on all devices compared to peek and pop which works only on 3D touch available devices
- Consists "Preview" and "Commands"

## Designing iPad Apps for Mac
### Architecture
- Tabbed apps -> Segmented apps
- Document browser based apps and scrollable apps will be transformed automatically in a familiar way onto macOS
- Use translucent backgrounds in sidebars

### Toolbars
- Use toolbars for actions which requires being accessible by being sticky in the toolbar

## Layout
- Use increasing screen space wisely, design accordingly while switching from iPhone -> iPad -> Mac

## Type
- Simpler fonts Medium 13pt, Small 11pt, Mini 9pt
- macOS doesn't support dynamic type
- Mac apps should be more neutral and use default color setups if possible

## Colors
- System colors are mapped to macOS equivalents

## Gestures
- Some gestures won't translate like pull to refresh or side screen swipes
- Other common gestures are mapped in a similar way
- Take advantage of hover states on macOS as well
- Utilize touch bars on macOS

## App Icons
- Take the extra mile to have a refined macOS app to stand among all apps

## Contextual Menus
- Very important and essential in the right click form
  - iOS contextual menus will be translated into right click menus on macOS
- Don't overwhelm
- Be succint, use short terms
- Convey action
- Order carefully
- Group with separators

## Menu Bars
- Catalog all the possible actions
- Assign shortcuts for common actions
