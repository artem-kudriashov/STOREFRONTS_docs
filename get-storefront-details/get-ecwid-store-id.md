# Get Ecwid store ID

### `Ecwid.getOwnerId()`

This method allows you to receive the store ID. Works on any opened storefront page.

Code example:

```javascript
var storeId = Ecwid.getOwnerId()
console.log(storeId);

// prints
// 1003
```

{% hint style="info" %}
If you need to make this call on the main Instant Site page, use `window.instantsite.getSiteId();` call instead.
{% endhint %}
