# Behavioral configs

Some store configuration settings allow you to change how Ecwid works on the website. These settings are useful when you integrate Ecwid storefront to a custom-built website.

### Redirect after purchase

Use this config to redirect customers to a custom URL instead of the default "Thank you for purchase" page after a successful online payment.

{% hint style="info" %}
Ecwid doesn't have any control over the custom pages. You need to build the page for this custom URL.
{% endhint %}

Code example:

```javascript
window.ec = window.ec || Object();
window.ec.config = window.ec.config || Object();

window.ec.config.custom_redirect_after_purchase = 'https://mycoolstore.com/thank-you.html';
```

This method only works for online payment methods. If an order is paid with an offline payment method, customers won't be redirected to a specified URL.

### Custom scroll behavior

This method allows you to set up a custom scroll position, disable auto-scroll, and create custom scroll behavior on your website. Check out the code examples below.

Set up a custom scroll position in px from page top:

```javascript
window.ec = window.ec || Object();
window.ec.config = window.ec.config || Object();

window.ec.config.scroll_indent = 150; 
```

Disable auto-scroll on the page:

```javascript
window.ec = window.ec || Object();
window.ec.config = window.ec.config || Object();

window.history.scrollRestoration = 'auto';
window.ec.config.navigation_scrolling = "DISABLED";
```

Apply custom scroll behavior:

```javascript
window.ec = window.ec || Object();
window.ec.config = window.ec.config || Object();

window.ec.config.navigation_scrolling = "CUSTOM";
window.ec.config.custom_scroller = function() { 
	window.scrollTo(500, 0); //scroll to 500px from top
};
```

### Set main store URL for widgets

Similarly to `Ecwid.setStorefrontBaseUrl()`, allows specifying a base store URL. Learn more about [setting up base URL dynamically](https://app.gitbook.com/s/G9n5VxMY9T0Ob3D56PSD/rest-api/storefront-widget-details/set-base-url-for-storefront-widgets).&#x20;

This method is useful when you have a custom website with Ecwid storefront widgets on different pages. By default, these pages have independent carts, which is not convenient for customers.&#x20;

Set one base URL for Ecwid widgets across all "secondary" pages on your website. As a result, all widgets will point to the checkout on the main store page.

Code example:

```javascript
window.ec = window.ec || Object();
window.ec.config = window.ec.config || Object();
window.ec.config.store_main_page_url = "http://www.example.com/store.html";
```

Use case examples:

* Create a one /store page and several pages showcasing specific products.
* Integrate different categories from your store onto different website pages.

### Set storefront language for search engine crawlers

Ecwid allows several translations for the same page, which helps with creating multilanguage websites.

However, search engines could get distracted by similar-looking pages. To help them index your website better, use our configs for automatic generation of the `hreflang` meta tags.

Force auto-generation of meta tags for the storefront by adding the`enableHreflangTags` and `internationalPages` configs.

* `enableHreflangTags` enables generation of the `hreflang` meta tag.
* `internationalPages` sets URLs for storefront translations. Google Search Engine [recommendations](https://developers.google.com/search/docs/specialty/international/localized-versions?hl=en\&visit_id=638478132411236535-1380254665\&rd=1#language-codes) on 'locale' values.

Config example:

```javascript
window.ec = window.ec || Object();
window.ec.config = window.ec.config || Object();
ec.config.storefrontUrls.enableHreflangTags = true;
ec.config.storefrontUrls.internationalPages = {
  "en": "https://site.com/store",
  "fr": "https://fr.site.com/store",
  "es-mx": "https://mx.site.com/store",
  "default": "https://site.com/store"
}
```
