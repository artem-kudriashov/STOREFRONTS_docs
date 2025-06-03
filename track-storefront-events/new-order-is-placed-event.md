# "New order is placed" event

### `Ecwid.OnOrderPlaced`

This event allows tracking placed orders on the storefront and receiving order details in a callback function with an `order` argument.

Code example:

```javascript
Ecwid.OnAPILoaded.add(() => {
    Ecwid.OnOrderPlaced.add((order) => {
        console.log(order.total);
    });
});

// prints
// 829
```

#### `order` callback argument

<table><thead><tr><th width="229">Name</th><th width="158">Type</th><th>Description</th></tr></thead><tbody><tr><td>items</td><td>array of objects <a href="new-order-is-placed-event.md#items">items</a></td><td>Details about products in order.</td></tr><tr><td>productsQuantity</td><td>number</td><td>Total quantity of products in order.</td></tr><tr><td>weight</td><td>number</td><td>Total order weight.</td></tr><tr><td>paymentMethod</td><td>string</td><td>Selected payment method name. <code>undefined</code> if no method is selected.</td></tr><tr><td>shippingMethod</td><td>string</td><td>Selected shipping method name. <code>undefined</code> if no method is selected.</td></tr><tr><td>shippingCarrierName</td><td>string</td><td>Selected shipping carrier name. <code>undefined</code> if no method is selected.</td></tr><tr><td>total</td><td>number</td><td>Order total cost including subtotal, discounts, coupons, taxes, fees, and shipping.</td></tr><tr><td>totalWithoutTax</td><td>number</td><td>Order total without taxes.</td></tr><tr><td>subtotal</td><td>number</td><td>Order subtotal (product cost before shipping cost applied).</td></tr><tr><td>subtotalWithoutTax</td><td>number</td><td>Order subtotal without taxes.</td></tr><tr><td>tax</td><td>number</td><td>Order total tax.</td></tr><tr><td>couponName</td><td>string</td><td>Applied discount coupon name. <code>undefined</code> if no discount coupon is applied.</td></tr><tr><td>couponDiscount</td><td>number</td><td>Value of coupon discount applied to order.</td></tr><tr><td>volumeDiscount</td><td>number</td><td>Value of discount applied to subtotal (doesn't include discount coupon).</td></tr><tr><td>customerGroupDiscount</td><td>number</td><td>Discount based on customer group.</td></tr><tr><td>discount</td><td>number</td><td>Total discount applied to order.</td></tr><tr><td>shipping</td><td>number</td><td>Order shipping cost.</td></tr><tr><td>shippingWithoutTax</td><td>number</td><td>Order shipping cost without taxes.</td></tr><tr><td>handlingFee</td><td>number</td><td>Order handling fee.</td></tr><tr><td>handlingFeeWithoutTax</td><td>number</td><td>Order handling fee without taxes.</td></tr><tr><td>shippingAndHandling</td><td>number</td><td>Sum of <code>shipping</code> and <code>handlingFee</code> fields.</td></tr><tr><td>billingPerson</td><td>object <a href="new-order-is-placed-event.md#billingperson">billingPerson</a></td><td>Customer billing address.</td></tr><tr><td>shippingPerson</td><td>object <a href="new-order-is-placed-event.md#shippingperson">shippingPerson</a></td><td>Customer shipping address.</td></tr><tr><td>affiliateId</td><td>string</td><td>Affiliate ID used in order.</td></tr><tr><td>orderNumber</td><td>number</td><td>Internal order ID. Use ID from <code>vendorNumber</code> instead.</td></tr><tr><td>vendorNumber</td><td>string</td><td>Order ID. Matches order <code>id</code> in REST API and customer emails.</td></tr><tr><td>date</td><td>string</td><td>Order creation datetime in UNIX timestamp, for example, <code>"1484638550"</code>.</td></tr><tr><td>paymentStatus</td><td>string</td><td><p>Payment status of an order. <br></p><p>One of:</p><p><code>AWAITING_PAYMENT</code></p><p><code>PAID</code></p><p><code>CANCELLED</code></p><p><code>REFUNDED</code></p><p><code>PARTIALLY_REFUNDED</code></p><p><code>INCOMPLETE</code></p><p><code>CUSTOM_PAYMENT_STATUS_1</code></p><p><code>CUSTOM_PAYMENT_STATUS_2</code></p><p><code>CUSTOM_PAYMENT_STATUS_3</code></p></td></tr><tr><td>fulfillmentStatus</td><td>string</td><td><p>Fulfillment status of an order. </p><p></p><p>One of: </p><p><code>AWAITING_PROCESSING</code></p><p><code>PROCESSING</code></p><p><code>SHIPPED</code></p><p><code>DELIVERED</code></p><p><code>WILL_NOT_DELIVER</code></p><p><code>RETURNED</code></p><p><code>READY_FOR_PICKUP</code></p><p><code>CUSTOM_FULFILLMENT_STATUS_1</code></p><p><code>CUSTOM_FULFILLMENT_STATUS_2</code></p><p><code>CUSTOM_FULFILLMENT_STATUS_3</code></p></td></tr><tr><td>customer</td><td>object <a href="new-order-is-placed-event.md#customer">customer</a></td><td>Customer's email and name.</td></tr><tr><td>extraFields</td><td>object <a href="new-order-is-placed-event.md#extrafields">extraFields</a></td><td>Order extra field details.</td></tr></tbody></table>

#### `items`

| Name     | Type           | Description                        |
| -------- | -------------- | ---------------------------------- |
| quantity | number         | Quantity of this product in order. |
| product  | object product | Product details.                   |
| options  | array          | Selected product options.          |

#### `product`

| Name             | Type    | Description                                      |
| ---------------- | ------- | ------------------------------------------------ |
| id               | Integer | Product ID.                                      |
| name             | String  | Product name.                                    |
| price            | Integer | Product price.                                   |
| shortDescription | String  | Product description truncated to 120 characters. |
| sku              | String  | Product SKU.                                     |
| url              | String  | Link to a product page.                          |
| weight           | Integer | Product weight.                                  |

#### `billingPerson`

| Name                | Type   | Description              |
| ------------------- | ------ | ------------------------ |
| name                | string | Customer's name.         |
| phone               | string | Customer's phone number. |
| companyName         | string | Customer's company name. |
| street              | string | Address: street.         |
| city                | string | Address: city.           |
| countryName         | string | Address: country name.   |
| countryCode         | string | Address: country code.   |
| stateOrProvinceName | string | Address: state name.     |
| stateOrProvinceCode | string | Address: state code.     |
| postalCode          | string | Address: zip code.       |

#### `shippingPerson`&#x20;

| Name                | Type   | Description              |
| ------------------- | ------ | ------------------------ |
| name                | string | Customer's name.         |
| phone               | string | Customer's phone number. |
| companyName         | string | Customer's company name. |
| street              | string | Address: street.         |
| city                | string | Address: city.           |
| countryName         | string | Address: country name.   |
| countryCode         | string | Address: country code.   |
| stateOrProvinceName | string | Address: state name.     |
| stateOrProvinceCode | string | Address: state code.     |
| postalCode          | string | Address: zip code.       |

#### `customer`

| Name  | Type   | Description       |
| ----- | ------ | ----------------- |
| name  | string | Customer's name.  |
| email | string | Customer's email. |

#### `extraFields`

| Name                       | Type   | Description                                                                                 |
| -------------------------- | ------ | ------------------------------------------------------------------------------------------- |
| orderBy                    | number | Sorting position for order details page in Ecwid admin. Starts with `0` (highest position). |
| title                      | string | Extra field name.                                                                           |
| orderDetailsDisplaySection | string | Section where the extra field is displayed.                                                 |
| type                       | string | Extra field type.                                                                           |
| value                      | string | Extra field value.                                                                          |
