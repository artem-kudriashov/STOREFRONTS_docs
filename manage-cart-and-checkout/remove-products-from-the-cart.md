# Remove products from the cart

### `Ecwid.Cart.removeProduct()`

This method removes product position from the shopping cart entirely. It accepts two arguments: `index` and `callback`:

* `index` allows you to specify which product position in the cart you want to remove. The specified product will be removed completely even if its quantity is greater than zero.
* `callback` allows you to execute any app logic that depends on the result of the operation, for example, updating the checkout UI or refreshing the cart. Use `callback` to ensure that your logic runs only after the product has been successfully removed.

{% hint style="warning" %}
This method completely removes the product from the cart. If you want to decrease its quantity, use `Ecwid.Cart.get()` to save product details on your side, then remove the product with `Ecwid.Cart.removeProduct()` and add it back with all the same details except for the decreased quantity with `Ecwid.Cart.addProduct()`.
{% endhint %}

To remove a product position from the cart, first, you need to get an index with the `Ecwid.Cart.get()` method. Position of the product in the `items` array is the index. For example, if you have two different products added to the cart, the first product has an index of `0`, and the second has an index of `1`.

Code example.

```javascript
Ecwid.Cart.removeProduct(0);
```

#### `callback`

Callback function receives 5 arguments: **success**, **itemsRemovedQuantity**, **product**, **cart**, **error**

<table><thead><tr><th width="205.5859375">Name</th><th width="138.8125">Type</th><th>Description</th></tr></thead><tbody><tr><td>success</td><td>boolean</td><td>Indicates operation status. If <code>true</code> - the product was added to the shopping cart.</td></tr><tr><td>itemsRemovedQuantity</td><td>number</td><td>Total quantity of products removed from the cart. </td></tr><tr><td>product</td><td>object <a href="get-cart-details.md#product">product</a></td><td><code>product</code> object after the operation.</td></tr><tr><td>cart</td><td>object <a href="get-cart-details.md#cart-callback-fields">cart</a></td><td><code>cart</code> object after the operation.</td></tr><tr><td>error</td><td>string</td><td>If <code>success</code> is <code>false</code>, contains error message.</td></tr></tbody></table>

### `Ecwid.Cart.removeProducts([])`&#x20;

This method works in the same way as Ecwid.Cart.removeProduct(), but allows you to remove multiple items from the cart at once. For example:

```javascript
Ecwid.Cart.removeProduct(0);
Ecwid.Cart.removeProduct(1);
```

and

```javascript
Ecwid.Cart.removeProducts([0,1]);
```

do the same thing - they remove the first two items from the cart.

This method also supports the same `callback` object.
