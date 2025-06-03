# Get visitor location

### `Ecwid.getVisitorLocation()`

This method gets the visitor's location based on their shipping or billing address (when entered), or IP. The call works even for signed-out customers.

Request example:

```javascript
console.log(
    JSON.stringify(
        Ecwid.getVisitorLocation()
    )
);

// prints
// 
// "{countryCode: 'US', stateCode: 'NE', source: 'SHIPPING_ADDRESS'}"
```

Fields available in the response:

| Name        | Type   | Description                                                                                                                                                                                |
| ----------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| countryCode | string | Country code (`null` if not found) in ISO 639-1.                                                                                                                                           |
| stateCode   | string | State code (`null` if not found) in ISO 639-1.                                                                                                                                             |
| source      | string | <p>The source of the received country code and state code. </p><p></p><p>One of: </p><p><code>SHIPPING_ADDRESS</code></p><p><code>BILLING_ADDRESS</code></p><p><code>IP_ADDRESS</code></p> |
