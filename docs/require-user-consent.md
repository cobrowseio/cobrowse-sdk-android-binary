# Requiring user consent (optional)

Please see full documentation at [https://cobrowse.io/docs](https://cobrowse.io/docs).

Try our **online demo** at the bottom of our homepage at <https://cobrowse.io/#tryit>.

## Implementation

You may want to ask the user for permission to view their screen before starting a session. You can use the following SDK hook to handle a remote session request.

```java

public class MainApplication extends Application implements CobrowseIO.SessionRequestDelegate {

    @Override
    public void onCreate() {
        super.onCreate();
        CobrowseIO.instance().setDelegate(this);

        // and the rest of cobrowse setup ...
    }

    @Override
    public void handleSessionRequest(Session session) {
        // Do something here, e.g. showing a permission request dialog
        // Make sure to call activate(<callback>) on the session object if
        // you want to start the session.
        // Provide a callback if you wish to handle errors during session
        // initiation.
        session.activate(null);
    }

    // ...
}

```

## Questions?
Any questions at all? Please email us directly at [hello@cobrowse.io](mailto:hello@cobrowse.io).
