# Fully clear the cart

### `Ecwid.Cart.clear()`

This method allows you to clear all details from the shopping cart. It has a callback function with two arguments: `success` (boolean) and `error` (string). If the method clears the cart successfully, you receive `true` in the `success` argument.

Code example:

```javascript
Ecwid.Cart.clear(function(success,error) { 
  if (success == true) {
      console.log("Cart was cleared");
  } else {
      console.log("Cart clear failed. Error message: " + error);
  }
});

// prints
// Cart was cleared
```
