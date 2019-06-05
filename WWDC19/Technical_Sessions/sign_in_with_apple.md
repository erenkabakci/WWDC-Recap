WWDC19
# Table of Contents
=================

   * [Sign in with Apple - Wednesday](#sign-in-with-apple---wednesday)
      * [Integrating with Your App](#integrating-with-your-app)
         * [Responses](#responses)
      * [Cross-Platform](#cross-platform)
      * [Best Practices](#best-practices)

# Sign in with Apple - Wednesday
Session materials: https://developer.apple.com/videos/play/wwdc2019/706/

- Fast, easy account setup and sign in
  - The app gets ID, Full name and verified email address
- Syncs across devices
- A hidden email address which routes to the actual email
- No password
- 2FA
- Free
- Cross-platform, available on all apple platforms
  - Javascript API makes it possible to use on windows and android as well

## Integrating with Your App
- Button -> Authorization -> Verification -> Handling Changes

- `ASAuthorizationAppleIDButton()` and hook an action to it
- `ASAuthorizationAppleIDProvider().createRequest()` & `.requestedScopes = [.fullName, .email]`
- Authorization callbacks to process the result

  - ### Responses
    - UserID
      - Uniques, stable, team scoped user ID
    - Verification data
      - Identity token, code
    - Account information (optional)
      - Name, verified email
    - Real user indicator

- Handling session changes via the notification center
- Integrates with iCloud Keychain passwords

## Cross-Platform
- Javascript SDK
  - Simple browser-based login
  - Similar to native API

## Best Practices
- Only require account setup when necessary
- Use real user indicator for best new account experience
- Always use the button API
