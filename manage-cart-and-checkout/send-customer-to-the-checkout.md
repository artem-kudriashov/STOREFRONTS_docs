# Send customer to the checkout

### `Ecwid.Cart.canGotoCheckout()`

This method checks whether you can send customers to the first step of the checkout called the **shopping cart**.&#x20;

It has one `callback` argument containing the boolean response. If `true`, you can send customers to the checkout with the `Ecwid.Cart.gotoCheckout()` method.

```javascript
Ecwid.Cart.canGotoCheckout(function(callback){
  console.log(callback);
});

// prints
// true
```

You can only receive `false` with this method if the store works through an old storefront and the _Ecwid admin > Settings > Legal > Terms & Conditions toggle_ is enabled.

### `Ecwid.Cart.gotoCheckout()`

This method sends a customer to the **first or second checkout step**.

This method works differently depending on the _Ecwid admin > Settings > Legal > Terms & Conditions toggle_ and whether the customer has already left an email in the shopping cart:&#x20;

* **No email**: the customer is sent to the shopping cart page.
* **Email + toggle disabled**: the customer is sent to the second checkout page (address details)
* **Email + toggle disabled + no shipping**: the customer is sent to the payment page.

Code example:

```javascript
Ecwid.Cart.gotoCheckout(function(){
  console.log("Checkout process started");
});

// prints
// Checkout process started
// Customer is redirected to the checkout
```
