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

## Compatability

Check via [caniuse.com](http://caniuse.com/#search=localstorage)