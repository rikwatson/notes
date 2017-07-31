# HTML

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