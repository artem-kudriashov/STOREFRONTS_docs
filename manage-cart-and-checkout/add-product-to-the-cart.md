# Add product to the cart

### `Ecwid.Cart.addProduct()`&#x20;

This method allows you to add a new product position to the shopping cart. It accepts two arguments: `product` and `callback`:

* `product` argument accepts either product ID or a product object with extended details including product ID, quantity, selected options, or subscription product settings.
* `callback` allows you to execute any app logic that depends on the result of the operation, for example, updating the checkout UI or refreshing the cart. Use callback to ensure that your logic runs only after the product has been successfully added.

When you use this method, it first checks the product by specified ID for stock and variations. If the selected options match one of the variations, Ecwid will check its stock first. If you don't have enough stock to add a product, Ecwid adds the available quantity. If the product is out of stock, nothing is added to the shopping cart.

Code example:

```javascript
var product = {
  id: 10,
  quantity: 3,
  options: {
    "Size": "L"
  },
  recurringChargeSettings: { 
    recurringInterval: "month",
    recurringIntervalCount: 1,
    },
  callback: function(success, product, cart) {
    // ...  
  }
}

Ecwid.Cart.addProduct(product);
```

#### `product` argument fields

<table><thead><tr><th width="235">Field</th><th width="100">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>number</td><td>Internal product ID.</td></tr><tr><td>quantity</td><td>number</td><td>Quantity of the product that will be added to the cart.</td></tr><tr><td>options</td><td>object options</td><td>Map of the selected product options (option name as a key and option value as a value).</td></tr><tr><td>selectedPrice</td><td>string</td><td>Selected price for the product with the parameter <code>"nameYourPriceEnabled": true</code>. If specified for a product with <code>"nameYourPriceEnabled": false</code>, the product will be added with the default price.</td></tr><tr><td>recurringChargeSettings</td><td>string</td><td>Defines subscription product settings if needed.</td></tr><tr><td>callback</td><td>string</td><td>Defines the callback function.</td></tr></tbody></table>

Code example for options object:

```json
"options": {  
    "Size": "M",  
    "Print_number": "9"  
}
```

#### `recurringChargeSettings`

<table><thead><tr><th width="219">Field</th><th width="119">Type</th><th>Description</th></tr></thead><tbody><tr><td>recurringInterval</td><td>string</td><td>Charge recurring interval. Supported values: <code>DAY</code>, <code>WEEK</code>, <code>MONTH</code>, <code>YEAR</code>.</td></tr><tr><td>recurringIntervalCount</td><td>number</td><td>Charge recurring interval. Supported values: for <code>DAY</code> - 1 (daily), for <code>WEEK</code> - 1 (weekly), 2 (biweekly), for <code>MONTH</code> - 1 (monthly), 3 (quarterly), for <code>YEAR</code> - 1 (annually).</td></tr></tbody></table>

#### `callback`

Callback function receives 4 arguments: **success**, **product**, **cart**, **error**

<table><thead><tr><th width="132">Name</th><th width="192">Type</th><th>Description</th></tr></thead><tbody><tr><td>success</td><td>boolean</td><td>Indicates operation status. If <code>true</code> - the product was added to the shopping cart.</td></tr><tr><td>product</td><td>object <a href="get-cart-details.md#product">product</a></td><td><code>product</code> object after the operation.</td></tr><tr><td>cart</td><td>object <a href="get-cart-details.md#cart-callback-fields">cart</a></td><td><code>cart</code> object after the operation.</td></tr><tr><td>error</td><td>string</td><td>If <code>success</code> is <code>false</code>, contains error message.</td></tr></tbody></table>
