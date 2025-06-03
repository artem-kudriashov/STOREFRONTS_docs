# Overview

Ecwid offers many configuration settings to change the website's look and feel. You can apply these settings dynamically through the JavaScript code based on specific conditions or set them in the HTML code.

### Apply configuration with JavaScript code

With JavaScript code, you can apply configuration settings dynamically.&#x20;

It grants you more flexibility if you, for example, have several storefronts. However, you need to set up a custom application with a self-hosted JS file. Learn how to set up a JavaScript file in the [Quickstart guide](../get-started/quickstart-customize-storefront-with-ecwid-js-api.md).

Once set up, use the following code example to set up configuration settings:

```javascript
Ecwid.OnAPILoaded.add(function() {
    window.ec = window.ec || Object();
    window.ec.config = window.ec.config || Object();
    
    // configs
};
```

### Apply configuration with HTML code

To always apply configuration settings without any JS code, you need access to the website's HTML code.&#x20;

Search `https://app.ecwid.com/script.js` to find where Ecwid script is called in the code and add configuration settings inside a `<script>` block right below it.

Code example:

```html
<div id="my-store-STOREID"></div>
<div>
	<script 
          data-cfasync="false" 
          type="text/javascript" 
          src="https://app.ecwid.com/script.js?STOREID&data_platform=code" 
          charset="utf-8">
  </script>
  <script 
          type="text/javascript"> xProductBrowser("id=my-store-STOREID", "defaultCategoryId=CATEGORYID");
  </script>
</div>

<script>
          window.ec = window.ec || Object();
          window.ec.config = window.ec.config || Object();
          
          //configs
</script>
```
