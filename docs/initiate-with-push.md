# Initiate with push (optional)

Please see full documentation at [https://cobrowse.io/docs](https://cobrowse.io/docs).

Try our **online demo** at the bottom of our homepage at <https://cobrowse.io/#tryit>.

## Implementation

These are the native-side requirements on Android to initiate sessions with push. More info at <https://cobrowse.io/docs#initiate-with-push>

You must first add Firebase Cloud Messaging (FCM) to your app. Please see FCM documentation at <https://firebase.google.com/docs/cloud-messaging/android/client>.

Next, whenever your device receives a registration token or push notification from FCM, pass that to the Cobrowse.io SDK, for example:

```java
package com.example;

import com.google.firebase.messaging.FirebaseMessagingService;
import com.google.firebase.messaging.RemoteMessage;

import io.cobrowse.CobrowseIO;

public class FirebaseMessaging extends FirebaseMessagingService {

    @Override
    public void onMessageReceived(RemoteMessage remoteMessage) {
        CobrowseIO.instance().onPushNotification(remoteMessage.getData());
    }

    @Override
    public void onNewToken(String token) {
        CobrowseIO.instance().setDeviceToken(getApplication(), token);
    }

}
```

## Questions?
Any questions at all? Please email us directly at [hello@cobrowse.io](mailto:hello@cobrowse.io).
