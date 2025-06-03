# Set customer's email for the checkout

### `Ecwid.Cart.setCustomerEmail()`

This method allows you to pre-define customer email with JavaScript. Combined with the `Ecwid.Cart.gotoCheckout()` you can skip the first checkout step. The method has three callback arguments: `email`, `successCallback` and `errorCallback`.

The `email` argument defines the customer email, and callback arguments are functions called if the method works successfully or fails.

Code example:

```javascript
Ecwid.Cart.setCustomerEmail(
    "example@example.com",
    function (successCallback) { console.log("Success") },
    function (errorCallback) { console.log("Fail") }
);

// prints
// Success
```
