# Cobrowse.io - Android Native SDK

Cobrowse.io is 100% free and easy to try out in your own apps. Please see full documentation at [https://docs.cobrowse.io](https://docs.cobrowse.io).

Try our **online demo** at the bottom of our homepage at <https://cobrowse.io/#tryit>.

## Installation

**In your app build.gradle**
```gradle
dependencies {
    // ... other dependencies ...
    implementation 'io.cobrowse:cobrowse-sdk-android:2.+'
}
```

To use Cobrowse.io in your project, please add the following lines to your Application subclass.

```java
package com.example;

import android.app.Application;
import io.cobrowse.CobrowseIO;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        CobrowseIO.instance().license("<your license key here>");
        CobrowseIO.instance().start(this);
    }
}
```

**Important:** Make sure you do this in your custom Application subclass `onCreate()` to ensure devices register in your dashboard right away.

You may also start CobrowseIO in your MainActivity or other Activity if necessary. In that case, the SDK will continue to function even as new Activities are being created and destroyed.

### Add your license key

Please register an account and generate your free License Key at <https://cobrowse.io/dashboard/settings>.

This will associate sessions from your mobile app with your Cobrowse.io account.

## Try it out

Once you have your app running in the Android emulator or on a physical device, navigate to <https://cobrowse.io/dashboard> to see your device listed. You can click the "Connect" button to initiate a Cobrowse session!

## Optional features

[Identify your devices](https://docs.cobrowse.io/sdk-features/identify-your-devices)

[Use 6-digit codes](https://docs.cobrowse.io/sdk-features/6-digit-codes)

[Redact sensitive data](https://docs.cobrowse.io/sdk-features/redact-sensitive-data)

[Customize the interface](https://docs.cobrowse.io/sdk-features/customize-the-interface)

[Initiate sessions with push](https://docs.cobrowse.io/sdk-features/initiate-sessions-with-push)

[Full device capabilities](https://docs.cobrowse.io/sdk-features/full-device-capabilities)

[Advanced features](https://docs.cobrowse.io/sdk-features/advanced-features)

## Questions?
Any questions at all? Please email us directly at [hello@cobrowse.io](mailto:hello@cobrowse.io).

## Requirements

* API version 19 (4.4 KitKat) or later
