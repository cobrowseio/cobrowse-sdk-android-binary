# Changelog

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

## [3.19.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.19.0) (2026-10-09)


### Features

* capture secondary displays in the full-device mode using the accessibility service
* introduce `Application.rootViews()` extension function
* introduce `RedactionDelegate#redactedViews(Application)` and `UnredactionDelegate#unredactedViews(Application)`


### Bug Fixes

* agent video falling further behind the longer an Android session runs
* auto-accept the MediaProjection prompt in the accessibility service in multi-display environments on Android 16 QPR1+ and Android 17
* don't show "Choose app" option in the full-device prompt
* duplicate `android:name` attribute in the `lollipop` manifest
* edit password fields at the cursor and stop fast typing resetting them
* inject every remote tap in full-device mode, not only those after a pointer move
* never redact the SDK-owned views (agent annotations, default session indicator)
* pin `minCompileSdk` to 19 in the published AAR metadata
* remote keys not reaching Compose text fields in full-device mode

### [3.18.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.18.1) (2026-09-01)


### Bug Fixes

* misaligned WebView redactions when the WebView is inside a container with padding

## [3.18.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.18.0) (2026-08-27)


### Features

* introduce `View.cobrowseRedacted()` and `View.cobrowseUnredacted()` extension functions


### Bug Fixes

* correct displaced webview content in software capture caused by Android WebView bug
* pin Kotlin 2.0 in `cobrowse-sdk-android-gradle-plugin` and `cobrowse-sdk-android-kotlin-plugin`
* promote unredacted siblings in webview

### [3.17.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.17.3) (2026-08-21)


### Bug Fixes

* improve event monitor for webviews

### [3.17.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.17.2) (2026-08-21)


### Bug Fixes

* workaround a WebKit bug that can affect webview redaction overlays

### [3.17.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.17.1) (2026-08-17)


### Bug Fixes

* make the Compose SDK require Kotlin 2.0

## [3.17.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.17.0) (2026-08-11)


### Features

* device metrics
* indicate redacted nodes in the view hierarchy


### Bug Fixes

* frames can stop updating in full-device on some devices
* improve error messages about incorrect SDK setup

## [3.16.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.16.0) (2026-07-29)


### Features

* add support for Kotlin 2.1.0 - 2.4.0


### Bug Fixes

* error message in the Gradle plugin about SDK versions mismatch
* Prevent duplicate `handleRemoteControlRequest` & `handleFullDeviceRequest` delegate calls
* Rate limit 6-digit code creation
* respect bubble rounded corners in the default session indicator on Android 17

## [3.15.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.15.0) (2026-07-15)


### Features

* Add laser pointer ripples


### Bug Fixes

* ensure that the calculated latency is returned when a message tracking is concluded

### [3.14.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.14.3) (2026-07-01)


### Bug Fixes

* auto-accept the full-device system prompt on Motorola devices with Android 15

### [3.14.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.14.2) (2026-06-17)


### Bug Fixes

* never serialize a null `attributes` map on the view hierarchy channel

### [3.14.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.14.1) (2026-06-10)


### Bug Fixes

* selectors failing to match against `id`

## [3.14.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.14.0) (2026-05-30)


### Features

* default to scaling method 1 (`DURING_RENDER`)
* downscale `SurfaceView` in rendering

### [3.13.4](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.13.4) (2026-04-16)

### [3.13.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.13.3) (2026-03-31)


### Bug Fixes

* improve TextureView rendering
* move write to buffer
* reduce allocations in selector matching logic
* respect `APPEARANCE_TRANSPARENT_CAPTION_BAR_BACKGROUND` in the default session indicator

### [3.13.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.13.2) (2026-01-29)


### Bug Fixes

* resolution not updating when the device rotates in full-device mode on Android 14 (API 34) and above

### [3.13.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.13.1) (2026-01-20)


### Bug Fixes

* abstract frame loop scheduling
* **experimental:** introduce additional scale value

## [3.13.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.13.0) (2026-01-15)


### Features

* Introduce `WebViewRedactionFactoryDelegate`


### Bug Fixes

* print a warning log message if Coil image loading library uses hardware bitmaps

### [3.12.4](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.12.4) (2025-11-25)


### Bug Fixes

* make sure an explicitly unredacted view is never redacted
* reduce per-frame allocations when encoding frames

### [3.12.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.12.3) (2025-11-20)


### Bug Fixes

* prevent concurrent encoding of bitmap during redering

### [3.12.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.12.2) (2025-11-19)


