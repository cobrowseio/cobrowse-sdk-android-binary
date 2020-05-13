# Customizing the interface (optional)

Please see full documentation at [https://cobrowse.io/docs](https://cobrowse.io/docs).

Try our **online demo** at the bottom of our homepage at <https://cobrowse.io/#tryit>.

## Implementation

You can fully customize the interface for a Cobrowse session. The SDK provides hooks via `CobrowseIO.SessionControlsDelegate` for you to render your own interface:

```java
package com.example;

import io.cobrowse.CobrowseIO;

public class MainApplication extends Application implements CobrowseIO.SessionControlsDelegate {

    @Override
    public void onCreate() {
        super.onCreate();
        CobrowseIO.instance().setDelegate(this);

        // and the rest of cobrowse setup ...
    }

    @Override
    public void showSessionControls(final Activity activity, final Session session) {
        // optionally show your own controls here
    }

    @Override
    public void hideSessionControls(final Activity activity, final Session session) {
        // hide controls created by the method above here
    }

    //...

}
```

## Customizing the 6 Digit Code screen

You can build your own UI to completely replace the default UI we provide for generating 6 digit codes. You can generate a code for your UI by using the `createSession` API:

```java
CobrowseIO.instance().createSession(new Callback<Error, Session>() {
    @Override
    public void call(@Nullable Error err, @Nullable Session session) {
        if (err != null) Log.e("CobrowseIO", "Error creating session " + err.getMessage());
        else if (session != null) Log.i("CobrowseIO", "Created session code " + session.code());
    }
});
```

**Note:** the codes expire shortly after creation (codes last less than 10 minutes), so wait until your user is ready to share the code with an agent before generating it:

You can monitor changes in the state of the session you create using the Cobrowse delegate methods:

```java
void sessionDidUpdate(final @NonNull Session session);
void sessionDidEnd(final @NonNull Session session);
```

You can get information about the state of the session using the following methods, which may adjust the UI you are showing:

```java
session.isPending() // session has been created but is waiting for agent or user
session.isAuthorizing() // waiting for the user to confirm the session
session.isActive() // session running, frames are streaming to the agent
session.isEnded() // session is over and can no longer be used or edited
```

## Questions?
Any questions at all? Please email us directly at [hello@cobrowse.io](mailto:hello@cobrowse.io).
