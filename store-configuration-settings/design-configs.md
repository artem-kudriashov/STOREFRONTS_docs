# Design configs

You can change the storefront design with the configuration settings described below.&#x20;

Control page layouts for product, category, and checkout pages, and font settings and labels for texts across the storefront.

### How to apply design configuration with HTML code

Design config requires an additional `Ecwid.refreshConfig && Ecwid.refreshConfig();` line to apply the changes. [Behavioral configs](behavioral-configs.md) do not require it.

Code example:

```html
<script>
  window.ec = window.ec || Object();
  window.ec.storefront = window.ec.storefront || Object();
  
  // Add design config
  window.ec.storefront.CONFIG_NAME = VALUE;
  
  // Apply design configs
  Ecwid.refreshConfig && Ecwid.refreshConfig();
</script>
```

### General store design settings

<table><thead><tr><th>Config name</th><th width="115">Type</th><th>Description</th></tr></thead><tbody><tr><td>show_signin_link</td><td>boolean</td><td>Visibility of the sign in link for customers: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>show_breadcrumbs</td><td>boolean</td><td>Visibility of the breadcrumbs: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>breadcrumbs_have_home_item</td><td>boolean</td><td>Visibility of the home page link in breadcrumbs: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>breadcrumbs_home_url</td><td>string</td><td>Set the URL to the home link in breadcrumbs. Empty by default.</td></tr><tr><td>breadcrumbs_separator</td><td>string</td><td><p>Defines breadcrumbs separator. Available values: any string.</p><p>For example:<br><code>/</code> gets<code>Store / SubCategory / SubSubCategory</code><br><code>-></code> gets<code>Store -> SubCategory -> SubSubCategory</code></p></td></tr><tr><td>product_list_show_sort_viewas_options</td><td>boolean</td><td>Visibility of the 'View as' and 'Sort by' options for category pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>show_footer_menu</td><td>boolean</td><td>Visibility of the footer menu: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>show_sku</td><td>boolean</td><td>Visibility of the product SKUs in category and product pages (less priority than the <code>product_list_sku_behavior</code> config): set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>show_root_categories</td><td>boolean</td><td>Visibility of the category grid on the home page: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr></tbody></table>

### Category and search pages

