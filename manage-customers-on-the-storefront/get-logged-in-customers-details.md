# Get logged in customer's details

### `Ecwid.Customer.get(customer)`

This method receives all data on the customer currently logged in to the store.

Request example:

```javascript
Ecwid.Customer.get(function(customer) { 
  console.log(customer.email);
});

// prints
// example@example.com
```

Fields available in the returned `customer` argument:

<table><thead><tr><th width="197">Field</th><th width="181">Type</th><th>Description</th></tr></thead><tbody><tr><td>email</td><td>string</td><td>Customer's email.</td></tr><tr><td>id</td><td>number</td><td>Customer's internal ID.</td></tr><tr><td>ownerId</td><td>number</td><td>Internal store ID.</td></tr><tr><td>registered</td><td>string</td><td>Customer's registration date in a stringified UNIX timestamp format. <br><br>For example, <code>"1718010611"</code>.</td></tr><tr><td>billingPerson</td><td>object <a href="get-logged-in-customers-details.md#billingperson">billingPerson</a></td><td>Customer's saved billing address.</td></tr><tr><td>shippingAddresses</td><td>array of objects <a href="get-logged-in-customers-details.md#shippingaddresses">shippingAddresses</a></td><td>Customer's saved shipping addresses.</td></tr></tbody></table>

#### billingPerson

<table><thead><tr><th width="217">Field</th><th width="140">Type</th><th>Description</th></tr></thead><tbody><tr><td>name</td><td>string</td><td>Full name of the customer.</td></tr><tr><td>companyName</td><td>string</td><td>Customer's company name.</td></tr><tr><td>street</td><td>string</td><td>Address line 1 and address line 2, separated by <code>\n</code>.</td></tr><tr><td>city</td><td>string</td><td>City.</td></tr><tr><td>countryCode</td><td>string</td><td>Two-letter country code.</td></tr><tr><td>countryName</td><td>string</td><td>Country name.</td></tr><tr><td>postalCode</td><td>string</td><td>Postal/ZIP code.</td></tr><tr><td>stateOrProvinceCode</td><td>string</td><td>State/province code, for example, <code>NY</code>.</td></tr><tr><td>phone</td><td>string</td><td>Customer's phone number.</td></tr></tbody></table>

#### shippingAddresses

<table><thead><tr><th width="130">Field</th><th width="200">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>number</td><td><p>Ordered ID of saved shipping address.<br></p><p>Starts with <code>0</code> and iterates by <code>1</code>.</p></td></tr><tr><td>person</td><td>object <a href="get-logged-in-customers-details.md#billingperson">billingPerson</a></td><td>Details of the saved shipping address.</td></tr></tbody></table>

