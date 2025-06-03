# Set customer's shipping and billing addresses

### `Ecwid.Cart.setAddress()`

This method allows you to prefill the **shipping address** before a customer gets to the checkout.&#x20;

It is useful when you want to remove some address fields, like country or state. Prefill address fields with this method and then hide them with CSS `{display: none;}` style.

The method has three arguments: `address` with the address details and two function callbacks, `successCallback` called if the method works successfully, and `errorCallback` called if it fails.

```javascript
Ecwid.Cart.setAddress(
	{
		"name": "John Carmichael",
  	"companyName": "Cool Slippers",
  	"street": "5th Ave",
  	"city": "New York",
  	"countryName": "United States",
  	"postalCode": "10002",
  	"stateOrProvinceCode": "NY",
  	"phone": "+1 234 523 11 42"
  },
  function(successCallback){ console.log('Success') },
  function(errorCallback){ console.log('Fail') }
);

// prints
// Success
```

Address fields in this method match the `shippingPerson` object.

### `Ecwid.Cart.setBillingAddress()`

This method allows you to prefill the customer billing address before customers get to the checkout. It accepts three arguments: `address` with the address details and two function callbacks, `successCallback` called if the method works successfully, and `errorCallback` called if it fails.

```javascript
Ecwid.Cart.setBillingAddress(
	{
		"name": "John Carmichael",
  	"companyName": "Cool Slippers",
  	"street": "5th Ave",
  	"city": "New York",
  	"countryName": "United States",
  	"postalCode": "10002",
  	"stateOrProvinceCode": "NY",
  	"phone": "+1 234 523 11 42"
  },
  function(successCallback){ console.log('Success') },
  function(errorCallback){ console.log('Fail') }
);

// prints
// Success
```

Address fields in this method match the `shippingPerson` object.
