# Cobrowse.io SDK for Android

Cobrowse.io for Android supports API 19 (4.4 KitKat) and above. Learn more at [https://cobrowse.io](https://cobrowse.io).

Clients may access and integrate full source code for our SDKs directly upon request. 

## Try it out

Please try our **online demo** at the bottom of our homepage at <https://cobrowse.io/#tryit>.

Cobrowse.io is 100% free and easy to try out in your apps. Please follow the installation instructions below, then head to <https://cobrowse.io/trial> to access the trial dashboard.

These instructions will install a binary distribution of the Cobrowse.io SDK. Clients may also access and integrate full source code for our SDKs directly by emailing us [hello@cobrowse.io](mailto:hello@cobrowse.io).

## Installation

Cobrowse.io uses a maven distribution. Please add the following lines to your gradle files.

**In your project build.gradle**
Esnure that JCenter is added to your list of repositories:
```gradle
repositories {
    jcenter()
}
```

**In your app build.gradle**
```gradle
dependencies {
    // ... other dependencies ...
    implementation 'io.cobrowse:cobrowse-sdk-android:1.+'
}
```

## Configuration

By default, your app will use our trial license key and trial dashboard at <https://cobrowse.io/trial>.

This will work fine for user-initiated sessions (see below), but agent-initiated sessions (see below) will require you to first register a free account and generate a unique license key. This will associate sessions from your mobile app with your Cobrowse.io account.

### Basic setup

To use Cobrowse.io in your project, please add the following lines to your Application subclass.

```java
package com.example;

import android.app.Application;
import io.cobrowse.core.CobrowseIO;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        CobrowseIO.instance().license("trial");
        CobrowseIO.instance().start(this);
    }
}
```

### Add your license key
Once you've signed up for a free account at <https://cobrowse.io/register>, you'll be able to find your license key at <https://cobrowse.io/dashboard/settings>. Add this to your Application subclass:
```java
CobrowseIO.instance().license("<your license key here>");
```
**Important:** Make sure you do this in your custom Application subclass `onCreate()` to ensure devices register in your dashboard right away.

## Agent-initiated Sessions

Without any additional UI or logic in your app, authenticated support agents are able to initiate sessions remotely via our online dashboard. To do this in an efficient way, we send an invisible push notification to the target device with a custom payload.

To setup agent-initiated sessions:

1. Set up Firebase Cloud Messaging for your app. See the latest Firebase documentation for instructions at <https://firebase.google.com/docs/cloud-messaging/>.
2. Enter your FCM Server Key from the FCM admin settings into your Cobrowse.io account at https://cobrowse.io/dashboard/settings.
3. Whenever your device receives a registration token from FCM, pass that to the Cobrowse.io SDK, for example:

```java
package com.example;

import com.google.firebase.iid.FirebaseInstanceId;
import com.google.firebase.iid.FirebaseInstanceIdService;

import io.cobrowse.core.CobrowseIO;

public class FirebaseIdService  extends FirebaseInstanceIdService {

    @Override
    public void onTokenRefresh() {
        String refreshedToken = FirebaseInstanceId.getInstance().getToken();
        CobrowseIO.instance().setDeviceToken(getApplication(), refreshedToken);
    }
}
```
4. Similarly, whenever you receive a push notification, forward that on to the Cobrowse.io SDK:

```java
package com.example;

import com.google.firebase.messaging.FirebaseMessagingService;
import com.google.firebase.messaging.RemoteMessage;

import io.cobrowse.core.CobrowseIO;

public class FirebaseMessaging extends FirebaseMessagingService {

    @Override
    public void onMessageReceived(RemoteMessage remoteMessage) {
        CobrowseIO.instance().onPushNotification(remoteMessage.getData());
    }
}
```
** Free License Key is required to see active devices listed in your account's online dashboard. Sign up at <https://cobrowse.io/register> and see Configuration above.


## User-initiated Sessions

You may also expose small UI in your app for users to generate a 6-digit code that they pass to an agent over the phone or chat to initiate a session. 

We have provided some default UI to make things easier to get started:

```java
import io.cobrowse.ui.CobrowseActivity;

public class YourActivity extends Activity {

    // the rest of your Activity

    public void startCobrowse(View view) {
        Intent intent = new Intent(this, CobrowseActivity.class);
        startActivity(intent);
    }
}
```

Make sure you've hooked up a trigger for the `startCobrowse` method that we've just added. By default your apps will register with a trial license, so you can access the them from <https://cobrowse.io/trial>. Enter the 6 digit code that will be generated by your app when you trigger the action!

## Questions?
We want to hear from you! Please email us directly at [hello@cobrowse.io](mailto:hello@cobrowse.io).

## Requirements

* API version 19 or later
