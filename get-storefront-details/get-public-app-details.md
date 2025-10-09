# Get public app details

There are several methods in JS API created specifically for public applications.

### `Ecwid.getAppPublicToken('client_id')`

This method accepts app `client_id` as an argument and responds with a public access token for the app. Public tokens are safe to use on the storefront, as they won't be able to reveal any private store data.

Code example:

```javascript
var publicToken = Ecwid.getAppPublicToken('my-cool-app');
console.log(publicToken);

// prints
// public_qKDUqKkNXzcj9DejkMUqEkYLq2E6BXM9
```

{% hint style="info" %}
If you need to make this call on the main Instant Site page, use `window.instantsite.getAppPublicToken('client_id');` call instead.
{% endhint %}

### `Ecwid.getAppPublicConfig('client_id')`

This method accepts app `client_id` as an argument and responds with a "public config" for the app, which is the data saved in App Storage as a public key. Read more about setting up [App Storage](https://app.gitbook.com/s/uOzT5egoVTAjMJwRuMQT/launch-apps/native-and-external-apps/build-user-settings-page-for-ecwid-admin/manage-personal-user-settings-storage#about-app-storage).

Code example:

```javascript
var publicConfig = Ecwid.getAppPublicConfig("client_id");
console.log(publicConfig);

// prints
// {"key": "public","value": "{'color':'red','text':'Email button','border-radius':'3px'}"}
```

{% hint style="info" %}
If you need to make this call on the main Instant Site page, use `window.instantsite.getAppPublicConfig('client_id');` call instead.
{% endhint %}

### `Ecwid.getInitializedWidgets()`

This method responds with a list of widgets currently loaded on the website. Full list of widgets:

* `Minicart` - Minicart widget
* `SearchPanel` - Search widget
* `ProductBrowser` - Main storefront widget, contains full Ecwid store
* `Categories` - Horizontal categories menu widget
* `Product` - Widget with an embedded product page

Code example:

```javascript
var widgets = Ecwid.getInitializedWidgets();
console.log(widgets);

// prints 
// ["Minicart", "SearchPanel", "ProductBrowser"]
```
