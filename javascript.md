# JavaScript: The 'J' in AJAX

_Cf._

 * [TypeScript](./typescript.md) & [ES2015](http://babeljs.io/learn-es2015/)
 * [I18N](./javascript.i18n.md)

 * [Snippets](http://www.webcodr.com/6/15-javascript-snippets-you-cant-live-without/) 15 Snippets you can't live without
 * [SOAP](http://www.guru4.net/articoli/javascript-soap-client/demo/en.aspx) Demo of using SOAP with JS
 * [Images](http://www.cryer.co.uk/resources/javascript/script3.htm) How to control the load order
 * [JWT](./json.jwt.md)

 * A JS Build [setup](http://marijnhaverbeke.nl/blog/my-babel-setup.html), rather clever with a FUSE compiling file system.

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

# Modules / IIFE

From [here](https://ponyfoo.com/books/mastering-modular-javascript/chapters/1#read).

```javascript
void function() {
  window.mathlib = window.mathlib || {}
  window.mathlib.sum = sum

  function sum(...values) {
    return values.reduce((a, b) => a + b, 0)
  }
}()

mathlib.sum(1, 2, 3)
// <- 6
```

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


## Shorthand

###  Null, Undefined, Empty Checks Shorthand

When creating new variables sometimes you want to check if the variable you’re referencing for it’s value isn’t null or undefined. I would say this is a very common check for JavaScript coders.

Longhand
```javascript
if (variable1 !== null || variable1 !== undefined || variable1 !== '') { let variable2 = variable1; }
```

Shorthand

```javascript
let variable2 = variable1  || '';
```

Don’t believe me? Test it yourself (paste into Chrome Dev Tools and click run):

```javascript
//null value example
let variable1 = null;
let variable2 = variable1  || '';
console.log(variable2);
//output: '' (an empty string)

//undefined value example
let variable1 = undefined;
let variable2 = variable1  || '';
console.log(variable2);
//output: '' (an empty string)

//normal value example
let variable1 = 'hi there';
let variable2 = variable1  || '';
console.log(variable2);
//output: 'hi there'
```

2. Object Array Notation Shorthand

Longhand

```javascript
let a = new Array(); a[0] = "myString1"; a[1] = "myString2"; a[2] = "myString3";
```

Shorthand

```javascript
let a = ["myString1", "myString2", "myString3"];
```

3. If true … else Shorthand
This is a great code saver for when you want to do something if the test is true, else do something else by using the ternary operator.

Longhand:

```javascript
let big;
if (x > 10) {
    big = true;
}
else {
    big = false;
}
```

Shorthand:

```javascript
let big = x > 10 ? true : false;
```

If you rely on some of the weak typing characteristics of JavaScript, this can also achieve more concise code. For example, you could reduce the preceding code fragment to this:

```javascript
let big = (x > 10);
//further nested examples
let x = 3,
big = (x > 10) ? "greater 10" : (x < 5) ? "less 5" : "between 5 and 10";
console.log(big); //"less 5"
let x = 20,
big = {true: x>10, false : x< =10};
console.log(big); //"Object {true=true, false=false}"
```

### Declaring variables Shorthand
I think this one is the most used abroad the community, even though we know that javascript uses hoist to your variable declaration. It’s a nice pattern declare all the variables at the top and inline.

Longhand:

```javascript
let x;
let y;
let z = 3;
```

Shorthand:

```javascript
let x, y, z=3;
```

### Assignment Operators Shorthand

Assignment operators are used to assign values to JavaScript variables and no doubt you use arithmetic everyday without thinking (no matter what programming language you use Java, PHP, C++ it’s essentially the same principle).

Longhand:

```javascript
x=x+1;
minusCount = minusCount - 1;
y=y*10;
```

Shorthand:

```javascript
x++;
minusCount --;
y*=10;
```

Other shorthand operators, given that x=10 and y=5, the table below explains the assignment operators:

```javascript
x += y //result x=15
x -= y //result x=5
x *= y //result x=50
x /= y //result x=2
x %= y //result x=0
```

### RegExp Object Shorthand

Example to avoid using the RegExp object.

Longhand:

```javascript
var re = new RegExp("\d+(.)+\d+","igm"),
result = re.exec("padding 01234 text text 56789 padding");
console.log(result); //"01234 text text 56789"
```

Shorthand:

```javascript
var result = /d+(.)+d+/igm.exec("padding 01234 text text 56789 padding");
console.log(result); //"01234 text text 56789"
```

### If Presence Shorthand

This might be trivial, but worth a mention. When doing “if checks” assignment operators can sometimes be ommited.

Longhand:

```javascript
if (likeJavaScript === true)
```

Shorthand:

```javascript
if (likeJavaScript)
```

Here is another example. If “c” is NOT equal to true, then do something.

Longhand:

```javascript
let c;
if ( c!= true ) {
// do something...
}
```

Shorthand:

```javascript
let c;
if ( !c ) {
// do something...
}
```

### Function Variable Arguments Shorthand

Object literal shorthand can take a little getting used to, but seasoned developers usually prefer it over a series of nested functions and variables. You can argue which technique is shorter, but I enjoy using object literal notation as a clean substitute to functions as constructors.

Longhand:

```javascript
function myFunction( myString, myNumber, myObject, myArray, myBoolean ) {
    // do something...
}
myFunction( "String", 1, [], {}, true );
```

Shorthand (looks long but only because I have console.log’s in there!):

```javascript
function myFunction() {
    console.log( arguments.length ); // Returns 5
    for ( i = 0; i < arguments.length; i++ ) {
        console.log( typeof arguments[i] ); // Returns string, number, object, object, boolean
    }
}
myFunction( "String", 1, [], {}, true );
```

### charAt() Shorthand
You can use the eval() function to do this but this bracket notation shorthand technique is much cleaner than an evaluation, and you will win the praise of colleagues who once scoffed at your amateur coding abilities!

Longhand:

```javascript
"myString".charAt(0);
```

Shorthand:

```javascript
"myString"[0]; // Returns 'm'
```

### Short function calling

Just like #1 you can use ternary operators to make function calling shorthand based on a conditional.

Longhand:

```javascript
function x() {console.log('x')};function y() {console.log('y')};
let z = 3;
if (z == 3) 
{
    x();
} else {
    y();
}
```

Shorthand:

```javascript
function x() {console.log('x')};function y() {console.log('y')};let z = 3;
(z==3?x:y)(); // Short version!
```

### Decimal base exponents

You may have seen this one around it’s essentially a fancy way to write without the zeros. 1e7 essentially means 1 followed by 7 zeros — it represents a decimal base (JS interprets as a float type) equal to 10,000,000.

Longhand:

```javascript
for (let i = 0; i < 10000; i++) {
```

Shorthand:

```javascript
for (let i = 0; i < 1e4; i++) {
```