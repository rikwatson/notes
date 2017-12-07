# HTML 5

 Also See:

 * JavaScript [Web workers](./javascript.webworkers.md)
 * [JavaScript](./javascript.js) (but really you should be looking at [TypeScript](./typescript.md))
 * [WebPack](https://www.sitepoint.com/bundle-static-site-webpack/)
 * Asm.js (or more likely webasm??? these days)
 * Web local storage etc
 * Progressive Web Apps [PWA](./html5.pwa.md)
 * [Background Sync](https://developers.google.com/web/updates/2015/12/background-sync) & [ponyfoo.com](https://ponyfoo.com/articles/backgroundsync)
 * [Form Validation](./html5.form-validation.md)
 * [Local Storage](./html5.localstorage.md)
 * The over-engineering of [ponyfoo.com](https://ponyfoo.com/articles/most-over-engineered-blog-ever)

# Progressive enhancement Background Sync example

It’ll be a while before all browsers support background sync, especially as Safari and Edge don’t yet support service workers. But progressive enhancement helps here:

```javascript
if ('serviceWorker' in navigator && 'SyncManager' in window) {
  navigator.serviceWorker.ready.then(function(reg) {
    return reg.sync.register('tag-name');
  }).catch(function() {
    // system was unable to register for a sync,
    // this could be an OS-level restriction
    postDataFromThePage();
  });
} else {
  // serviceworker/sync not supported
  postDataFromThePage();
}
```


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

## Webworkers

```html
<!DOCTYPE html>
<script id="worker1" type="javascript/worker">
    // This script won't be parsed by JS engines because its type is javascript/worker.
    self.onmessage = function(e) {
        self.postMessage('msg from worker');
    };
// Rest of your worker code goes here.
    </script>
<script>
    var blob = new Blob([
                         document.querySelector('#worker1').textContent
                         ], { type: "text/javascript" })
                         
                         // Note: window.webkitURL.createObjectURL() in Chrome 10+.
                         var worker = new Worker(window.URL.createObjectURL(blob));
                         worker.onmessage = function(e) {
                             console.log("Received: " + e.data);
                         }
worker.postMessage("hello"); // Start the worker.
    </script>
```