### Bug Fixes

* Add performance logging for main frame loop components

### [3.12.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.12.1) (2025-11-14)


### Bug Fixes

* downscale frames on a background thread
* encoders no longer encode frames unessasarily
* lower the Kotlin dependency to `1.6.21` in the main SDK
* reduce the number of view traversal operation if no redaction selector is set

## [3.12.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.12.0) (2025-10-31)


### Features

* handle shadow roots in webview redaction
* Improve rendering performance

## [3.11.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.11.0) (2025-10-24)


### Features

* expose session timestamps

## [3.10.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.10.0) (2025-10-22)


### Features

* collect extra attributes from Android view
* expose `ended_reason` on Session
* target Android 15 (API 35)
* update OkHttp dependency to `4.12.0`

com.squareup.okhttp3:okhttp dependency has been upgraded from 3.12.13 to 4.12.0 due to security concerns, in particular CVE-2021-0341, CVE-2023-0833, CVE-2023-3635.

OkHttp 3.12.13 was the latest version that supports Android 4.4. In order to continue to use Cobrowse SDK on Android 4.4 consider force-downgrading OkHttp dependency in your own app:
```
dependencies {
    implementation("com.squareup.okhttp3:okhttp:3.12.13")
}


configurations.all {
    resolutionStrategy {
        force("com.squareup.okhttp3:okhttp:3.12.13")
    }
}
```

### Bug Fixes

* full_device should switch to On when the user has accepted the system prompt, not immediately
* remote control with `android.widget.PopupWindow`

### [3.9.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.9.1) (2025-08-06)

## [3.9.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.9.0) (2025-08-06)


### Features

* add playground support for Android views
* Compose UI redaction API is now stable


### Bug Fixes

* don't treat missing ID or content description as `"null"` string literal
* Support new versions of RN webview

### [3.8.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.8.2) (2025-06-16)


### Bug Fixes

* add support for extension functions﻿ in the Kotlin compiler plugin

### [3.8.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.8.1) (2025-06-05)


### Bug Fixes

* add support for elvis `?:` and safe call `?.` operators in the Kotlin compiler plugin

## [3.8.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.8.0) (2025-05-29)


### Features

* add `selectorSources` configuration option to disable replication of certain selector parts
* session quality monitoring


### Bug Fixes

* improve extracting properties for `cobrowseSelector` modifier

## [3.7.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.7.0) (2025-05-23)


### Features

* webview domain redaction config from sdk


### Bug Fixes

* extract `testTag` value if it's inside `remember` function

## [3.6.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.6.0) (2025-04-08)


### Features

* webview redaction rules

### [3.5.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.5.1) (2025-04-04)


### Bug Fixes

* avoid injecting redundant `cobrowseSelector()` modifiers
* extract `testTag` modifier value if it's behind `Modifier.then`

## [3.5.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.5.0) (2025-04-01)


### Features

* add playground support for Compose UI
* add support for different tool colors and disappearing ink drawings
* support unredaction for Jetpack Compose UI


### Bug Fixes

* make `defaultAttributes` an ordinary map type
* throw an exception when trying to set an invalid redaction selector
* treat ID in selectors as `id` property of `attributes`

### [3.4.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.4.1) (2025-03-11)

## [3.4.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.4.0) (2025-03-05)


### Features

* allow additional Compose redaction selector attributes be set in Gradle configuration


### Bug Fixes

* reduce overhead of Compose redaction modifiers

## [3.3.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.3.0) (2025-02-27)


### Features

* add support for multi-level redaction selectors in Compose UI
* add support to arrows and rectangles drawings
* use Kotlin 2.0

### [3.2.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.2.1) (2025-02-12)


### Bug Fixes

* keep a more consistent Modifier chain in Compose UI for redaction overlays

## [3.2.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.2.0) (2025-02-11)


### Features

* Android 16 Beta 1 support


### Bug Fixes

* fix incorrect bounds of redaction overlay on multi-line `EditText`

## [3.1.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.1.0) (2025-02-04)


### Features

* add `CobrowseIO.okHttpClient()` method to let the host app provide its own `OkHttpClient` instance
* unify `Modifier.cobrowseSelector()` with `Modifier.cobrowseAutomatedSelector()`


### Bug Fixes

* remote control back event not handled if "predictive back" feature is enabled

### [3.0.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.0.3) (2025-01-29)

### [3.0.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.0.2) (2025-01-28)


### Bug Fixes

* compatibility issues with Kotlin 2.0 in the compiler plugin

