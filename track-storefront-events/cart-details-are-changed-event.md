# "Cart details are changed" event

### `Ecwid.OnCartChanged`

This event allows tracking any cart changes excluding the payment method selection. Its callback function with the `cart` [argument](cart-details-are-changed-event.md#cart-argument-fields) contains details about the cart after the change event.

`Ecwid.OnCartChanged` event triggers when:

* Cart is initialized, synced, or cleared.
* Product has been added, updated (increased quantity, changed selected options), or removed from the cart.
* Discount coupon or discount is applied or removed.
* Shipping address is added or updated.
* Shipping method is selected or changed.

Code example:

```javascript
Ecwid.OnCartChanged.add(function(cart){
    console.log(JSON.stringify(cart));
});

// prints
// 
// {
// 	"id":"TJ6VG",
// 	"cartId":"99E7E224-5F6F-4C00-BFE9-9F72F2B5A471",
// 	"orderId":506524300,
// 	"items":[...],
// 	"productsQuantity":4,
// 	"shippingMethod":"Standard shipping",
// 	"shippingPerson":{...},
// 	"weight":4
// }
```

#### `cart` argument fields

<table><thead><tr><th width="211">Field</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>cartId</td><td>string</td><td>Cart ID. Matches with the cart ID in REST API <code>/carts</code> endpoint.</td></tr><tr><td>id</td><td>string</td><td>Order ID, assigned to the cart. Remains the same when an order is placed.</td></tr><tr><td>couponName</td><td>string</td><td>Name of the discount coupon applied to the cart. Does not contain the actual coupon code.</td></tr><tr><td>items</td><td>array{object}</td><td>Details about products in the shopping cart.</td></tr><tr><td>orderId</td><td>number</td><td>Internal order ID.</td></tr><tr><td>productsQuantity</td><td>number</td><td>Total quantity of products added to the shopping cart.</td></tr><tr><td>weight</td><td>number</td><td>Total weight of products added to the shopping cart.</td></tr><tr><td>shippingMethod</td><td>string</td><td>Name of the selected shipping method. Available only when a customer goes to the <code>checkout_payment_details</code> page.</td></tr><tr><td>shippingPerson</td><td>object{shippingPerson}</td><td>Details about shipping address. Available only when a customer goes to the <code>shipping_delivery</code> page.</td></tr></tbody></table>

#### `items`

`items` contains an array of objects with the details for each product added to the shopping cart.

| Field    | Type           | Description                                                                             |
| -------- | -------------- | --------------------------------------------------------------------------------------- |
| quantity | number         | Quantity of the specific product added to the shopping cart.                            |
| product  | object product | Details about the product added to the shopping cart.                                   |
| options  | object         | Map of the selected product options (option name as a key and option value as a value). |

Code example for options object:

```json
"options": {  
    "Size": "M",  
    "Print_number": "9"  
}
```

#### `product`

| Field            | Type   | Description                                             |
| ---------------- | ------ | ------------------------------------------------------- |
| id               | number | Internal product ID.                                    |
| sku              | string | Product SKU.                                            |
| price            | number | Product price before applied taxes, fees, or discounts. |
| name             | string | Product name.                                           |
| weight           | number | Product weight.                                         |
| shortDescription | string | Product description truncated to 120 characters.        |
| url              | string | Link to the product page.                               |
| variation        | number | Product variation ID.                                   |

#### `shippingPerson`

| Name                | Type             | Description                                           |
| ------------------- | ---------------- | ----------------------------------------------------- |
| name                | string           | Customer's name.                                      |
| companyName         | string, optional | Company name of a customer, if available.             |
| street              | string, optional | Shipping/billing address. Street.                     |
| city                | string, optional | Shipping/billing address. City.                       |
| countryName         | string, optional | Shipping/billing address. Country name.               |
| countryCode         | string, optional | Shipping/billing address. Country code in ISO 3166-2. |
| postalCode          | string, optional | Shipping/billing address. ZIP code.                   |
| stateOrProvinceCode | string, optional | Shipping/billing address. State code ISO 3166-2.      |
| phone               | string, optional | Customer's phone number, if available.                |

