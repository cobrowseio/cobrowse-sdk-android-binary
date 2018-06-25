# Cobrowse.io - Android Native SDK

Cobrowse.io for Android supports API 19 (4.4 KitKat) and above. 

Cobrowse.io is 100% free and easy to try out in your own apps. Please see full documentation at [https://cobrowse.io/docs](https://cobrowse.io/docs).

Try our **online demo** at the bottom of our homepage at <https://cobrowse.io/#tryit>.

*Clients may access and integrate full source code for our SDKs directly upon request.*

## Installation

**In your app build.gradle**
```gradle
dependencies {
    // ... other dependencies ...
    implementation 'io.cobrowse:cobrowse-sdk-android:1.+'
}
```

To use Cobrowse.io in your project, please add the following lines to your Application subclass.

```java
package com.example;

import android.app.Application;
import io.cobrowse.core.CobrowseIO;

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

### Add your license key

Please register an account and generate your free License Key at <https://cobrowse.io/dashboard/settings>.

This will associate sessions from your mobile app with your Cobrowse.io account.


### Add device metadata 

To help you identify, search, and filter devices in your Cobrowse dashboard, it's helpful to specify any meaningful metadata. 

You may add any custom key/value pairs you'd like, and they will all be searchable and filterable in your online dashboard. We've added a few placeholders for convenience only - all fields are optional.

```java
package com.example;

import android.app.Application;
import io.cobrowse.core.CobrowseIO;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        CobrowseIO.instance().license("<your license key here>");

        Log.i("App", "Cobrowse device id: " + CobrowseIO.instance().deviceId(this));

        HashMap<String, Object> customData = new HashMap<>();
        customData.put("user_id", "<your_user_id>");
        customData.put("user_name", "<your_user_name>");
        customData.put("user_email", "<your_user_email>");
        customData.put("device_id", "<your_device_id>");
        customData.put("device_name", "<your_device_name>");
        CobrowseIO.instance().customData(customData);

        CobrowseIO.instance().start(this);
    }
}
```

## Try it out

Once you have your app running in the Android emulator or on a physical device, navigate to <https://cobrowse.io/dashboard> to see your device listed. You can click the "Connect" button to initiate a Cobrowse session!

## Optional features

[Initiate sessions with push](./docs/initiate-with-push.md)

[Use 6-digit codes](./docs/user-initiated-codes.md)

[Redact sensitive data](./docs/redact-sensitive-data.md)

## Questions?
Any questions at all? Please email us directly at [hello@cobrowse.io](mailto:hello@cobrowse.io).

## Requirements

* API version 19 or later