### [3.0.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.0.1) (2025-01-28)


### Features

* allow disabling injecting automated Compose UI redaction selectors if selector is already set in the code

## [3.0.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v3.0.0) (2025-01-27)


### ⚠ BREAKING CHANGES

* Compose UI support: the `redacted()` modifier for Compose UI was renamed to `cobrowseRedacted()` to prevent naming clashes with other libraries
* Remove default code and session UI (#298)
* SDK now invokes delegate methods, including session consent delegate, even when there no activity running. These delegates are: `SessionRequestDelegate`, `RemoteControlRequestDelegate`, `FullDeviceRequestDelegate`. This allows handling some requests while the app is backgrounded.
* the SDK now tracks application and activity objects from your app automatically. You don't have to pass them manually.
* `customData` is now restricted to string values only

**Before**
```java
CobrowseIO.instance().customData(new HashMap<String, Object>() {{
    put(CobrowseIO.USER_EMAIL_KEY, "android@example.com");
    put(CobrowseIO.DEVICE_NAME_KEY, "Android Demo");
    put("your-own-key2", 42);
}});
```

**After**
```java
CobrowseIO.instance().customData(Map.of(
        CobrowseIO.USER_EMAIL_KEY, "android@example.com",
        CobrowseIO.DEVICE_NAME_KEY, "Android Demo",
        "your-own-key2", "42"
));
```
* Removes the boolean versions of the fullDevice setter / getters. You should now use the more descriptive enum versions instead.
* Updated the minimum support Cobrowse API version to 1.21.0
* The built-in intercom integration support has been removed. To continue to support cobrowse Intercom integrations in your apps please set an Intercom user property called `CobrowseID` to the `CobrowseIO.instance().deviceId()` value, like so:

```java
Intercom.client().updateUser(
        new UserAttributes.Builder()
                .withCustomAttributes(Map.of("CobrowseID", CobrowseIO.instance().deviceId()))
                .build());
```

### Features

* allow verbose logging in the Gradle build plugin
* call delegate methods when no activity is running
* only allow strings as customData
* Remove automatic intercom integration
* Remove bool versions of full device
* Remove default code and session UI
* remove deprecated Cobrowse APIs which required `Application` / `Activity` instances.
* Rename `redacted` Compose UI modifier to `cobrowseRedacted`
* Update minimum API version to 1.21.0


### Bug Fixes

* allow events with integer values
* redaction selectors for Compose UI not being injected into anonymous blocks

## [2.39.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.39.0) (2024-12-16)


### Features

* add support for `Modifier.testTag("")` in automated selectors for Compose UI

## [2.38.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.38.0) (2024-11-28)


### Features

* ensure that SDK callbacks are invoked on the main thread 
* target Android 14 (API 34)


### Bug Fixes

* rendering error with Compose `GraphicsLayer` API

### [2.37.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.37.3) (2024-10-31)

### [2.37.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.37.2) (2024-10-30)


### Bug Fixes

* ComposeUI semantics naming

### [2.37.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.37.1) (2024-10-29)

## [2.37.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.37.0) (2024-10-29)


### Features

* introduce Kotlin compiler plugin and Gradle build plugin for compose UI redaction automation

### [2.36.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.36.1) (2024-10-11)


### Bug Fixes

* **remote_control:** Restore keypress capability

## [2.36.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.36.0) (2024-10-04)


### Features

* add selector parsing in SDK

### [2.35.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.35.2) (2024-09-26)


### Bug Fixes

* catch invalid selectors

### [2.35.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.35.1) (2024-09-14)


### Bug Fixes

* optimisation for dashboard selectors

## [2.35.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.35.0) (2024-09-11)


### Features

* add Redaction index to improve selector performance
* single level dashboard selector support for Compose UI

### [2.34.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.34.3) (2024-08-27)

### [2.34.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.34.2) (2024-07-25)


### Bug Fixes

* fix WebView over-redaction with ComposeUI
* the SDK now asks for the redacted views on scroll events

### [2.34.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.34.1) (2024-07-03)


### Bug Fixes

* auto-accept the media projection prompt on Google Pixel phones with Android 14
* avoid rendering incomplete frames if a hardware bitmap is on the screen
* ensure we don't untrack webviews if they are still visible
* update the CBOR Java dependency to `4.5.4` to fix CVE-2024-23684

## [2.34.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.34.0) (2024-06-05)


### Features

* Android 15 support; target Android 14
* force webviews to LAYER_TYPE_NONE while in session


### Bug Fixes

* auto-accepting the media projection prompt on Samsung with Android 14
* disable overscroll when in session to prevent leaking sensitive data on full device mode
* don't use the broken H264 encoder on Raspberry
* improve webview redaction with better handling of scroll state mismatches
* reduce number of suppressed frames on global layouts
* reduce redaction flicker caused by redacted webviews
* stop frames being rescheduled early too frequently

### [2.33.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.33.1) (2024-04-22)


### Bug Fixes

* prefer `COLOR_FormatYUV420Flexible` color format when possible

## [2.33.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.33.0) (2024-04-03)


### Features

* implement redaction for Jetpack Compose UI


### Bug Fixes

* crash when rendering a window with a hardware bitmap on it

### [2.32.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.32.2) (2024-02-20)


### Bug Fixes

* ensure webview is redacted while calculating webview redaction even if the webview itself is unredacted

### [2.32.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.32.1) (2024-02-20)


### Bug Fixes

* issue when a session is changed from a push notification received in a background thread

## [2.32.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.32.0) (2024-02-07)


### Features

* make `CobrowseService` removable

### [2.31.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.31.1) (2024-01-17)

## [2.31.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.31.0) (2024-01-17)


### Features

* let agents to type passwords into secure input fields in the full device mode

### [2.30.4](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.30.4) (2024-01-02)


### Bug Fixes

* SDK not refreshing frames correctly when a camera preview is shown

### [2.30.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.30.3) (2023-12-08)


### Bug Fixes

* error when redacting a scroll container which is not a `ViewGroup`

### [2.30.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.30.2) (2023-11-22)


### Bug Fixes

* WebView redaction not working in a ConstaintLayout container

### [2.30.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.30.1) (2023-11-06)


### Bug Fixes

* clear `currentSession()` if an error is returned
* declare `ACCESS_NETWORK_STATE` permission requirement

## [2.30.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.30.0) (2023-10-02)


### Features

* allow capabilities to be set on a session object

## [2.29.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.29.0) (2023-09-11)


### Features

* add new method `CobrowseIO#setDeviceToken()` which does not require an applicaiton instance
* SDK now targets Android 13 (API 33)


### Bug Fixes

* use sdk capabilities when not available from the server

### [2.28.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.28.2) (2023-08-07)


### Bug Fixes

* meet new requirements for foreground service on Android 14
* use a different default session indicator in the multi-window mode

### [2.28.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.28.1) (2023-07-31)


### Bug Fixes

* explicitly set layout of View when redacting webview in react native

## [2.28.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.28.0) (2023-06-30)


### Features

* Android 14 (API 34) support
* Implement redaction within WebViews

## [2.27.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.27.0) (2023-06-05)


### Features

* add new parameterless methods `CobrowseIO#start()` and `CobrowseIO#deviceId()`

## [2.26.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.26.0) (2023-05-01)


### Bug Fixes

* finish `CobrowseAccessibilitySetup` activity after opening the system settings

### [2.25.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.25.2) (2023-04-13)


### Bug Fixes

* Fix capabilities state in full-device mode

### [2.25.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.25.1) (2023-03-13)

## [2.25.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.25.0) (2023-03-12)


### Features

* Support unredaction as a first class SDK feature

## [2.24.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.24.0) (2023-03-02)


### Features

* allow new sessions to preempt existing ones
* Capabilities support
* support non-FQDN socket URLs


### Bug Fixes

* registration job ID misuse

### [2.23.5](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.23.5) (2022-12-20)


### Bug Fixes

* bug when SDK does not accept API URL with a trailing slash
* networking concurrency issue that may throw `NullPointerException` invoking `int java.util.Timer.purge()` on a null object reference

### [2.23.4](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.23.4) (2022-11-08)

### [2.23.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.23.3) (2022-11-08)

### [2.23.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.23.2) (2022-11-08)

### [2.23.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.23.1) (2022-11-08)

## [2.23.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.23.0) (2022-09-06)


### Features

* allow customization of full device request behavior.


### Bug Fixes

* redaction overlay not appearing on TextView/EditText which have both `android:gravity="end"` and `android:singleLine="true"` attributes set.
* remote redaction not applying to fragment dialogs.

## [2.22.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.22.0) (2022-08-29)


### Features

* SDK now targets Android 12 (API 31).


### Bug Fixes

* automatically accept the MediaProjection prompt on Android 12L in the accessibility service.
* don't use `COLOR_FormatYUV420SemiPlanar` on Android 12 and newer.
* H264 encoder on HTC 10 and Sharp SH-01L.

### [2.21.6](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.21.6) (2022-05-31)


### Bug Fixes

* fix a case that could potentially cause duplicate full device prompts to be shown

### [2.21.5](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.21.5) (2022-05-25)


### Bug Fixes

* add support for redacting NestedScrollViews.
* don't set profile and level on MSM8996 devices with Android 8.
* remote drawing is not showing properly when device the refresh rate changes.

### [2.21.4](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.21.4) (2022-05-12)


### Bug Fixes

* add support for redacting horizontal scroll views

### [2.21.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.21.3) (2022-05-06)


### Bug Fixes

* redact all scroll content in ScrollViews

### [2.21.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.21.2) (2022-05-06)


### Bug Fixes

* extend redaction overlays in scroll containers

### [2.21.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.21.1) (2022-05-06)

## [2.21.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.21.0) (2022-05-06)


### Features

* set a device token to lock sessions to the device


### Bug Fixes

* fix H264 encoder on Google Pixel devices with Android 12.

### [2.20.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.20.1) (2022-04-26)


### Bug Fixes

* trigger a new full device permission prompt the first time it is used in each session

## [2.20.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.20.0) (2022-04-19)


### Features

* expose new full device APIs
* set full_device state as enum properties


### Bug Fixes

* use full device requested as default value for old servers

## [2.19.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.19.0) (2022-04-14)


### Features

* automatically accept the MediaProjection permission prompt only if the SDK is configured to do so.


### Bug Fixes

* add the customer Proguard/R8 rules.

### [2.18.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.18.2) (2022-02-16)


### Bug Fixes

* Fix untrusted touch events being blocked on Android 12

### [2.18.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.18.1) (2022-02-07)


### Bug Fixes

* only call loaded event after call completes

## [2.18.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.18.0) (2022-02-02)


### Features

* add delegate method that's called the first time a session is fetched from the server

### [2.17.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.17.2) (2022-01-31)


### Bug Fixes

* dynamically update full_device_control in device info on session object

### [2.17.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.17.1) (2022-01-31)


### Bug Fixes

* add DPI-specific notification icons.
* add missing 'android:exported' attribute to all SDK components.
* crash on Android 12 if a session is activated in background.
* get rid of redundant process lifecycle listener.
* specify the mutability flag in the notification PendingIntent.

## [2.17.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.17.0) (2022-01-28)


### Features

* rearrange the sample app UI.


### Bug Fixes

* Replace AsyncTask with java.util.concurrent classes
* skip custom data updates that match the cached version

## [2.16.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.16.0) (2021-12-08)


**Special Consideration**

Due to recent Google Play Store policy changes regarding use of the Accessibility Service APIs there are extra changes required to continue using our support for full device remote control. Please follow the docs here to ensure your Accessibility Service will still function: https://docs.cobrowse.io/sdk-features/full-device-capabilities


### Bug Fixes

* don't activate 'android.permission.BIND_ACCESSIBILITY_SERVICE' by default.

### [2.15.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.15.1) (2021-12-08)


### Bug Fixes

* slow screen update on back navigation.
* TextureView capture on Android 4.4.

## [2.15.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.15.0) (2021-11-29)


### Features

* activate COLOR_FormatYUV420PackedPlanar.
* implement COLOR_FormatYUV420Flexible support.
* use accessibility API to handle all remote touches in full-device mode.


### Bug Fixes

* disable COLOR_FormatYUV420SemiPlanar on Google Pixel 3a XL.

### [2.14.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.14.1) (2021-11-15)


### Bug Fixes

* initialise custom data as soon as 6 digit code is created.

## [2.14.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.14.0) (2021-11-08)


### Features

* activate foreground notification on older Android platforms.


### Bug Fixes

* run initialization from a background thread.
* never stop CobrowseService before starting it again.

## [2.13.0](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.13.0) (2021-10-20)


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
* fix the mediaprojection prompt autoclick on Android 11.

### [2.12.3](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.12.3) (2021-09-24)


### Bug Fixes

* prevent black screen flashes on the agent side
* stop automatically accepting all MediaProjection prompts if the current session is not full-device.

### [2.12.2](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.12.2) (2021-09-14)


### Bug Fixes

* full-device prompt auto-click on Android 5.1

### [2.12.1](https://github.com/cobrowseio/cobrowse-sdk-android-binary/releases/tag/v2.12.1) (2021-07-13)
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
