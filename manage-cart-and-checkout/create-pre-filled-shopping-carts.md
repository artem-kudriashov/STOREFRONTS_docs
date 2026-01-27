# Create pre-filled shopping carts

Checkout API allows you to create URLs that open a shopping cart and fill it with products and delivery details. These links can be used for promotions or sharing pre-filled carts with customers.

Here's how you can get such a link:

* Create a JSON with cart details using the cart structure from JS API cart management methods.

{% hint style="info" %}
Only the `products` field is required for the method to work.
{% endhint %}

* Convert it to a string ( `JSON.stringify()` ).
* Encode it to URI format (`encodeURIComponent()` ).&#x20;
* Combine it with the base URL to get the resulting URL. Use the code example below to get the format.

<details>

<summary>Code example</summary>

```javascript
var cartPageLink = "https://mywebsite.com/store#!/~/cart/create=";

// For Wix users, it'll be:
// var cartPageLink = "https://mywebsite.com/!/~/cart/create="

var cartItems = [{
    "id": 66821181, // ID of the product in Ecwid
    "quantity": 3, // Quantity of products to add
    "options": { // Specify product options
        "Color": "White",
        "Size":"11oz"
    }
}, {
    "id": 66722581,
    "quantity": 5
}];

var cart = {
     "gotoCheckout": true, // go to next checkout step right away (after 'Cart' page)
     "products": cartItems, // products to add to cart
     "profile": {
         "address": { // Shipping address details
             "name": "john smith",
             "companyName": "general motors",
             "street": "5th Ave",
             "city": "New York",
             "countryCode": "US",
             "postalCode": "10002",
             "stateOrProvinceCode": "NY",
             "phone": "+1 234 235 22 12"
         },
         "billingAddress": { // Billing address details
             "countryCode": "US",
             "stateOrProvinceCode": "AL",
         },
         "email": "test@test.com", // Customer email
         "orderComments": "Comments!" // Order comments
     }
 }

cart = JSON.stringify(cart);
cartCode = encodeURIComponent(cart);

// For Wix users, it'll be:
// cartCode = encodeURIComponent(btoa(cart));

console.log(cartCode);

// prints the resulting string used for creating the cart
//
// %7B%22gotoCheckout%22%3Atrue%2C%22products%22%3A%5B%7B%22id%22%3A66821181%2C%22quantity%22%3A3%2C%22options%22%3A%7B%22Color%22%3A%22White%22%2C%22Size%22%3A%2211oz%22%7D%7D%2C%7B%22id%22%3A66722581%2C%22quantity%22%3A5%7D%5D%2C%22profile%22%3A%7B%22address%22%3A%7B%22name%22%3A%22john%20smith%22%2C%22companyName%22%3A%22general%20motors%22%2C%22street%22%3A%225th%20Ave%22%2C%22city%22%3A%22New%20York%22%2C%22countryCode%22%3A%22US%22%2C%22postalCode%22%3A%2210002%22%2C%22stateOrProvinceCode%22%3A%22NY%22%2C%22phone%22%3A%22%2B1%20234%20235%2022%2012%22%7D%2C%22billingAddress%22%3A%7B%22countryCode%22%3A%22US%22%2C%22stateOrProvinceCode%22%3A%22AL%22%7D%2C%22email%22%3A%22test%40test.com%22%2C%22orderComments%22%3A%22Comments!%22%7D%7D
//

finalLink = cartPageLink+cartCode
console.log(finalLink);

// prints a completed link that you can share with customers

```



</details>

{% hint style="info" %}
If you use a Wix website, you need to base64-encode cart URL with `btoa()` method before using `encodeURIComponent()`.\
\
Additionally, you'll need to change base cart URL to `"https://mywebsite.com/!/~/cart/create="` &#x20;
{% endhint %}