<table><thead><tr><th>Config name</th><th width="110">Type</th><th>Description</th></tr></thead><tbody><tr><td>enable_catalog_on_one_page</td><td>boolean</td><td><p>Defines if the one-page catalog is enabled: set <code>true</code> to enable or <code>false</code> to disable it.<br></p><p>One-page catalog shows all categories on the home page.</p></td></tr><tr><td>hide_category_block_show_all_enabled_products</td><td>boolean</td><td>Allows to hide categories completely from the storefront and show all enabled products on one page instead.</td></tr><tr><td>enable_simple_category_list</td><td>boolean</td><td>Defines if all categories have the same number of cards in a row: set <code>true</code> to enable or <code>false</code> to disable it.</td></tr><tr><td>product_list_title_behavior</td><td>string</td><td>Defines display mode of product title: <code>"SHOW"</code>, <code>"HIDE"</code>, <code>"SHOW_ON_HOVER"</code>.</td></tr><tr><td>product_list_sku_behavior</td><td>string</td><td>Defines display mode of product SKU: <code>"SHOW"</code>, <code>"HIDE"</code>, <code>"SHOW_ON_HOVER"</code>.</td></tr><tr><td>product_list_price_behavior</td><td>string</td><td>Defines display mode of product price: <code>"SHOW"</code>, <code>"HIDE"</code>, <code>"SHOW_ON_HOVER"</code>.</td></tr><tr><td>product_list_subtitles_behavior</td><td>string</td><td>Defines display mode of product subtitle: <code>"SHOW"</code>, <code>"HIDE"</code>, <code>"SHOW_ON_HOVER"</code>.</td></tr><tr><td>product_list_buybutton_behavior</td><td>string</td><td>Defines display mode of the 'Buy now' button: <code>"SHOW"</code>, <code>"HIDE"</code>, <code>"SHOW_ON_HOVER"</code>.<br>The 'Buy now' button must first be enabled in the Ecwid admin > Settings > General > Cart > Show "Buy now" buttons.</td></tr><tr><td>product_list_show_frame</td><td>boolean</td><td>Visibility of the border for product cards: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_list_product_info_layout</td><td>string</td><td>Defines alignment for SKU, price, and name in product cards. Available values: <code>"CENTER"</code>, <code>"LEFT"</code>, <code>"JUSTIFY"</code>, <code>"RIGHT"</code>.</td></tr><tr><td>product_list_category_title_behavior</td><td>string</td><td>Defines how category names are displayed on category pages. Available values: <code>"SHOW_ON_IMAGE"</code> (default), <code>"SHOW_BELOW_IMAGE"</code>, <code>"HIDE"</code>, <code>"SHOW_ON_HOVER"</code>.</td></tr><tr><td>product_list_show_product_images</td><td>boolean</td><td>Visibility of the product images on category pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_filters_visible_on_catalog_pages</td><td>boolean</td><td>Visibility of the product filters section on category pages.</td></tr><tr><td>product_filters_position_on_catalog_pages</td><td>string</td><td>Defines alignment for product filters on category pages. Available values: <code>"left"</code> (default), <code>"right"</code>.</td></tr><tr><td>product_filters_position_search_page</td><td>string</td><td>Defines alignment for product filters on search pages. available values: <code>"left"</code> (default), <code>"right"</code>.</td></tr><tr><td>product_filters_opened_by_default_on_catalog_pages</td><td>boolean</td><td>Defines if the product filters section is opened by default on category pages.</td></tr><tr><td>product_filters_orientation</td><td>string</td><td>Defines how product filters are discplayed on the storefront. Available values: <code>VERTICAL</code> - product filters are displayed on the side, <code>HORIZONTAL</code> - product filters are displayed above the product list.</td></tr><tr><td>product_list_swatches_product_option_behavior</td><td>string</td><td>Visibility of swatches on category pages: <code>SHOW</code>, <code>HIDE</code>.</td></tr><tr><td>product_list_swatches_product_option_shape</td><td>string</td><td>Shape of product swatches on category page: <code>CIRCLE</code>, <code>SQUARE</code>, <code>ROUNDED_SQUARE</code> (default).</td></tr></tbody></table>

### Product pages

