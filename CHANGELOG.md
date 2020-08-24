# Changelog

## [2.5.0] - 2020-08-24
- Provides access to agent email when account settings allow
- Add support for requesting consent before using remote control tools

## [2.3.0] - 2020-06-23
- Make license() getter public
- Android X core 1.3.0
- Moved majority of docs to docs.cobrowse.io

## [2.0.0] - 2019-11-04
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

## [1.11.5] - 2019-08-09
- Prevent multiple requests for full screen access at once, plus a few minor bug fixes

## [1.11.4] - 2019-07-22
- Using a delegate without implementing RemoteControlDelegate should not prevent control

## [1.11.3] - 2019-07-15
- Fix error caused by background job startup ordering

## [1.11.1] - 2019-06-21
- Fix crash on API 19 devices

## [1.11.0] - 2019-06-21
- Optimisations to rendering process
