WWDC19
### [Back to the Readme](./Readme.md)

# Table of Contents
=================

   * [Introducing SF Symbols - Tuesday](#introducing-sf-symbols---tuesday)
      * [SF Symbols App](#sf-symbols-app)
      * [Technical Details](#technical-details)
         * [Tips](#tips)

# Introducing SF Symbols - Tuesday
Session materials: https://developer.apple.com/videos/play/wwdc2019/206/

- Vector based
- Has all the weights of a font family
- More than a thousand of them!
- Aligned horizontally and vertically to fit along with the text
- A new property called scale
  - While the font staying the same, emphasize of a symbol can change and it affects the size as well.
  - Small, medium, large scales
- Can be localized as well

- Some of the historically used system icons are now also using sf symbol designs

## SF Symbols App
- A good browser for all available SF symbols
- Let's you create your own symbol set throughout the sf symbols app. Exportable.
  - The ready template is in SVG format can be used in other apps like Sketch

## Technical Details
- A new API: `UIImage(systemName: "")`for already available SF Symbols
- `UIImage(named: "")` for custom created symbols
  - Symbols take precedence over icons or images due to the same method name. This allows the usage of new symbols on iOS 13 without adding extra version check code.

- `imageView.preferredSylmbolConfiguration = The new custom configuration`
- Symbol point sizes are typhographical != screen point sizes
- Symbols should be using symbol points like fonts. A 28pt symbol could be 32x33 in dimension but this is irrelevant now
- Possibility add a baseline to an image with `UIImage.withBaselineOffsetFromBottom(3.5f)`
- `button.setPreferredSymbolConfiguration()` for button symbol configurations
- `SymbolScale.large` changes into `SymbolScale.medium` from portrait to landscape orientation
- `UIImage.withTintColor(.redColor, renderingMode: .alwaysOriginal)` This is not available in the first macOS beta

### Tips
- Prefer horizontal and vertical centering
- Build layouts smallest to largest
- Be flexible: image sizes can change
- Caching images rarely helps performance
- Avoid rasterizing!

### [Back to the Readme](./Readme.md)
