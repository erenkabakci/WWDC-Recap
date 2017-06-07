WWDC 2017

# What's New in SiriKit * Wednesday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/214/

## SiriKit
 - Last year: `Intents`, watchOS 3.0
 - Debugging on simulator since 10.3.2

## Easy development/debugging
 - You don't have to talk to `Siri` each time.
 Preset sentence : “show my XXX code”

## Domains and intents

### Payments (was there)
  - Send/request
  - Search& pay bills(10.3.2),

### Accounts (new - type of accounts or companies -checking))
  - Transfer money, check the balance in your account.. (`INTransferMoneyIntent`, `INSearchForAccountsIntent`)

## Lists and Notes:
### Lists:
  - Search in the list
  - Complete/update a task
  - Set a reminder
  - Create/add task

### Notes:
  - Create a note (title, groupName, content)
  - Append/delete a note
  - Search in a note, sort (by Date)/filter (date/completed/location etc)

## Visual codes
  - Barcodes/QR codes/contact code etc - “show my XXX code”
  - `INVisualCodeIntent` (contact, requestPayment, sendPayment)

## Steps
  1. Resolve
    - Use case: unknown code type / contact code type
  2. Confirm
    - Use case: check if user is logged in if the code needs to be shown for an authorised user
  3. Handle (only required method) : return the visualCodeImage

## Customizable UI
### Configure View
 - Set size
 - Replace a view or multiple views with a custom view
 - Custom Interactive Behaviour


## Additional Enhancements
### Background workout app intent handling
  - Application continue UserActivity
  - Extension-App (handleInApp for extension, HandleIntent for app)

### Alternative App Names
- In the .plist `INAlternativeAppNames` array
