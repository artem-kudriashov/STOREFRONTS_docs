# Open product pages with params

Base JS call:

```javascript
Ecwid.openPage('product', 'id': 72585497);
```

List of additional parameters for the call:

* `'id'` - Internal product ID. This is a **required** parameter for opening product pages.
* `'name'` - Product name for the URL in lowercase, with spaces replaced with dashes. For example, `pizza-33cm`.
* `'slug_value'` - Custom page slug for the product. Use it instead of the `name` parameter if a product has a custom slug.
* `'variation'` - Accepts product variation ID as a value to open a specific product variation.
* `'options'` - Accepts an array of product option choices (dropdown and radio button option types). \
  \
  Option choices are assigned to product options depending on the option index (starts at 1). For example, `'options': [3,1]` selects the third value for the first option, and the first value for the second option.

{% hint style="info" %}
If you pass both `id` and `name` or `id` and `slug_value` parameters, Ecwid JS API will create a product URL and open it without making additional backend requests to confirm the category exists. The choice between the `name` or `slug_value` parameters depends on whether a product has a custom slug.
{% endhint %}

Code examples:

```javascript
Ecwid.openPage('product', {'id': 72585497, 'slug_value': 'best-toys'});

Ecwid.openPage('product', {'id': 45523512, 'name': 'Pizza Roll'});

Ecwid.openPage('product', {'id': 72585497, 'variation': 16351010});

Ecwid.openPage('product', {'id': 72585497, 'options': [2,2]});
```

There is an alternative way to open a page with pre-selected options or a variation **without JS API**. You can add option choices or the variation ID (`?options=1,2,3` or `?variation=123456`) as a query parameter to product page URLs and open it. URL examples:\
`https://example.com/store/example-product?variation=163510`\
`https://example.com/store/example-product?options=4,3`
