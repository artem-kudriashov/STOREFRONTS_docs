# Get storefront language and currency

### `Ecwid.getStorefrontLang()`

This method responds with the current storefront language in ISO 639-1 language code. Use it to dynamically translate custom content on the page.

Code example:

```javascript
var lang = Ecwid.getStorefrontLang();
console.log(lang);

//prints
// "en"
```

### `Ecwid.formatCurrency()`

This method allows you to get store currency settings on the storefront. It is useful if you need to add a widget that displays some price to customers.

It accepts a numeric price as an argument and responds with a formatted price using store settings: currency symbol, and delimiter symbol and precision.

Code example:

```javascript
var currencyFormat = Ecwid.formatCurrency(12.99);
console.log(currencyFormat);

// prints
// "$12.99"
```
