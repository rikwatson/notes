# Dynamically Changing favicon


This would be nice to do for a RAG widget.

 * http://stackoverflow.com/questions/260857/changing-website-favicon-dynamically
 * http://stackoverflow.com/questions/6964144/dynamically-generated-favicon
 * https://gist.github.com/mathiasbynens/428626
 * https://mathiasbynens.be/demo/dynamic-favicons


[gist 428626](https://gist.github.com/mathiasbynens/428626)

```javascript
/*!
 * Dynamically changing favicons with JavaScript
 * Works in all A-grade browsers except Safari and Internet Explorer
 * Demo: http://mathiasbynens.be/demo/dynamic-favicons
 */

// HTML5™, baby! http://mathiasbynens.be/notes/document-head
document.head || (document.head = document.getElementsByTagName('head')[0]);

function changeFavicon(src) {
 var link = document.createElement('link'),
     oldLink = document.getElementById('dynamic-favicon');
 link.id = 'dynamic-favicon';
 link.rel = 'shortcut icon';
 link.href = src;
 if (oldLink) {
  document.head.removeChild(oldLink);
 }
 document.head.appendChild(link);
}
```

or

[gist 2c09ff0081c43691a40d4a96233809a5](https://gist.github.com/rikwatson/2c09ff0081c43691a40d4a96233809a5)

```html
<!doctype html>
<html>
 <head>
  <meta charset="utf-8">
  <title>Dynamically changing favicons with JavaScript</title>
 </head>
 <body>
  <h1>Dynamically changing favicons with JavaScript</h1>
  <button>Click to change favicon</button>
  <p>See <a href="http://gist.github.com/428626">gist 428626</a>. Works in Firefox, Opera, and Chrome. Fails in Safari and Internet Explorer. — <a href="/" title="Mathias Bynens, front-end web developer">Mathias</a></p>
  <script>

   // HTML5, baby! https://mathiasbynens.be/notes/document-head
   document.head || (document.head = document.getElementsByTagName('head')[0])

   function changeFavicon(src) {
    var link = document.createElement('link'),
        oldLink = document.getElementById('dynamic-favicon')
    link.id = 'dynamic-favicon'
    link.rel = 'icon'
    link.href = src
    if (oldLink) {
     document.head.removeChild(oldLink)
    }
    document.head.appendChild(link)
   }

   // Example: https://mathiasbynens.be/demo/dynamic-favicons
   var btn = document.getElementsByTagName('button')[0]
   btn.onclick = function() {
    changeFavicon('http://www.google.com/favicon.ico')
   }
  </script>
 </body>
</html>
```
