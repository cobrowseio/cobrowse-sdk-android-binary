# Changelog

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

### [3.2.1](#) (2025-02-12)


### Bug Fixes

* keep a more consistent Modifier chain in Compose UI for redaction overlays ([#316](#)) ([347022f](#))

## [3.2.0](#) (2025-02-11)


### Features

* Android 16 Beta 1 support ([#285](#)) ([9701328](#))


### Bug Fixes

* fix incorrect bounds of redaction overlay on multi-line `EditText` ([#314](#)) ([613c741](#))

## [3.1.0](#) (2025-02-04)


### Features

* add `CobrowseIO.okHttpClient()` method to let the host app provide its own `OkHttpClient` instance ([#313](#)) ([2e7dc69](#))
* unify `Modifier.cobrowseSelector()` with `Modifier.cobrowseAutomatedSelector()` ([#306](#)) ([f5bf22a](#))


### Bug Fixes

* remote control back event not handled if "predictive back" feature is enabled ([#312](#)) ([a4f3a94](#))

### [3.0.3](#) (2025-01-29)

### [3.0.2](#) (2025-01-28)


### Bug Fixes

* compatibility issues with Kotlin 2.0 in the compiler plugin ([#308](#)) ([93571c1](#))

### [3.0.1](#) (2025-01-28)


### Features

* allow disabling injecting automated Compose UI redaction selectors if selector is already set in the code ([#304](#)) ([805f746](#))

## [3.0.0](#) (2025-01-27)


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

* allow verbose logging in the Gradle build plugin ([#300](#)) ([e98bd15](#))
* call delegate methods when no activity is running ([#297](#)) ([ffcbfb7](#))
* only allow strings as customData ([#287](#)) ([53610c5](#))
* Remove automatic intercom integration ([#288](#)) ([f216763](#))
* Remove bool versions of full device ([#290](#)) ([966dcb1](#))
* Remove default code and session UI ([#298](#)) ([9bd7148](#))
* remove deprecated Cobrowse APIs which required `Application` / `Activity` instances. ([#291](#)) ([b9eb9e6](#))
* Rename `redacted` Compose UI modifier to `cobrowseRedacted` ([#286](#)) ([8e67de2](#))
* Update minimum API version to 1.21.0 ([#289](#)) ([07cea76](#))


### Bug Fixes

* allow events with integer values ([#299](#)) ([d9c2cdb](#))
* redaction selectors for Compose UI not being injected into anonymous blocks ([#301](#)) ([fc7984a](#))

## [2.39.0](#) (2024-12-16)


### Features

* add support for `Modifier.testTag("")` in automated selectors for Compose UI ([#295](#)) ([5344b4f](#))

## [2.38.0](#) (2024-11-28)


### Features

* ensure that SDK callbacks are invoked on the main thread  ([#283](#)) ([b892ab4](#))
* target Android 14 (API 34) ([a249039](#))


### Bug Fixes

* rendering error with Compose `GraphicsLayer` API ([#284](#)) ([055cadf](#))

### [2.37.3](#) (2024-10-31)

### [2.37.2](#) (2024-10-30)


### Bug Fixes

* ComposeUI semantics naming ([#279](#)) ([711a229](#))

### [2.37.1](#) (2024-10-29)

## [2.37.0](#) (2024-10-29)


### Features

* introduce Kotlin compiler plugin and Gradle build plugin for compose UI redaction automation ([#272](#)) ([9756bf9](#))

### [2.36.1](#) (2024-10-11)


### Bug Fixes

* **remote_control:** Restore keypress capability ([#277](#)) ([a893b53](#))

## [2.36.0](#) (2024-10-04)


### Features

* add selector parsing in SDK ([#276](#)) ([5c90d87](#))

### [2.35.2](#) (2024-09-26)


### Bug Fixes

* catch invalid selectors ([2af549a](#))

### [2.35.1](#) (2024-09-14)


### Bug Fixes

* optimisation for dashboard selectors ([abce2de](#))

## [2.35.0](#) (2024-09-11)


### Features

* add Redaction index to improve selector performance ([#273](#)) ([933f297](#))
* single level dashboard selector support for Compose UI ([#275](#)) ([b92ff62](#))

### [2.34.3](#) (2024-08-27)

### [2.34.2](#) (2024-07-25)


### Bug Fixes

* fix WebView over-redaction with ComposeUI ([#271](#)) ([ed4dc44](#))
* the SDK now asks for the redacted views on scroll events ([#269](#)) ([488e926](#))

### [2.34.1](#) (2024-07-03)


### Bug Fixes

* auto-accept the media projection prompt on Google Pixel phones with Android 14 ([#262](#)) ([ad0040e](#))
* avoid rendering incomplete frames if a hardware bitmap is on the screen ([#267](#)) ([8aaac21](#))
* ensure we don't untrack webviews if they are still visible ([#265](#)) ([8704ae0](#))
* update the CBOR Java dependency to `4.5.4` to fix CVE-2024-23684 ([#268](#)) ([62df3a1](#))

## [2.34.0](#) (2024-06-05)


### Features

* Android 15 support; target Android 14 ([#243](#)) ([d866903](#))
* force webviews to LAYER_TYPE_NONE while in session ([#256](#)) ([7074f0c](#))


### Bug Fixes

* auto-accepting the media projection prompt on Samsung with Android 14 ([#253](#)) ([53a4e28](#))
* disable overscroll when in session to prevent leaking sensitive data on full device mode ([#259](#)) ([ccc81ce](#))
* don't use the broken H264 encoder on Raspberry ([#254](#)) ([b91157e](#))
* improve webview redaction with better handling of scroll state mismatches ([#258](#)) ([d14141d](#))
* reduce number of suppressed frames on global layouts ([804c32c](#))
* reduce redaction flicker caused by redacted webviews ([#249](#)) ([23e0528](#))
* stop frames being rescheduled early too frequently ([ee281b8](#))

### [2.33.1](#) (2024-04-22)


### Bug Fixes

* prefer `COLOR_FormatYUV420Flexible` color format when possible ([#240](#)) ([6dde2e9](#))

## [2.33.0](#) (2024-04-03)


### Features

* implement redaction for Jetpack Compose UI ([#232](#)) ([749745d](#))


### Bug Fixes

* crash when rendering a window with a hardware bitmap on it ([#238](#)) ([8db83d4](#))

### [2.32.2](#) (2024-02-20)


### Bug Fixes

* ensure webview is redacted while calculating webview redaction even if the webview itself is unredacted ([#237](#)) ([7cc04ea](#))

### [2.32.1](#) (2024-02-20)


### Bug Fixes

* issue when a session is changed from a push notification received in a background thread ([#234](#)) ([9a8ca86](#))

## [2.32.0](#) (2024-02-07)


### Features

* make `CobrowseService` removable ([#236](#)) ([269d3e4](#))

### [2.31.1](#) (2024-01-17)

## [2.31.0](#) (2024-01-17)


### Features

* let agents to type passwords into secure input fields in the full device mode ([#231](#)) ([0d23d8c](#))

### [2.30.4](#) (2024-01-02)


### Bug Fixes

* SDK not refreshing frames correctly when a camera preview is shown ([#229](#)) ([1f2c18e](#))

### [2.30.3](#) (2023-12-08)


### Bug Fixes

* error when redacting a scroll container which is not a `ViewGroup` ([#226](#)) ([9b1b0ca](#))

### [2.30.2](#) (2023-11-22)


### Bug Fixes

* WebView redaction not working in a ConstaintLayout container ([#225](#)) ([c511d1d](#))

### [2.30.1](#) (2023-11-06)


### Bug Fixes

* clear `currentSession()` if an error is returned ([#212](#)) ([037a254](#))
* declare `ACCESS_NETWORK_STATE` permission requirement ([#218](#)) ([1d22031](#))

## [2.30.0](#) (2023-10-02)


### Features

* allow capabilities to be set on a session object ([#213](#)) ([0929fec](#))

## [2.29.0](#) (2023-09-11)


### Features

* add new method `CobrowseIO#setDeviceToken()` which does not require an applicaiton instance ([#204](#)) ([aa4956c](#))
* SDK now targets Android 13 (API 33) ([#203](#)) ([aea9f40](#))


### Bug Fixes

* use sdk capabilities when not available from the server ([#211](#)) ([1b9eb3d](#))

### [2.28.2](#) (2023-08-07)


### Bug Fixes

* meet new requirements for foreground service on Android 14 ([#196](#)) ([1d9d7fe](#))
* use a different default session indicator in the multi-window mode ([#198](#)) ([eaad75e](#))

### [2.28.1](#) (2023-07-31)


### Bug Fixes

* explicitly set layout of View when redacting webview in react native ([#197](#)) ([2422bc0](#))

## [2.28.0](#) (2023-06-30)


### Features

* Android 14 (API 34) support ([#192](#)) ([0dbc7ee](#))
* Implement redaction within WebViews ([#187](#)) ([73c28da](#))

## [2.27.0](#) (2023-06-05)


### Features

* add new parameterless methods `CobrowseIO#start()` and `CobrowseIO#deviceId()` ([#189](#)) ([3728a09](#))

## [2.26.0](#) (2023-05-01)


### Bug Fixes

* finish `CobrowseAccessibilitySetup` activity after opening the system settings ([#185](#)) ([8fb5e30](#))

### [2.25.2](#) (2023-04-13)


### Bug Fixes

* Fix capabilities state in full-device mode ([#183](#)) ([ead57b5](#))

### [2.25.1](#) (2023-03-13)

## [2.25.0](#) (2023-03-12)


### Features

* Support unredaction as a first class SDK feature ([#178](#)) ([92f4dfa](#))

## [2.24.0](#) (2023-03-02)


### Features

* allow new sessions to preempt existing ones ([5a80566](#))
* Capabilities support ([#175](#)) ([551ba76](#))
* support non-FQDN socket URLs ([50698a2](#))


### Bug Fixes

* registration job ID misuse ([#173](#)) ([838e7ce](#))

### [2.23.5](#) (2022-12-20)


### Bug Fixes

* bug when SDK does not accept API URL with a trailing slash ([#162](#)) ([fe2f3fc](#))
* networking concurrency issue that may throw `NullPointerException` invoking `int java.util.Timer.purge()` on a null object reference ([#170](#)) ([1c4681b](#))

### [2.23.4](#) (2022-11-08)

### [2.23.3](#) (2022-11-08)

### [2.23.2](#) (2022-11-08)

### [2.23.1](#) (2022-11-08)

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
