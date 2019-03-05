# Redact sensitive data (optional)

Please see full documentation at [https://cobrowse.io/docs](https://cobrowse.io/docs).

Try our **online demo** at the bottom of our homepage at <https://cobrowse.io/#tryit>.

## Implementation

Redaction allows you to remove specific elements from the agents view. This allows you to keep private user data private. There are two ways to redact data in Cobrowse:

**1. Define the redacted views in your app source code (recommended)**

Implement the Redaction.Redacted interface on any Activity that contains sensitive views. This interface contains one method:

```java
List<View> redactedViews();

// From this method you should return a list of the views you want Cobrowse to redact, for example:
public List<View> redactedViews() {
    List<View> redacted = new ArrayList<>();
    redacted.add(findViewById(R.id.redact_me));
    return redacted;
}

```


If making changes to your Activity classes isn't an option, we also support a delegate style method to allow you to supply this information in one place. Find out more about this by emailing us at [hello@cobrowse.io](hello@cobrowse.io).


**2. Use the Cobrowse web dashboard to define redacted views**

You can also define redactions using a selector entered into the web dashboard. This can be useful if your app is already in production and you need to redact a field retrospectively, either due to a missed redaction entry in the app build or changing requirements. Visit the [dashboard settings](https://cobrowse.io/dashboard/settings/redaction) to enter redaction selectors.
