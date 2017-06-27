# JavaScript: The 'J' in AJAX

Cf. [TypeScript](./typescript.md) & [ES2015](http://babeljs.io/learn-es2015/)

 * [Snippets](http://www.webcodr.com/6/15-javascript-snippets-you-cant-live-without/) 15 Snippets you can't live without
 * [SOAP](http://www.guru4.net/articoli/javascript-soap-client/demo/en.aspx) Demo of using SOAP with JS
 * [Images](http://www.cryer.co.uk/resources/javascript/script3.htm) How to control the load order


# Frameworks

 * [SproutCore](http://www.sproutcore.com/demos/)
 * [JQuery](http://stanlemon.net/projects/jquery-templates.html) Using the template


# JScript - WSH

 * [Win32 Scripting](http://cwashington.netreach.net/main/default.asp?topic=links)
 * [Winscripter](http://www.winscripter.com/)
 * [VBscript & JScript](http://articles.techrepublic.com.com/5100-10878_11-1056451.html)


# Better documentation via Markdown

* [jodoc](http://davebalmer.wordpress.com/2011/03/29/source-code-documentation-javadoc-vs-markdown/)
* [selfdocjs](http://joelhughes.co.uk/selfdocjs-javascript-that-documents-itself)

# Dropbox access:

* [dropbox JS](http://code.google.com/p/dropbox-js/) See ./resouces/dropbox.js &
 [here](http://dropbox-js.googlecode.com/svn-history/r7/trunk/dropbox.js).

# Twitter

* [jsgoodies](https://twitter.com/#!/jsgoodies)

# Module Loading etc

*[RequireJS](http://requirejs.org/docs/api.html)

# Books

## JavaScript: The Good Parts, by Douglas Crockford

It took me more than one try to get through this not-very-thick book, and it is not gospel. However, it is mandatory reading for any serious JavaScript developer.

## Eloquent JavaScript, Marijn Haverbeke

This is another [book](http://eloquentjavascript.net/) that I consider mandatory; you may not read straight through it, but you should have it close at hand. I like it so much that I actually bought the print version, and then was lucky enough to get a signed copy from Marijn at JSConf 2011.

## JavaScript Patterns, by Stoyan Stefanov

This was the book that showed me there were names for so many patterns that Iíd discovered purely through fumbling around with my own code. I read it on the flight to the 2010 Boston jQuery Conference, and itís definitely the kind of book that I wouldnít have gotten as much out of a year earlier, when I had a lot less experience with the kinds of problems it addresses.

## Object-Oriented JavaScript, by Stoyan Stefanov

It's been ages since I read this book, and so I confess that I donít have a strong recollection of it, but it was probably the first book I read that got me thinking about structuring JavaScript code beyond the ìget some elements, do something with themî paradigm of jQuery.


# PhoneGap

* [Creating Tab Bar](http://phoniphone.wordpress.com/2010/05/09/create-the-tabbar/)
* [1St App](http://phoniphone.wordpress.com/2010/11/03/first-phonegap-app-available-on-app-store/), [Lottery App](http://phoniphone.wordpress.com/2011/06/07/new-html5-app-available-on-app-store/) in App store.
* [Custom background colour](http://phoniphone.wordpress.com/2010/05/28/custom-background-color/)
* iOS style [CSS Animations](http://albertogasparin.it/articles/2011/06/ios-css-animations-performances/)
* Native Apps in JS in [iOS](http://matt.might.net/articles/how-to-native-iphone-ipad-apps-in-javascript/)
* [UIControls](http://nachbaur.com/blog/phonegap-uicontrols-ready-to-go) in PhoneGap

# Literal Programming

* [selfDoc.js](http://joelhughes.co.uk/selfdocjs-javascript-that-documents-itself)
* [Javaoc .v. Markdown](http://davebalmer.wordpress.com/2011/03/29/source-code-documentation-javadoc-vs-markdown/)

# Resources

* [JavaScript Weekly](http://javascriptweekly.com)
* [WebView JS Bridge](https://github.com/marcuswestin/WebViewJavascriptBridge#readme)
* [Understanding `this`](http://javascriptweblog.wordpress.com/2010/08/30/understanding-javascripts-this/)
* [Web Workes tutorial](http://www.cach.me/blog/2011/01/javascript-web-workers-tutorial-parse-wiki-text-in-real-time/)
* [`apply` keyword](http://www.devguru.com/technologies/ecmascript/quickref/apply.html) & [here](http://odetocode.com/blogs/scott/archive/2007/07/05/function-apply-and-function-call-in-javascript.aspx)
* [Closures explained](http://skilldrick.co.uk/2011/04/closures-explained-with-javascript/)

# JavaScript Error Logging

## Completed

* Test the likes of <br/> &nbsp; etc.
* Log every 10 second via timer (See log.js, also diag.js)

# TODO

* Then move this code into K12. Via LOG. 

## GAE

Look at logs [here](https://appengine.google.com) also [GAE](./gae.md).

## log4javascript

[Home Page](http://log4javascript.org/)

Use the Async XHR wrapper & log to GAE

The [AjaxAppender](http://log4javascript.org/docs/manual.html#ajaxappender)

An Ajax [example](http://log4javascript.org/demos/ajax.html).

[StackOverflow](http://stackoverflow.com/questions/2825640/log-client-side-errors-to-the-server) example.

# Toggle Visibility - Show/Hide Anything

One piece of javascript code that I use very frequently is a function that basically toggles the visibility of an element e.g. click, show, click, hide.

```html
<script type="text/javascript">
<!--
    function toggle_visibility(id) {
           var e = document.getElementById(id);
           if(e.style.display == 'block')
              e.style.display = 'none'
           else
              e.style.display = 'block'
        }
//-->
</script>
```

Simply paste the above snippet of code underneath your <body> tag and you call it by passing to it the ID of the element you wish to toggle the visibility of (this element can be anything that takes an id attribute). For example

```html
<a href="#" onclick="toggle_visibility('foo');">Click here to toggle visibility of element #foo</a>
<div id="foo">This is foo</div>
```
