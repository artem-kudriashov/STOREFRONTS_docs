# Get cart details

### Ecwid.Cart.get()

This method allows you to receive full information about the current shopping cart. The response is available in the `cart` [callback](get-cart-details.md#cart-callback-fields).

<details>

<summary>Example of JS call and response</summary>

```javascript
Ecwid.Cart.get(function(cart){
  console.log(JSON.stringify(cart));
});

/* prints

{
    "id": "TJ6VG",
    "cartId": "99E7E224-5F6F-4C00-BFE9-9F72F2B5A471",
    "orderId": 506524300,
    "items": [
        {
            "quantity": 2,
            "product": {
                "id": 455570501,
                "sku": "0000077",
                "price": 500,
                "name": "Pizza #2",
                "weight": 1,
                "shortDescription": "",
                "url": "https://example.company.site/products/Example-product-p455570501",
                "variation": 2343242
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
                "weight": 0.5,
                "shortDescription": "",
                "url": "https://example.company.site/products/Example-product-2-p439710255"
            },
            "options": {
                "Size": "L, R",
                "Print_number": "123"
            }
        }
    ],
    "productsQuantity": 6,
    "shippingMethod": "Pickup",
    "shippingPerson": {
        "countryCode": "GE",
        "countryName": "Georgia",
        "name": "Jhn Doe",
        "phone": "16019521325",
        "stateOrProvinceCode": "TB"
    },
    "weight": 6
}

/*
```

</details>

#### `cart` callback fields

<table><thead><tr><th width="161.31640625">Field</th><th width="197.03125">Type</th><th>Description</th></tr></thead><tbody><tr><td>cartId</td><td>string</td><td>Cart ID. Matches with the cart ID in REST API <code>/carts</code> endpoint.</td></tr><tr><td>id</td><td>string</td><td>Order ID, assigned to the cart. Remains the same when an order is placed and becomes visible to the customer and store owner in notifications and Ecwid admin.</td></tr><tr><td>orderId</td><td>string</td><td>Internal order ID for Ecwid services. Use <code>id</code> field instead.</td></tr><tr><td>items</td><td>array of objects <a href="get-cart-details.md#items">items</a></td><td>Details about products in the shopping cart.</td></tr><tr><td>productsQuantity</td><td>number</td><td>Total quantity of products added to the shopping cart.</td></tr><tr><td>subtotal</td><td>number</td><td>Cart subtotal – cost of all products added to the cart without any discounts, taxes, or shipping costs applied.</td></tr><tr><td>total</td><td>number</td><td>Cart total – total cost of the cart with all available price modifiers applied.</td></tr><tr><td>isPricesIncludeTax</td><td>boolean</td><td>Defines if the order uses gross/net prices.</td></tr><tr><td>tax</td><td>number</td><td>Total tax applied to the cart. May include taxes to both product and shipping costs.</td></tr><tr><td>couponName</td><td>string</td><td>Name of the discount coupon applied to the cart. Does not contain the actual coupon code.</td></tr><tr><td>paymentMethod</td><td>string</td><td>Name of the payment method selected by a customer at the storefront.</td></tr><tr><td>paymentModule</td><td>string</td><td>Internal "module" for the payment method selected by a customer at the storefront.<br><br>Only available for Ecwid-build payment methods.</td></tr><tr><td>weight</td><td>number</td><td>Total weight of products added to the shopping cart.</td></tr><tr><td>shippingMethod</td><td>string</td><td>Name of the selected shipping method. Available only when a customer goes to the <code>checkout_payment_details</code> page.</td></tr><tr><td>shippingPerson</td><td>object <a href="get-cart-details.md#shippingperson">shippingPerson</a> </td><td>Details about shipping address. Available only when a customer goes to the <code>shipping_delivery</code> page.</td></tr><tr><td>billingPerson</td><td>object <a href="get-cart-details.md#shippingperson">shippingPerson</a> </td><td>Details about customer's billing address. Has the same format with the <code>shippingPerson</code>.<br><br>Becomes available only when a customer goes to the payment page.</td></tr></tbody></table>

#### items

`items` contains an array of objects with the details for each product added to the shopping cart.

| Field    | Type                                          | Description                                                                                 |
| -------- | --------------------------------------------- | ------------------------------------------------------------------------------------------- |
| quantity | number                                        | Quantity of the specific product added to the shopping cart.                                |
| product  | object [product](get-cart-details.md#product) | Details about the product added to the shopping cart.                                       |
| options  | object options                                | Map of the selected product options (option name as a `key` and option value as a `value`). |

Code example for `options` object:

```json
"options": {  
    "Size": "M",  
    "Print_number": "9"  
}
```

#### product

<table><thead><tr><th width="208.140625">Field</th><th width="206.078125">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td>number</td><td>Internal product ID.</td></tr><tr><td>sku</td><td>string</td><td>Product SKU.</td></tr><tr><td>price</td><td>number</td><td>Product price before applied taxes, fees, or discounts.</td></tr><tr><td>isCustomerSetPrice</td><td>boolean</td><td>If <code>true</code>, product allows customer to set their own price for it.</td></tr><tr><td>selectedPrice</td><td>number</td><td>If <code>isCustomerSetPrice</code> is <code>true</code>, contains a custom price for the product that the customer entered before adding a product to the cart.</td></tr><tr><td>name</td><td>string</td><td>Product name.</td></tr><tr><td>weight</td><td>number</td><td>Product weight.</td></tr><tr><td>shortDescription</td><td>string</td><td>Product description truncated to 120 characters.</td></tr><tr><td>url</td><td>string</td><td>Link to the product page.</td></tr><tr><td>variation</td><td>number</td><td>If selected options match with one of product variations, this field contains the ID of product variation added to the cart.</td></tr><tr><td>mediaItem</td><td>object <a href="get-cart-details.md#mediaitem">mediaItem</a></td><td>Details about product media (images and video)</td></tr><tr><td>recurringChargeSettings</td><td>object <a href="get-cart-details.md#recurringchargesettings">recurringChargeSettings</a></td><td>Details about subscription customer has chosen for the product. <br><br>Only available for subscription products.</td></tr></tbody></table>

#### shippingPerson

<table><thead><tr><th width="188.38671875">Name</th><th width="115.94140625">Type</th><th>Description</th></tr></thead><tbody><tr><td>name</td><td>string</td><td>Customer's name.</td></tr><tr><td>companyName</td><td>string</td><td>Company name of a customer, if available.</td></tr><tr><td>street</td><td>strin</td><td>Shipping/billing address. Street.</td></tr><tr><td>city</td><td>string</td><td>Shipping/billing address. City.</td></tr><tr><td>countryName</td><td>string</td><td>Shipping/billing address. Country name.</td></tr><tr><td>countryCode</td><td>string</td><td>Shipping/billing address. Country code in ISO 3166-2.</td></tr><tr><td>postalCode</td><td>string</td><td>Shipping/billing address. ZIP code.</td></tr><tr><td>stateOrProvinceCode</td><td>string</td><td>Shipping/billing address. State code ISO 3166-2.</td></tr><tr><td>phone</td><td>string</td><td>Customer's phone number, if available.</td></tr></tbody></table>

#### mediaItem

<table><thead><tr><th width="157.23828125">Name</th><th width="163.8203125">Type</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td>string</td><td>One of:<br><code>PICTURE</code><br><code>VIDEO</code></td></tr><tr><td>isMain</td><td>boolean</td><td><p>Defines if the image is main for the product.<br><br>Products can have only one main image and multiple secondary ones referred as the "gallery".</p><p></p><p>Only for the <code>PICTURE</code> type.</p></td></tr><tr><td>id</td><td>string</td><td><p>Internal image ID.</p><p></p><p>Only for the <code>PICTURE</code> type.</p></td></tr><tr><td>borderInfo</td><td>object <a href="get-cart-details.md#borderinfo">borderInfo</a></td><td><p>Details about image border.</p><p></p><p>Only for the <code>PICTURE</code> type.</p></td></tr><tr><td>width</td><td>number</td><td><p>Image width in pixels. </p><p></p><p>Only for the <code>PICTURE</code> type.</p></td></tr><tr><td>height</td><td>number</td><td><p>Image height in pixels. </p><p></p><p>Only for the <code>PICTURE</code> type.</p></td></tr><tr><td>image160pxUrl</td><td>string</td><td><p>Link to the image resized to fit 160x160px container.</p><p></p><p>Only for the <code>PICTURE</code> type.</p></td></tr><tr><td>image400pxUrl</td><td>string</td><td><p>Link to the image resized to fit 400x400px container.</p><p></p><p>Only for the <code>PICTURE</code> type.</p></td></tr><tr><td>image800pxUrl</td><td>string</td><td><p>Link to the image resized to fit 800x800px container.</p><p></p><p>Only for the <code>PICTURE</code> type.</p></td></tr><tr><td>videoInfo</td><td>object <a href="get-cart-details.md#videoinfo">videoInfo</a></td><td><p>Details about embedded video. </p><p></p><p>Only for the <code>VIDEO</code> type.</p></td></tr></tbody></table>

#### videoInfo

<table><thead><tr><th width="153.7109375">Name</th><th width="98.734375">Type</th><th>Description</th></tr></thead><tbody><tr><td>embedHtml</td><td>string</td><td>String with HTML code for video embedding.</td></tr><tr><td>url</td><td>string</td><td>Link to the video.</td></tr><tr><td>width</td><td>number</td><td>Width of the embedded video.</td></tr><tr><td>height</td><td>number</td><td>Height of the embedded video.</td></tr></tbody></table>

#### borderInfo

| Field           | Type                                                          | Description                         |
| --------------- | ------------------------------------------------------------- | ----------------------------------- |
| dominatingColor | object [dominatingColor](get-cart-details.md#dominatingcolor) | Border color in RGBa format.        |
| homogeneity     | boolean                                                       | Defines if an image is homogeneous. |

#### dominatingColor

<table><thead><tr><th>Field</th><th width="139">Type</th><th>Description</th></tr></thead><tbody><tr><td>isDark</td><td>number</td><td><code>true</code> if the image is considered dark.</td></tr><tr><td>isFullyTransparent</td><td>number</td><td><code>true</code> if the image is considered transparent.</td></tr><tr><td>rbgHexValue</td><td>number</td><td>HEX code for the calculated "medium" color of all outside pixels of the image, for example <code>#2e3236</code>.</td></tr></tbody></table>

#### recurringChargeSettings

<table><thead><tr><th width="273.265625">Field</th><th width="92.80078125">Type</th><th>Description</th></tr></thead><tbody><tr><td>recurringIntervalCount</td><td>number</td><td>Index of the current recurring interval.</td></tr><tr><td>recurringSubscriptionInterval</td><td>string</td><td>How often subscription charges will happen.<br><br>One of: <code>DAY</code>, <code>WEEK</code>, <code>MONTH</code>, <code>YEAR</code>.</td></tr><tr><td>signUpFee</td><td>number</td><td>Additional fee to the first payment for the subscription.</td></tr><tr><td>subscriptionPriceWithSignUpFee</td><td>number</td><td>Total price of the first subscription payment.</td></tr></tbody></table>
