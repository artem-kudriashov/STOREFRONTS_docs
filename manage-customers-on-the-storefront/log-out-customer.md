# Log out customer

### `Ecwid.Customer.signout(success,error)`

This method signs out customer from their account.

Request example:

```javascript
Ecwid.Customer.signOut(function(success,error) { 
  if (success == true) {
      console.log("Customer signed out");
  } else {
      console.log("Signout failed. Error message: " + error);
  }
});

// prints
// Customer signed out
```

Fields available in the response:

| Name    | Type    | Description                                                |
| ------- | ------- | ---------------------------------------------------------- |
| success | boolean | Is `true` if a customer was signed out, `false` otherwise. |
| error   | string  | Error message. Has value only if `success` is `false`      |
