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

## Questions?
Any questions at all? Please email us directly at [hello@cobrowse.io](mailto:hello@cobrowse.io).
