# Customizing the interface (optional)

Please see full documentation at [https://cobrowse.io/docs](https://cobrowse.io/docs).

Try our **online demo** at the bottom of our homepage at <https://cobrowse.io/#tryit>.

## Implementation

You can fully customize the interface for a Cobrowse session. The SDK provides hooks via `Session.SessionControlsDelegate` for you to render your own interface:

```java
package com.example;

import io.cobrowse.core.CobrowseIO;

public class MainApplication extends Application implements Session.SessionControlsDelegate {

    @Override
    public void onCreate() {
        super.onCreate();
        CobrowseIO.instance().setDelegate(this);

        // and the rest of cobrowse setup ...
    }

    @Override
    public View controlsForSession(final Activity activity, final Session session) {
        Button content = new Button(activity);
        content.setBackgroundColor(Color.RED);
        // also attach listeners etc...
        content.setText("END");
        content.setLayoutParams(new FrameLayout.LayoutParams(150, 100));
        content.setX(50);
        content.setY(50);
        return content;
    }

    //...

}
```

## Questions?
Any questions at all? Please email us directly at [hello@cobrowse.io](mailto:hello@cobrowse.io).
