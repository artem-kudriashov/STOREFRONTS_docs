# Set customer's comments for order

### `Ecwid.Cart.setOrderComments()`

This method allows you to pre-define customer comments for order with JavaScript. The method has three callback arguments: `orderComments`, `successCallback` and `errorCallback`.

The `orderComments` argument defines the customer's comments and callback functions.

Code example:

```javascript
Ecwid.Cart.setOrderComments(
    "Please ask courier to call  1-800 on the door",
    function (successCallback) { console.log("Success") },
    function (errorCallback) { console.log("Fail") }
);

// prints
// Success
```
