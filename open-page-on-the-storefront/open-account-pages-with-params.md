# Open account pages with params

Base JS calls:

```javascript
Ecwid.openPage('account');

Ecwid.openPage('account/subscription');sd
```

List of additional parameters for the `'account'` call:

* `'returnurl'` - Optional parameter for redirecting users to a specific URL after successful login.

Code example:

```javascript
Ecwid.openPage('account', {'returnurl': 'https://www.ecwid.com/demo/Surfboards-c20671017'});
```

List of additional parameters for the `'account/subscription'` call:

* `'id'` - Subscription ID used to redirect customers to a specific subscription page. Required parameter.

Code example:

```javascript
Ecwid.openPage('account/subscription', {'id': 1006502});
```
