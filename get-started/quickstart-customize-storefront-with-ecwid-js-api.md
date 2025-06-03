# Quickstart: customize storefront with Ecwid JS API

To start working on your storefront customization project, you need a self-hosted JavaScript file connected to an app in your Ecwid store.&#x20;

In the following guide, you'll start with a new JS file running on your server and end up with an app that runs your script file and initializes Ecwid JS API every time the storefront is opened by a customer.

### Step 1. Set up a custom application in your store

To make any code changes to the storefront, you need a custom app to be installed in your store. If you don't have a custom application yet, jump into the **Building apps** section.

[Set up a custom app](https://app.gitbook.com/s/uOzT5egoVTAjMJwRuMQT/get-started/set-up-your-dev-environment-in-ecwid)

### Step 2: Connect a self-hosted JS file with the app

To get started with the JS API, you'll need to set up a self-hosted JS file running on your server all the time. This file, for example `my_script.js`, will automatically load and run on the storefront every time it's opened.

To set it up, get a static HTTPS link to the file, for example `https://myserver.com/js/my_script.js`, and request an app update from the API Support team.

[Request application update](https://app.gitbook.com/s/uOzT5egoVTAjMJwRuMQT/contact-ecwid-api-support-team)

Once the app is updated, your script file automatically loads and runs on the storefront. If the app is installed in multiple Ecwid stores, the script runs in all of their storefronts.

### Step 3: Initialize Ecwid JS API in the file

Once you have the JS file running on the storefront, you'll need to **initialize Ecwid JS API** in it. This way, you can unlock the full potential of storefront customizations and make your code more simplified in a lot of cases.

To do so, simply start your code with the following function:

```javascript
Ecwid.OnAPILoaded.add(function() {
	console.log("Ecwid JS API is loaded.");
});
```

Now you can utilize all methods described below, along with the configuration settings. Learn all JS API features:

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Automate your code execution</strong></td><td><a href="broken-reference">Broken link</a></td></tr><tr><td><strong>Client-side access to store details</strong> </td><td><a href="broken-reference">Broken link</a></td></tr><tr><td><strong>Manage your customers</strong></td><td><a href="broken-reference">Broken link</a></td></tr><tr><td><strong>Work with checkout and cart</strong></td><td><a href="broken-reference">Broken link</a></td></tr><tr><td><strong>Redirect customers between pages</strong></td><td><a href="broken-reference">Broken link</a></td></tr><tr><td><strong>Change store behavior with configs</strong></td><td><a href="../store-configuration-settings/behavioral-configs.md">behavioral-configs.md</a></td></tr></tbody></table>

