# Heroku

## Hosting Static HTML Pages

Just create a `index.php` (or `whatever.php`) and add the following:

```
<?php include_once("whatever.html"); ?>
```

## TODO

 * Understand the basics
 * Move rikwatson.com over (mainly static).
 * Swift playgrounds
 * Custom [domain][domain] via DNS. 
 * Move rikwatson.com to heroku.com (Via [Casey Liss][casey]).
 * Look at [camel][camel] Casey's blogging engine.

## Apps

### rikwatson

			App URL: http://rikwatson.herokuapp.com/
			Git URL: git@heroku.com:rikwatson.git
			
Use the following code to set up your app for local development:

			git clone git@heroku.com:rikwatson.git -o heroku


## URLs

 * Heroku [Dashboard][dashboard]
 * https://dashboard.heroku.com/apps?www-home-top
 * https://toolbelt.heroku.com/
 * https://devcenter.heroku.com/
 * https://devcenter.heroku.com/articles/getting-started-with-nodejs
   +     username: rik.watson@omega-point.com  
   +     password: In `1password`


[casey]: http://www.caseyliss.com/2014/5/1/heroku-first-impressions
[camel]: https://github.com/cliss/camel
[domain]: https://devcenter.heroku.com/articles/custom-domains
[dashboard]: https://dashboard.heroku.com/apps/rikwatson/settings