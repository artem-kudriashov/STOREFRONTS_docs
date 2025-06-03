# Open search page with params

Base JS call:

```javascript
Ecwid.openPage('search');
```

List of additional parameters for the call:

* `'keyword'`: Search string for product title, description, and SKU.
* `'inventory'`: Supports only one value: if `instock`, only products "In stock" are returned.
* `'onsale'`: Supports only one value: if `onsale`, only products with "Compare to" prices are returned.
* `'priceFrom'`: Minimum product price for search, for example, `500.00`.
* `'priceTo'`: Maximum product price for search, for example, `899.99`.
* `'offset'`: Offset from the beginning of the returned items list. Default is 0.
* `'categories'`: Category IDs for search, for example: `0,123456,8236623`
* `'includeProductsFromSubcategories'`: Supports two values: if `true`, the search includes products from subcategories of selected categories, `false` otherwise. Default is `true`.
* `'attribute_[name]=[values]'`: Search by product attributes. Accepts several values separated by a comma. To search for an exact match to attribute value, enclose it in quotation marks.
* `'option_[name]=[values]'`: Search by product options. Accepts several values separated by a comma. To search for an exact match to option value, enclose it in quotation marks.
* `'createdFrom'`: Product creation datetime (lower bound) matching REST API date format, for example, `createdFrom=2020-01-30 10:00:00 +0000`.
* `'createdTo'`: Product creation datetime (upper bound) matching REST API date format, for example, `createdFrom=2020-01-30 10:00:00 +0000`.

Code examples:

```javascript
Ecwid.openPage('search', {'keyword': 'surfboard', 'page': 2});

Ecwid.openPage('search', {'priceTo': '50'});

Ecwid.openPage(
    'search', 
    {
      'keyword': 'shoes', 
      'attribute_Brand': 'Nike',
      'inventory': 'instock',
      'offset': 50
    }
  );
```
