WWDC19
#

# Modernizing Your UI for iOS 13 - Wednesday
Session materials: https://developer.apple.com/videos/play/wwdc2019/224/
A sample project with complex options will be available here.

## Effective from April 2020
- Launch images are dropped completely, launch storyboards are the only way to go
- iOS 13 will always stretch apps to the fullscreen of the current device, no more empty bars at the top and the bottom
- Support split screen multitasking

## New Bar Appearance
- Free when you link against iOS13
```
let appearance = UINavigationBarAppearance()

appearance.configureWithOpaqueBackground()

appearance.titleTextAttributes = []
appearance.largeTitleTextAttributes = []

navigationBar.standardAppearance = appearance

// Navigation bar appearances
.standardAppearance, .compactAppearance, .scrollEdgeAppearance

// button appearances
.buttonAppearance, .doneButtonAppearance
```

`UIToolbarAppearance` & `UITabBarAppearance`

- Similar things applies to individual navigation Items for a specific navigation bar appearance for a single view in the hierarchy
`navigationBar.standardAppearance().copy`

## New Presentation Styles
- They stack on top of each other like a deck
- Dynamic readable width for the presented sheet

- `UIModalPresentationStyle.automatic` -> Resolving to different styles based on the parent view that are presenting
- `UIModalPresentationStyle.pageSheet` -> Automatic resolves to this one for custom view controllers
- `UIModalPresentationStyle.formSheet`
- `.fullScreen` if this is desired intentionally
- `.popover` to get the built in popover style

- Pull to dismiss in sheets are supported out of the box
  ```
  // UIAdaptivePresentationControllerDelegate

  func draftDidChange() {}
  func presentationControllerDidAttemptToDismiss(_:) {
    // Ideally present an action sheet here to warn the user
  }
  func shouldDismiss() {}
  func willDismiss() {}
  func didDismiss() {}
  ```
## Share Extensions
- These will automatically become sheets

- Use sheets
- Implement the modal flow

## Search
- `UISearchController` scope and search button are finally can be hidden!!!
- `UISearchTextField` is finally a normal UITextField which can be easily customized!!!
- `searchController.showSearchResultController` let's to show/hide results in the built in controller

### Search Tokens
- Available on any `UISearchTextField`
- Copy & Paste
- Drag & drop these tokens
- Always precedes text
- Can be selected and deleted
- Mixed selections are allowed

### Creating Tokens
- `UISearchToken()`
- `field.replaceTextualPortion -> with the token`

### Ranges and Positions
- `.textualRange` only gives the range of a piece of text without a token preceding

## Gestures
### Selection Gestures in Custom Text Views
  - ### `UITextInteraction` -> allows adding native text editing actions to a custom textView as long as `UITextInput` protocol is conformed
    - Three lines of code
    - Editable and non-editable text interactions
    - Use UITextInput protocol to control selection UI

### Multiple Selection Gestures in Tables and Collections
  - Quickly select batch items in collection and tableViews
    - Two finger and slide down will put the view to the edit mode and pan across the area to select the cells!
    - Hold shift or cmd key on a hardware keyboard will do the same on these views
    - "Select" turns into "Cancel" or "Done"
    - Show action buttons after multiple selection is triggered
### Editing Gestures