<table><thead><tr><th>Config name</th><th width="104">Type</th><th>Description</th></tr></thead><tbody><tr><td>product_details_layout</td><td>string</td><td>Defines layout for product pages. Available values: <code>"TWO_COLUMNS_SIDEBAR_ON_THE_LEFT"</code>, <code>"TWO_COLUMNS_SIDEBAR_ON_THE_RIGHT"</code>, <code>"THREE_COLUMNS_SIDEBAR_ON_THE_RIGHT"</code>, <code>"THREE_COLUMNS_SIDEBAR_ON_THE_LEFT"</code>.</td></tr><tr><td>product_details_show_breadcrumbs</td><td>boolean</td><td>Visibility of the breadcrumbs on product pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_product_name</td><td>boolean</td><td>Visibility of the product name: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_product_sku</td><td>boolean</td><td>Visibility of the product SKU: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_product_price</td><td>boolean</td><td>Visibility of the product price: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_sale_price</td><td>boolean</td><td>Visibility of the product sale price: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_price_per_unit</td><td>boolean</td><td>Visibility of the product price per unit: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_tax</td><td>boolean</td><td>Visibility of the product taxes: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_product_options</td><td>boolean</td><td>Visibility of the product options block: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_hide_price_modifiers</td><td>boolean</td><td>Visibility of the price modifiers for product options: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_buy_button</td><td>boolean</td><td>Visibility of the buy button on product pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_qty</td><td>boolean</td><td>Visibility of the "quantity" field on product pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_attributes</td><td>boolean</td><td>Visibility of the product attributes: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_weight</td><td>boolean</td><td>Visibility of the product weight: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_number_of_items_in_stock</td><td>boolean</td><td>Visibility of the items in stock on product pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_in_stock_label</td><td>boolean</td><td>Visibility of the 'In stock' label on product pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_wholesale_prices</td><td>boolean</td><td>Visibility of the wholesale prices: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_product_description</td><td>boolean</td><td>Visibility of the product description: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_save_for_later</td><td>boolean</td><td>Visibility of the 'Save for Later' block on product pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_share_buttons</td><td>boolean</td><td>Visibility of the share buttons block: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_facebook_share_button</td><td>boolean</td><td>Visibility of the Facebook share button: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_pinterest_share_button</td><td>boolean</td><td>Visibility of the Pinterest share button: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_twitter_share_button</td><td>boolean</td><td>Visibility of the Twitter share button: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_vk_share_button</td><td>boolean</td><td>Visibility of the VKontakte share button: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_image_carousel</td><td>boolean</td><td>Visibility of the gallery images: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_additional_images_has_shadow</td><td>boolean</td><td>Visibility of the shadow for gallery images: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_subtitle</td><td>boolean</td><td>Visibility of product subtitles: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_navigation_arrows</td><td>boolean</td><td>Visibility of image navigation arrows on product pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_show_product_photo_zoom</td><td>boolean</td><td>Defines availability of image hover zoom on product pages: set <code>true</code> to enable or <code>false</code> to disable.</td></tr><tr><td>product_details_show_product_name_always_first_on_mobile</td><td>boolean</td><td>Defines if the product name is always on top on mobile: set <code>true</code> to enable or <code>false</code> to disable.</td></tr><tr><td>product_details_cut_product_description_in_sidebar</td><td>boolean</td><td>Defines if the product description shows in the sidebar and displays only one paragraph with the "Show more"expand button: set <code>true</code> to enable or <code>false</code> to disable.</td></tr><tr><td>product_details_two_columns_with_right_sidebar_show_product_description_on_sidebar</td><td>boolean</td><td>Defines if the product description shows in the sidebar for two columns and right sidebar config: set <code>true</code> to enable or <code>false</code> to disable.</td></tr><tr><td>product_details_two_columns_with_left_sidebar_show_product_description_on_sidebar</td><td>boolean</td><td>Defines if the product description shows in the sidebar for two columns and left sidebar config: set <code>true</code> to enable or <code>false</code> to disable.</td></tr><tr><td>product_details_gallery_layout</td><td>string</td><td>Defines layout for image gallery on product pages. Available values: <code>IMAGE_SINGLE_THUMBNAILS_HORIZONTAL</code>, <code>IMAGE_SINGLE_THUMBNAILS_VERTICAL</code>,<code>IMAGE_FEED</code>.</td></tr><tr><td>product_details_additional_images_preview_on_click</td><td>boolean</td><td>Visibility of gallery images on fullscreen image preview: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>product_details_thumbnails_aspect_ratio</td><td>string</td><td>Defines image aspect ratio for gallery thumbnails. Available values: <code>"AUTO"</code>, <code>"PORTRAIT_0667"</code>, <code>"PORTRAIT_075"</code>, <code>"SQUARE_1"</code>, <code>"LANDSCAPE_1333"</code>, <code>"LANDSCAPE_15"</code>.</td></tr><tr><td>product_details_show_breadcrumbs_position</td><td>string</td><td>Defines the position of breadcrumbs on product pages. Available values: <code>PRODUCT_DETAILS_SIDEBAR</code>, <code>NAVIGATION_CONTAINER</code>.</td></tr><tr><td>product_details_show_image_alt_text_as_visible_description</td><td>boolean</td><td>Defines if image alt text shows under gallery images at the storefront. Available values: <code>true</code>, <code>false</code> (default).</td></tr><tr><td>product_details_swatches_product_option_size</td><td>string</td><td>Size of product swatches on the product page: <code>SMALL</code>, <code>MEDIUM</code>, <code>LARGE</code> (default).</td></tr><tr><td>product_details_swatches_product_option_shape</td><td>string</td><td>Shape of product swatches on the product page: <code>CIRCLE</code>, <code>SQUARE</code>, <code>ROUNDED_SQUARE</code> (default).</td></tr></tbody></table>

### Checkout pages

