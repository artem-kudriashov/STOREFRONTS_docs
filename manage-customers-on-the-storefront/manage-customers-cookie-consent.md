# Manage customer's cookie consent

Storefront JS API allows you to set cookie consent on behalf of the user or react to its changes depending on the value.

Find a list of available methods below.

### Get user's cookie consent

The `Ecwid.getTrackingConsent();` receives the customer's answer to the cookie consent banner. Use it to define what cookies your application can collect.

{% hint style="warning" %}
If the cookie consent value is overridden by the JS method or config, `Ecwid.getTrackingConsent()` returns the new value added by JS method/config.
{% endhint %}

Code example:

```javascript
Ecwid.getTrackingConsent();

// {  userResponse: "ACCEPTED", askConsent: true }
```

Fields available in the returned object:

<table><thead><tr><th width="171">Field</th><th width="115">Type</th><th>Description</th></tr></thead><tbody><tr><td>userResponse</td><td>string</td><td><p></p><p>Customer's cookie consent. Available values:</p><ul><li><code>"UNDEFINED"</code>: Customer hasn't given their consent yet.</li><li><code>"ACCEPTED"</code>: Collect all types of cookies.</li><li><code>"DECLINED"</code>: Collect only essential cookies.</li><li><code>"ANALYTICS_ONLY"</code>: Collect essential and analytics cookies only.</li><li><code>"PERSONALIZATION_ONLY"</code>: Collect essential and personalization cookies.</li></ul></td></tr><tr><td>askConsent</td><td>boolean</td><td><code>true</code> if store requests customer consent, <code>false</code> otherwise.</td></tr></tbody></table>

### Set user's cookie consent

There are two ways of setting cookie consent value on behalf of the user: through the JS function and the HTML code. We recommend using only one of these methods on your website. If both are used, the _HTML config gets higher priority_.

The JavaScript method is useful when you add Ecwid to a website that asks for users' cookie consent before Ecwid. With it, you can dynamically set cookie consent for the Ecwid store, when users set it on your website.

The HTML config allows you to disable the cookie consent banner and set one value on behalf of users. For example, you can use it to only allow analytics cookies for all users.

#### Set cookie consent with JavaScript

Before using this JavaScript method, make sure to [enable JS API](ref:get-started-with-storefront-js-api#enable-js-api-on-the-storefront) in your script file.

The `Ecwid.setTrackingConsent();` method accepts an argument matching one of the following values:

* `"UNDEFINED"`: Customer hasn't given their consent yet.
* `"ACCEPTED"`: Collect all types of cookies.
* `"DECLINED"`: Collect only essential cookies.
* `"ANALYTICS_ONLY"`: Collect essential and analytics cookies only.
* `"PERSONALIZATION_ONLY"`: Collect essential and personalization cookies.

Code example:

```javascript
Ecwid.setTrackingConsent("DECLINED");
Ecwid.getTrackingConsent();
//{userResponse: "DECLINED", askConsent: false}
```

#### Set cookie consent with HTML

You can override the user's cookie consent with a static value through the [Ecwid HTML integration code](https://support.ecwid.com/hc/en-us/articles/115004678945-Ecwid-for-any-website#-adding-ecwid-to-a-custom-built-website). You need to add a `<script></script>` block right under the integration code with four config lines inside. _All config lines are required_.

The `ec.config.tracking.ask_consent` config must always be `true`.

Value of the `ec.config.tracking.user_response` defines the consent and must be one of the following:

* `"UNDEFINED"`: Customer hasn't given their consent yet.
* `"ACCEPTED"`: Collect all types of cookies.
* `"DECLINED"`: Collect only essential cookies.
* `"ANALYTICS_ONLY"`: Collect essential and analytics cookies only.
* `"PERSONALIZATION_ONLY"`: Collect essential and personalization cookies.

Code example:

```html
<script>
ec.config = ec.config || {};
ec.config.tracking = ec.config.tracking || {};
ec.config.tracking.ask_consent = true;
ec.config.tracking.user_response = "DECLINED";
</script>
```

### Track changes in consent value

The `Ecwid.OnConsentChanged();` method allows you to catch any changes to the consent value.

Code example:

```javascript
Ecwid.OnConsentChanged.add(function(consent) {
    console.log("consent changed to " + consent);
});
Ecwid.setTrackingConsent("DECLINE");
//consent changed to DECLINED
```

### Enable cookie-free mode on the website

You can disable the collection of all non-essential cookies completely by adding a specific config to the [Ecwid HTML integration code](https://support.ecwid.com/hc/en-us/articles/115004678945-Ecwid-for-any-website#-adding-ecwid-to-a-custom-built-website).

Code example:

```html
<script>
window.ec = window.ec || Object();
window.ec.config = window.ec.config || Object();
window.ec.config.disable_all_cookies = true;
</script>
```
