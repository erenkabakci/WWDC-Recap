WWDC 2017

# Updating Your Apps to iOS11 * Tuesday 16:10
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/204/

## UIBarItem
  - UI changes when long pressed to tabbar item
  - `UIBarItem.landscapeImagePhone`
  - `UIBarItem.largeContentSizeImage`
## Controlling When Large Titles Display
  - `navigationBar.prefersLareTitles`
  - `navigationBar.largeTitleDisplayMode` enum
## Integrated UISearchControlle with Navigation
  - `navigationItem.searchController`
  - `navigationItem.hideSearchBarWhenScrolling`
## UIToolbar and UINavigationBar supports AutoLayout
  - Items are compatible with autolayout
  - Zero-sized custom views must be avoided. Provide size,
    - Constraints with-height ||
    - Implement `intrinsicContentSize` ||
    - Connect your subviews via constraints
## Layout Margins
  - Easier insets handling. Supported on RTL as well. `.left` is aligned with `.leading`
    - directional layout margins
    - system minimum layout margins
  - `topLayoutGuide` and `bottomLayoutGuide` is deprecated. Safe area is introduced. Inset could be modified with viewSafeArea insets.
## UIScrollView
  - `frameLayoutGuide` for `UIScrollView` stays fixed
## UITableView
  - `seperatorInset` in `UITableView` allows editing insets for readable area. This is always relative to the orientation meaning that will be resizing automatically for whole screen.
## Swipe Actions
  - New look and feel automatically for all table views
  - Supports full swipe to delete for iOS 11-linked apps
  - Leading and trailing swipe for different actions via delegate methods