<table><thead><tr><th>Config name</th><th width="93">Type</th><th>Description</th></tr></thead><tbody><tr><td>shopping_cart_show_qty_inputs</td><td>boolean</td><td>Visibility of the "quantity" field on the checkout pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>shopping_cart_show_sku</td><td>boolean</td><td>Visibility of the item SKU on checkout pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>shopping_cart_show_weight</td><td>boolean</td><td>Visibility of the item weight on checkout pages: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>checkout_show_state_input</td><td>boolean</td><td>Visibility of the <code>state</code> field in checkout address forms: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>checkout_show_address_line_2</td><td>boolean</td><td>Visibility of the <code>address_line_2</code> field in checkout address forms: set <code>true</code> to show the element or <code>false</code> to hide it.</td></tr><tr><td>shopping_cart_products_collapsed_on_desktop</td><td>boolean</td><td>Defines if the list of products is auto-collapsed on desktop cart pages if the cart has more than 4 products: set <code>true</code> to enable (default) or <code>false</code> to disable.</td></tr><tr><td>shopping_cart_products_collapsed_on_mobile</td><td>boolean</td><td>Defines if the list of products is auto-collapsed on mobile cart pages: set <code>true</code> to enable (default) or <code>false</code> to disable.</td></tr><tr><td>checkout_expand_billing_address_form</td><td>boolean</td><td>Defines if the billing address form is auto-expanded on the checkout: set <code>true</code> to enable or <code>false</code> to disable (default).</td></tr></tbody></table>

### Fonts and colors

Ecwid has an additional `chameleon` config allowing you to change store colors, font parameters, and label texts. It can also be used to automatically set storefront font and color settings matching the ones you use on your website where Ecwid store is integrated.

Set storefront fonts and colors automatically:

```html
<script>
	window.ec = window.ec || Object();
	window.ec.config = window.ec.config || Object();
	window.ec.config.chameleon = window.ec.config.chameleon || Object();
	window.ec.config.chameleon.font = 'auto';
	window.ec.config.chameleon.colors = 'auto';
	Ecwid.refreshConfig && Ecwid.refreshConfig();
</script>
```

Set storefront fonts and colors manually:

```html
<script>
	window.ec = window.ec || Object();
	window.ec.config = window.ec.config || Object();
	window.ec.config.chameleon = window.ec.config.chameleon || Object();
	window.ec.config.chameleon.colors = {
		'color-background':'#D3D3D3',
		'color-foreground':'#4EA3F0',
		'color-link':'#FF0606',
		'color-button':'#4EA3F0',
		'color-price':'#FF0606'
	}
	window.ec.config.chameleon.font = {
		'font-family':'arial,sans-serif'
	}
	Ecwid.refreshConfig && Ecwid.refreshConfig();
</script>
```

The `chameleon.colors` config allows you to set the following settings:

| Name                       | Type                        | Description                                                                                                            |
| -------------------------- | --------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| color-background           | string (HEX and RGBA color) | Background color for storefront and small buttons ("Clear bag", "Apply", etc.).                                        |
| color-foreground           | string (HEX and RGBA color) | Color of all texts.                                                                                                    |
| color-link                 | string (HEX and RGBA color) | Color for all links (breadcrumbs, "Sign In", "Favourites", etc.).                                                      |
| color-button               | string (HEX and RGBA color) | Color for main buttons ("Add to bag", "Checkout", etc.) and small buttons on mouse hover ("Clear bag", "Apply", etc.). |
| color-price                | string (HEX and RGBA color) | Color for product prices.                                                                                              |
| gallery.use\_exact\_colors | boolean                     | If `true`, background color for gallery images will match `color-foreground` setting. Default value is `false`.        |

### Storefront labels

Most storefront texts have an internal "label" assigned to them. You can use this label to change the wording in your store.

Use an integrated free tool for searching and changing text labels without coding – [Storefront Label Editor](https://www.ecwid.com/apps/tools/storefront-label-editor). Once you find a label with the app, you can apply text changes within the app or with your JavaScript/HTML code. The code aproach is recommended if you want to have a store on several websites and change wordings on these websites independently.

Code example:

```html
<script type="text/javascript">
  ecwidMessages = {
    "BreadCrumbs.your_bag": "Your shopping cart",
    "Minicart.shopping_bag": "Shopping Cart",
    "ShoppingCartView.shopping_bag": "Your Shopping Cart",
    "EmptyShoppingCartPanel.empty": "Your Shopping Cart is empty"
  };
</script>
```
