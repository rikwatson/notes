# Webworker in JavaScript

 * [Web workers without a separate Javascript file?](https://stackoverflow.com/questions/5408406/web-workers-without-a-separate-javascript-file)
 * PonyFoo [ServiceWorker: A Basic Guide to BackgroundSync](https://ponyfoo.com/articles/backgroundsync)

## Full example of BLOB inline worker:

Works in Chrome and Safari - not sure about iOS. - yes (Via http://caniuse.com/)

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

