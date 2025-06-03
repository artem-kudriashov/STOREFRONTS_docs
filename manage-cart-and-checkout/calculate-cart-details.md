# Calculate cart details

### `Ecwid.Cart.calculateTotal()`

This method calculates the current cart asynchronously and passes the result as an `order` callback argument with a snapshot of the generated order with essential details.

<details>

<summary>Example of the call and response</summary>

```javascript
Ecwid.Cart.calculateTotal(function(order) {
  console.log(JSON.stringify(order));
});

/* prints

{
    "subtotal": 3500,
    "subtotalWithoutTax": 3500,
    "total": 3850,
    "totalWithoutTax": 3500,
    "tax": 350,
    "couponDiscount": 0,
    "volumeDiscount": 0,
    "customerGroupDiscount": 0,
    "customerGroupVolumeDiscount": 0,
    "discount": 0,
    "shipping": 0,
    "shippingWithoutTax": 0,
    "handlingFee": 0,
    "handlingFeeWithoutTax": 0,
    "pricesIncludeTax": false,
    "cart": {
        "id": "TJ6VG",
        "cartId": "99E7E224-5F6F-4C00-BFE9-9F72F2B5A471",
        "orderId": 506524300,
        "items": [
            {
                "quantity": 3,
                "product": {
                    "id": 455570501,
                    "sku": "0000077",
                    "price": 500,
                    "name": "Pizza #2",
                    "weight": 1,
                    "shortDescription": "",
                    "url": "https://example.company.site/products/Example-product-p455570501"
                },
                "options": {}
            },
            {
                "quantity": 4,
                "product": {
                    "id": 439710255,
                    "sku": "000001",
                    "price": 500,
                    "name": "Pizza",
                    "weight": 1,
                    "shortDescription": "123 pie",
                    "url": "https://wexample.company.site/products/Example-product-2-p439710255"
                },
                "options": {
                    "Size": "L, R",
                    "djbfdmnfb": "1234"
                }
            }
        ],
        "productsQuantity": 7,
        "shippingMethod": "Pickup",
        "shippingPerson": {
            "countryCode": "GE",
            "countryName": "Georgia",
            "name": "Jon Stewart Doe",
            "phone": "16019521325",
            "stateOrProvinceCode": "TB"
        },
        "weight": 7
    }
}

*/
```

</details>

#### `order` argument fields

<table><thead><tr><th width="282">Name</th><th width="120">Type</th><th>Description</th></tr></thead><tbody><tr><td>cart</td><td>object cart</td><td>Contains full cart details after calculation matching the <code>Ecwid.Cart.get()</code> result.</td></tr><tr><td>couponDiscount</td><td>number</td><td>Total discount from applied coupons.</td></tr><tr><td>customerGroupDiscount</td><td>number</td><td>Discount value from customer group discounts.</td></tr><tr><td>customerGroupVolumeDiscount</td><td>number</td><td>Absolute discount from customer group discounts.</td></tr><tr><td>discount</td><td>number</td><td>Total discount value from all sources.</td></tr><tr><td>handlingFee</td><td>number</td><td>Total fees applied to order.</td></tr><tr><td>handlingFeeWithoutTax</td><td>number</td><td>Total fees applied to order before taxes.</td></tr><tr><td>pricesIncludeTax</td><td>boolean</td><td>Specifies if product prices include taxes defining tax calculation formulae. If <code>true</code>, the store works with "gross prices". If <code>false</code> the store works with "net prices".</td></tr><tr><td>shipping</td><td>number</td><td>Total shipping cost.</td></tr><tr><td>shippingWithoutTax</td><td>number</td><td>Total shipping cost before taxes applied.</td></tr><tr><td>subtotal</td><td>number</td><td>Order subtotal. Includes the shopping cart total with discounts and taxes but without shipping costs or handling fees.</td></tr><tr><td>subtotalWithoutTax</td><td>number</td><td>Order subtotal before applied taxes.</td></tr><tr><td>tax</td><td>number</td><td>Total sum of taxes applied to order.</td></tr><tr><td>total</td><td>number</td><td>Order total that includes all costs, fees, taxes, and discounts.</td></tr><tr><td>totalWithoutTax</td><td>number</td><td>Order total before taxes applied.</td></tr><tr><td>volumeDiscount</td><td>number</td><td>Total discount for order subtotal.</td></tr></tbody></table>
