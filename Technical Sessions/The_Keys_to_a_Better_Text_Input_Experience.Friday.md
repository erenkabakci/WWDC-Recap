WWDC 2017

Table of Contents
=================

  * [The Keys to a Better Text Input Experience \- Friday](#the-keys-to-a-better-text-input-experience---friday)
    * [Integrating the Keyboard into Your App](#integrating-the-keyboard-into-your-app)
      * [Undocked and Split Keyboards](#undocked-and-split-keyboards)
      * [Working with non\-scrolling views](#working-with-non-scrolling-views)
    * [Making Your App Feel Magical](#making-your-app-feel-magical)
      * [Multilingual \- Remembering User Selected Keyboard](#multilingual---remembering-user-selected-keyboard)
      * [UIResponder to Remember Keyboard](#uiresponder-to-remember-keyboard)
      * [Being Aware of Context](#being-aware-of-context)
      * [Smart Quote and Smart Dash](#smart-quote-and-smart-dash)
      * [Smart Insertion and Deletion](#smart-insertion-and-deletion)
      * [Marked Text](#marked-text)
      * [Hardware Keyboard](#hardware-keyboard)
    * [Creating Custom Input Views](#creating-custom-input-views)
    * [Other Third Party Keyboard APIs](#other-third-party-keyboard-apis)

# The Keys to a Better Text Input Experience - Friday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/242/

## Integrating the Keyboard into Your App
### Undocked and Split Keyboards
  - Being in the right space
### Working with non-scrolling views
  - Use keyboard anchors in auto-layout
  - Use `intrinsicContentSize`

## Making Your App Feel Magical
### Multilingual - Remembering User Selected Keyboard
### UIResponder to Remember Keyboard
  - `TextInputContextIdentifier`
### Being Aware of Context
  - `UITextContentType`
    - Provides contextual predictions
    - Displays on QuickType bar
    - QuickType Sources are shown in the bar
  - Context Types for Password AutoFill
    - `UITextContentTypeUsername` & `UITextContentTypePassword`
    - Check password autofill session
### Smart Quote and Smart Dash
  - Typographical automatic conversions
### Smart Insertion and Deletion
  - Automatic whitespace handling for context being added/deleted

All these are turned by on default but `UITextInputTraits`
  - `.default`, `.yes`, `.no`

### Marked Text
### Hardware Keyboard
  - Override the key commands in UIResponder via `UIKeyCommand` to support actions like CMD-Z

## Creating Custom Input Views
  - Subclass `UIInputViewController`

## Other Third Party Keyboard APIs
  - Incorporate the system input menu via globe icon
  - Personalization with the supplementary lexicon
  - Multilingual
