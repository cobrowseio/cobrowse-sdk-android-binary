# Changelog

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

## [2.23.0](#) (2022-09-06)


### Features

* allow customization of full device request behavior. ([35a75ba](#))


### Bug Fixes

* redaction overlay not appearing on TextView/EditText which have both `android:gravity="end"` and `android:singleLine="true"` attributes set. ([fffaca3](#))
* remote redaction not applying to fragment dialogs. ([e207bd0](#))

## [2.22.0](#) (2022-08-29)


### Features

* SDK now targets Android 12 (API 31). ([d821ec7](#))


### Bug Fixes

* automatically accept the MediaProjection prompt on Android 12L in the accessibility service. ([529f838](#))
* don't use `COLOR_FormatYUV420SemiPlanar` on Android 12 and newer. ([c249a6d](#))
* H264 encoder on HTC 10 and Sharp SH-01L. ([6fae952](#))

### [2.21.6](#) (2022-05-31)


### Bug Fixes

* fix a case that could potentially cause duplicate full device prompts to be shown ([ecd0ff9](#))

### [2.21.5](#) (2022-05-25)


### Bug Fixes

* add support for redacting NestedScrollViews. ([de54c26](#))
* don't set profile and level on MSM8996 devices with Android 8. ([9f16851](#))
* remote drawing is not showing properly when device the refresh rate changes. ([a2f6452](#))

### [2.21.4](#) (2022-05-12)


### Bug Fixes

* add support for redacting horizontal scroll views ([4b7cbd8](#))

### [2.21.3](#) (2022-05-06)


### Bug Fixes

* redact all scroll content in ScrollViews ([cc66ce5](#))

### [2.21.2](#) (2022-05-06)


### Bug Fixes

* extend redaction overlays in scroll containers ([d2e7bec](#))

### [2.21.1](#) (2022-05-06)

## [2.21.0](#) (2022-05-06)


### Features

* set a device token to lock sessions to the device


### Bug Fixes

* fix H264 encoder on Google Pixel devices with Android 12.

### [2.20.1](#) (2022-04-26)


### Bug Fixes

* trigger a new full device permission prompt the first time it is used in each session

## [2.20.0](#) (2022-04-19)


### Features

* expose new full device APIs
* set full_device state as enum properties


### Bug Fixes

* use full device requested as default value for old servers

## [2.19.0](#) (2022-04-14)


### Features

* automatically accept the MediaProjection permission prompt only if the SDK is configured to do so.


### Bug Fixes

* add the customer Proguard/R8 rules.

### [2.18.2](#) (2022-02-16)


### Bug Fixes

* Fix untrusted touch events being blocked on Android 12

### [2.18.1](#) (2022-02-07)


### Bug Fixes

* only call loaded event after call completes

## [2.18.0](#) (2022-02-02)


### Features

* add delegate method that's called the first time a session is fetched from the server

### [2.17.2](#) (2022-01-31)


### Bug Fixes

* dynamically update full_device_control in device info on session object

### [2.17.1](#) (2022-01-31)


### Bug Fixes

* add DPI-specific notification icons.
* add missing 'android:exported' attribute to all SDK components.
* crash on Android 12 if a session is activated in background.
* get rid of redundant process lifecycle listener.
* specify the mutability flag in the notification PendingIntent.

## [2.17.0](#) (2022-01-28)


### Features

* rearrange the sample app UI.


### Bug Fixes

* Replace AsyncTask with java.util.concurrent classes
* skip custom data updates that match the cached version

## [2.16.0](#) (2021-12-08)


**Special Consideration**

Due to recent Google Play Store policy changes regarding use of the Accessibility Service APIs there are extra changes required to continue using our support for full device remote control. Please follow the docs here to ensure your Accessibility Service will still function: https://docs.cobrowse.io/sdk-features/full-device-capabilities


### Bug Fixes

* don't activate 'android.permission.BIND_ACCESSIBILITY_SERVICE' by default.

### [2.15.1](#) (2021-12-08)


### Bug Fixes

* slow screen update on back navigation.
* TextureView capture on Android 4.4.

## [2.15.0](#) (2021-11-29)


### Features

* activate COLOR_FormatYUV420PackedPlanar.
* implement COLOR_FormatYUV420Flexible support.
* use accessibility API to handle all remote touches in full-device mode.


### Bug Fixes

* disable COLOR_FormatYUV420SemiPlanar on Google Pixel 3a XL.

### [2.14.1](#) (2021-11-15)


### Bug Fixes

* initialise custom data as soon as 6 digit code is created.

## [2.14.0](#) (2021-11-08)


### Features

* activate foreground notification on older Android platforms.


### Bug Fixes

* run initialization from a background thread.
* never stop CobrowseService before starting it again.

## [2.13.0](#) (2021-10-20)


### Features

* disable H.264 encoder on Android 4.4.
* implement handling remote 'Enter' key event.
* stop using 'WindowManagerGlobal' private API on Android 10+.
* target Android 11.


### Bug Fixes

* avoid using Freescale hardware encoder on older platforms.
* don't destroy the MediaCodec instance when resetting the encoder.
* IllegalStateException when accessing 'MediaCodec.getOutputFormat()' on Android 4.4.
* remove warning for non-production APIs
* fix the mediaprojection prompt autoclick on Android 11. ([c167cdc](#))

### [2.12.3](#) (2021-09-24)


### Bug Fixes

* prevent black screen flashes on the agent side
* stop automatically accepting all MediaProjection prompts if the current session is not full-device.

### [2.12.2](#) (2021-09-14)


### Bug Fixes

* full-device prompt auto-click on Android 5.1

### [2.12.1](#) (2021-07-13)
- Added experimental support for Surface based views
- Improved touch handling for full device control

### [2.12.0] - 2021-06-09
- Expose full device setter

### [2.11.0] - 2021-05-21
- Allow overriding the default remote control consent prompt

### [2.10.0] - 2021-04-09
- Expose full device getter

### [2.5.0] - 2020-08-24
- Provides access to agent email when account settings allow
- Add support for requesting consent before using remote control tools

### [2.3.0] - 2020-06-23
- Make license() getter public
- Android X core 1.3.0
- Moved majority of docs to docs.cobrowse.io

### [2.0.0] - 2019-11-04
- BREAKING: Core classes are now under the io.cobrowse namespace rather than io.cobrowse.core
- BREAKING: Delegate interfaces have been renamed and moved under the io.cobrowse.CobrowseIO namespace:
            CobrowseIO.SessionRequestDelegate   (previously Session.RequestDelegate)
            CobrowseIO.SessionControlsDelegate  (previously Session.SessionControlsDelegate)
            CobrowseIO.RedactionDelegate        (previously Redaction.Delegate)
- BREAKING: A confirmation prompt is now shown to the user by default when a session is requested.
            You can disable or change this using the delegate methods above.
- BREAKING: A foreground service is started on newer versions on Android when a session is started.
            You can disable or change this using the delegate methods above.
- BREAKING: Removed remote control delegate methods while we develop an improved API

### [1.11.5] - 2019-08-09
- Prevent multiple requests for full screen access at once, plus a few minor bug fixes

### [1.11.4] - 2019-07-22
- Using a delegate without implementing RemoteControlDelegate should not prevent control

### [1.11.3] - 2019-07-15
- Fix error caused by background job startup ordering

### [1.11.1] - 2019-06-21
- Fix crash on API 19 devices

### [1.11.0] - 2019-06-21
- Optimisations to rendering process
