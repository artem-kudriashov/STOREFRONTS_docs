# Open category pages with params

Base JS call:

```javascript
Ecwid.openPage('category');
```

List of additional parameters for the call:

* `'id'` - Category ID. If not specified, Ecwid will ignore any other params and open the main (root) category page (same as `'id': 0`).
* `'name'` - Category name as it would look in the URL: lowercase, spaces replaced with dashes. For example, the "Rental Spaces" category name would transform into `rental-spaces`.
* `'slug_value'` - Custom page slug for the category. Use it instead of the `name` parameter if a category has a custom slug.
* `'page'` - Page number for categories where products don't fit on one page. If you pass a value bigger than the number of pages in the category, Ecwid will open the last page.

{% hint style="info" %}
If you pass both `id` and `name` or `id` and `slug_value` parameters, Ecwid JS API will create a category URL and open it without making additional backend requests to confirm the category exists. The choice between the `name` or `slug_value` parameters depends on whether a category has a custom slug.
{% endhint %}

Code example:

```javascript
Ecwid.openPage('category', {'id': 20671017, slug_value: 'rental', 'page': 2});
```

You can also open the side menu with product filters on category pages with the `Ecwid.showProductFilters();` call.

Code example:

```javascript
Ecwid.openPage('category', 'id': 20671017);

Ecwid.showProductFilters();
```
