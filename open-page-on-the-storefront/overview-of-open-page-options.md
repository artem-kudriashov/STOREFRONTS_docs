# Overview of open page options

This method allows you to open a specific page on the storefront. The function accepts page slugs and additional parameters in its arguments.

For example, you can use these redirects in different promo activities:

* Create a popup with a sale product and redirect customers to this product on click.
* Offer customers to log in to receive some bonus.
* Redirect customers to the search page with pre-configured terms showing promo products.

Code examples:

{% tabs %}
{% tab title="Redirect customers to the cart page" %}
Create a custom cart icon and assign redirect to the cart page with a single line of code executed on the click:

```javascript
Ecwid.openPage('cart')
```
{% endtab %}

{% tab title="Open search page with shoes of one brand" %}
Promote a specific product type and brand with a pre-configured search:

```javascript
Ecwid.openPage(
    'search', 
    {
        'keyword': 'shoes', 
        'attribute_Brand': 'Nike',
        'inventory': 'instock'
    }
);
```
{% endtab %}
{% endtabs %}

### Full list of available pages

* `'product'` - Product page. Additional params allow you to pre-select options or even variations.&#x20;
* `'category'` - Page of a specific category.
* `'search'` - Search products page. Additional params allow you to make preconfigured search links.
* `'cart'` - Checkout step 1. Customers enter their email and apply discount coupons.
* `'checkout/address'` - Checkout step 2. Customers enter their address.
* `'checkout/shipping'` - Checkout step 3. Customers choose shipping/pickup method.
* `'checkout/payment'` - Checkout step 4. Customers choose a payment method and go to the payment page.
* `'checkout/order-confirmation'`- "Thank you for purchase" page customers see after placing an order.
* `'account'` - Customer's account page.
* `'account/address-book'`- Customer's account page (saved shipping addresses).
* `'account/favorites'`- Customer's account page (products added to favorites).
* `'pages/about'` - Legal page (about the store).
* `'pages/shipping-payment'` - Legal page (shipping/payment policies).
* `'pages/returns'` - Legal page (return policy).
* `'pages/terms'` - Legal page (Terms of use).
* `'pages/privacy-policy'` - Legal page (Cookie/Privacy policies).

Learn more about pages that can be opened with additional params:

{% content-ref url="open-product-pages-with-params.md" %}
[open-product-pages-with-params.md](open-product-pages-with-params.md)
{% endcontent-ref %}

{% content-ref url="open-category-pages-with-params.md" %}
[open-category-pages-with-params.md](open-category-pages-with-params.md)
{% endcontent-ref %}

{% content-ref url="open-search-page-with-params.md" %}
[open-search-page-with-params.md](open-search-page-with-params.md)
{% endcontent-ref %}

{% content-ref url="open-account-pages-with-params.md" %}
[open-account-pages-with-params.md](open-account-pages-with-params.md)
{% endcontent-ref %}
