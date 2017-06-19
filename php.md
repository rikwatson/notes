# PHP

A'ka `Personal Home Page`, now `PHP: Hypertext Preprocessor`, still awful.

Use by [Heroku](./heroku).

Apparently the most popular programming language of the web. Effectivly a [HTML](./html) Pre-processor.

Comic from [www.commitstrip.com](http://www.commitstrip.com/en/2015/11/13/the-last-ever-line-of-code/)

![](./php.jpg)

# Links

 * [REPL](https://repl.it/languages/php)

```php

$cars=array
  (
    "Volvo"=>array
    (
      "XC60",
      "XC90"
    ),
      "BMW"=>array
    (
      "X3",
      "X5"
    ),
      "Toyota"=>array
    (
      "Highlander"
    )
  ); 

echo "Normal count: " . count($cars), PHP_EOL;
echo "Recursive count: " . count($cars,1), PHP_EOL;


echo "-----------", PHP_EOL;

$item = "blah blah <im:rating>1</im:rating> blah blah";

preg_match_all("/<im:rating>([0-5])<\/im:rating>/um", $item, $rating);

echo $item , PHP_EOL;

echo "ratins is:" . $rating . " with a count of " . count($rating) , PHP_EOL;

echo "print_r gives -", PHP_EOL;

var_dump ($rating);

echo "------", PHP_EOL;

	foreach ($rating[1] as $element){
		echo ".. " . $element , PHP_EOL;
	}
	unset ($element);
	
	
echo $rating[1][0] , PHP_EOL;

$num = "5";
echo $num, PHP_EOL;

echo "is_numeric:" . is_numeric($num), PHP_EOL;
```
