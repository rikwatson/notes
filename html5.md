# HTML 5

 Also See:

 * JavaScript [Webworkkers](./javascript.webworkers.md)
 * JavaScript (but really you should be looking at TypeScript)
 * WebPack
 * Asm.js (or more likely webasm??? these days)
 * Web local storage etc
 * Web Worker

## Canonical Links

Avoid split brain, also [non-trivial](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html):

```html
<link rel=”canonical” href=”http://themindfulbit.com/blog/noble-absence">
```

## Auto Refresh

Delay is in seconds, zero is valid.

So, this is once a day.

```html
<meta http-equiv="refresh" content="3600">
```

## Compatability

Check via [caniuse.com](http://caniuse.com/)

# Local Storage

Note: Session storage is also available (`sessionStorage`)

```javascript
if (typeof(Storage) !== "undefined") {
    // Code for localStorage/sessionStorage.
} else {
    // Sorry! No Web Storage support..
}
```

Key value pairs, always strings at least 5Gb storage.


```javascript
// Store
localStorage.setItem("lastname", "Smith");
// Retrieve
document.getElementById("result").innerHTML = localStorage.getItem("lastname");
```

Equivalent

```javascript
// Store
localStorage.lastname = "Smith";
// Retrieve
document.getElementById("result").innerHTML = localStorage.lastname;
```

Delete via:

``` javascript
localStorage.removeItem("lastname");
```