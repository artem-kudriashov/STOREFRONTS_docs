# "Instant Site section load" events

[Instant Site](https://support.ecwid.com/hc/en-us/articles/207100069-What-is-Instant-Site) is a website builder created by Ecwid. Every page is built from blocks called sections (also referred to as **tiles**).

These blocks improve overall website loading speed by loading and unloading dynamically depending on the viewport (what a user currently sees).

### `window.instantsite.onTileLoaded`

This method allows you to track when a specific tile becomes **loaded** (visible to the user) and calls your JavaScript code inside.

Code example:

```javascript
document.addEventListener("DOMContentLoaded", function() {
	window.instantsite.onTileLoaded.add(function (tile) {
		// your code here
		if (tile === 'tile-id') {
			document.getElementById("tile-id").innerHTML = '<iframe src=""></iframe>'; //add custom iframe
		}
	});
});
```

### `window.instantsite.onTileUnloaded`

This method allows you to track when a specific tile becomes **unloaded** (out of user's monitor) and calls your JavaScript code inside.

Code example:

```javascript
document.addEventListener("DOMContentLoaded", function() {
	window.instantsite.onTileUnloaded.add(function (tile) {
		// your code here
		if (tile === 'tile-id') {
			document.getElementById("tile-id").innerHTML = ''; //remove Custom iframe
		}
	});
});
```
