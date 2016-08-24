# Dimelo Android master #

## Dimelo Android 1.2.4 (August 24th, 2016) ##
- Fix: Messages are now correctly received and sent after internet recovery (when starting offline).

## Dimelo Android 1.2.3 (August 3rd, 2016) ##
- Feature: It is now possible to refresh the number of unread messages from anywhere in the application by using the method fetchUnreadCount.

## Dimelo Android 1.2.2 (July 11th, 2016) ##
- Fix: Upgrade gradle to fix potential issues with native libraries.

## Dimelo Android 1.2.1 (July 5th, 2016) ##
- Fix: "Share" feature (removed hard-coded reference to autorithy `com.dimelo.fileprovider`).
- Fix: Use custom inherited FileProvider class to prevent conflicts.


## Dimelo Android 1.2.0 (May 19th, 2016) ##
- Feature: Remove local cache file
- Feature: Allow customization of attachments icon
- Fix: Compatibility with a wider range of Android Support libraries

## Dimelo Android 1.1.4 (May 19th, 2016) ##
- Fix: button geometry with Android API 19
- FIx: layout size calculation with Android Support Library > 23.3.0

## Dimelo Android 1.1.3 (May 11th, 2016) ##
- Fix: compatibility with Android Support Library > 23.1

## Dimelo Android 1.1.2 (April 14th, 2016) ##
- Feature: It is now possible to customize text message and attachments background with different bubbles
- Feature: It is now possible to customize the color the send message arrow when disabled (no text & no attachment selected)
- Fix: Fixed crash which occured when the SDK was used without `com.google.android.geo.API_KEY`

## Dimelo Android 1.1.1 (January 13th, 2016) ##
- Fix: Fixed crash when calling setUserIdentifier or setJwt after first chat setup.

## Dimelo Android 1.1.0 (December 18th, 2015) ##
- Feature: Added support for image and location attachments.


## Dimelo Android 1.0.0 (July 7th, 2015) ##
- Feature: First official release supporting Dimelo Mobile protocol but limited to text
  interaction.
