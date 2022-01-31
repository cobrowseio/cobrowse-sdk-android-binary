# Changelog

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

### [2.17.1](#) (2022-01-31)


### Bug Fixes

* add DPI-specific notification icons. ([280c61f](#))
* add missing 'android:exported' attribute to all SDK components. ([834764c](#))
* crash on Android 12 if a session is activated in background. ([04dfbef](#))
* get rid of redundant process lifecycle listener. ([a4c7ed3](#))
* specify the mutability flag in the notification PendingIntent. ([daf14b5](#))

## [2.17.0](#) (2022-01-28)


### Features

* add a reproduction of the issue with android.app.Dialog and 'singleInstance' activity. ([af714f9](#))
* rearrange the sample app UI. ([e8a5112](#))


### Bug Fixes

* Replace AsyncTask with java.util.concurrent classes ([cc71189](#))
* replace AsyncTask with java.util.concurrent classes. ([5abfefb](#))
* skip custom data updates that match the cached version ([2559433](#))

## [2.16.0](#) (2021-12-08)


**Special Consideration**

Due to recent Google Play Store policy changes regarding use of the Accessibility Service APIs there are extra changes required to continue using our support for full device remote control. Please follow the docs here to ensure your Accessibility Service will still function: https://docs.cobrowse.io/sdk-features/full-device-capabilities


### Bug Fixes

* don't activate 'android.permission.BIND_ACCESSIBILITY_SERVICE' by default. ([ae0f0f2](#))

### [2.15.1](#) (2021-12-08)


### Bug Fixes

* slow screen update on back navigation. ([ab42339](#))
* TextureView capture on Android 4.4. ([a8454f5](#))

## [2.15.0](#) (2021-11-29)


### Features

* activate COLOR_FormatYUV420PackedPlanar. ([d0596bc](#))
* implement COLOR_FormatYUV420Flexible support. ([b894f75](#))
* use accessibility API to handle all remote touches in full-device mode. ([c1c0beb](#))


### Bug Fixes

* disable COLOR_FormatYUV420SemiPlanar on Google Pixel 3a XL. ([511bcde](#))

### [2.14.1](#) (2021-11-15)


### Bug Fixes

* initialise custom data as soon as 6 digit code is created ([18b1f0a](#))

## [2.14.0](#) (2021-11-08)


### Features

* activate foreground notification on older Android platforms. ([13be810](#))
* add new Session-related unit tests. ([7aba57f](#))


### Bug Fixes

* initialization from a background thread. ([65c68c7](#))
* never stop CobrowseService before starting it again. ([01d993c](#))
* unit tests on Kitkat. ([eba17ea](#))

## [2.13.0](#) (2021-10-20)


### Features

* disable H.264 encoder on Android 4.4. ([ef8da80](#))
* implement handling remote 'Enter' key event. ([411878d](#))
* stop using 'WindowManagerGlobal' private API on Android 10+. ([8b15399](#))
* target Android 11. ([a019ea6](#))


### Bug Fixes

* avoid using Freescale hardware encoder on older platforms. ([2c1e121](#))
* don't destroy the MediaCodec instance when resetting the encoder. ([e2abcfa](#))
* IllegalStateException when accessing 'MediaCodec.getOutputFormat()' on Android 4.4. ([44c9827](#))
* remove deprecated devices from Firebase tests. ([75a54d2](#))
* remove warning for non-production APIs ([735365c](#))
* the mediaprojection prompt autoclick on Android 11. ([c167cdc](#))

### [2.12.3](#) (2021-09-24)


### Bug Fixes

* prevent black screen flashes on the agent side ([71768e5](#))
* stop automatically accepting all MediaProjection prompts if the current session is not full-device. ([5c7baa6](#))
* the first frame returned by FullDeviceFrameSource must be dirty. ([1358e16](#))

### [2.12.2](#) (2021-09-14)


### Bug Fixes

* full-device prompt auto-click on Android 5.1 ([f7712ab](#))

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
