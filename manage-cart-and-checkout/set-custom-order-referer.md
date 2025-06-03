# Set custom order referer

This method allows you to dynamically declare the `ec.order.referer_id` variable through the JavaScript code to set the order referer.

Code example:

```javascript
ec.order = ec.order || {};
ec.order.referer_id = 'Amazon'
```

The field appears in exported order CSVs, invoices, email notifications, and REST API as `refererId` field.
