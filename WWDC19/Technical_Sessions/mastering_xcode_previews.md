WWDC19
# Table of Contents
=================

   * [Mastering Xcode Previews - Thursday](#mastering-xcode-previews---thursday)
      * [PreviewProvider Protocol](#previewprovider-protocol)
      * [Development Assets](#development-assets)

# Mastering Xcode Previews - Thursday
Session materials: https://developer.apple.com/videos/play/wwdc2019/233/

- Xcode builds a preview of the current view separately and injects the view with dynamic replacement to show in the preview mode

## `PreviewProvider` Protocol
  ```
  # if DEBUG
  public enum SomePreviews: PreviewProvider {
    public static var previews: some View {
      Group {
        SomeView()
        .device() // Different devices to be shown in the preview
        .previewLayout(.sizeThatFits) // Just shows the specific view with the intrinsic size it gets,

        SomeView()
        .environment(|.sizeCategory, .extraLarge) // To simulate dynamic text sizes on the preview
        .previewDisplayName() // to show the selected preview option in the preview mode
      }
    }
  }
  #endif
  ```
  - Wrap previewable views into forEach to simulate different cases of an iterable like dynamic font types

## Development Assets
  - Target settings -> General -> Development Assets

## Populate The Preview with Fixtures (JSON)
  - Parse a given JSON with a simple decoder to have a variety of data to be able to check different cases on the preview UI

- Pinning a preview will make it sticky across other views to make it visible everywhere

### Create a New Preview File for an Existing View Controller
  - A separate previews file
  ```
  // Implement following two protocols to make the vc previewable
  PreviewProvider
  static var previews

  UIViewControllerRepresentable
  func makeUIViewController() {
    // load from storyboard or instantiate
  }

  func updateUIViewController() {}
  ```

- Make your apps scene aware

![Image](./scene_delegate.png)
