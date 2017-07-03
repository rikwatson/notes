# Python

Even has [it's own](http://taoofmac.com/space/dev/Python/Grimoire) [grimoire](./words.md)

 * V2.7 or V3
 * [Installing](./python.macos.md) etc on a Mac.
 * [Pip](./python.pip.md), virtualenv and all that.
 * Working with [macOS](./python.macos.md)
 * Manipulating [Excel](./python.excel.md)
 * Serverless with [Chalice](./python.chalice.md)
 * [The Hitchhiker’s Guide to Python!](http://docs.python-guide.org/en/latest/)



## Top-level script environment, `__main__` etc

```python
def main():
	doSomething()

if __name__ == "__main__":
    main()
```

## Embedding in iOS

 * [Python Apple Support](https://github.com/pybee/Python-Apple-support)
 * [](https://pybee.org/project/using/ios-app/)

## Split a list

```python
L = [1,2,3,4,5,6,7,8]
C = 3
print [L:[i:i+C] for i in range(0, len(L), C)]
```

## How to flatten a tuple

```python
# Basically the problem was that I wanted to create a flat tuple from a tuple and a single value like such:
#
val = 3
tup = ( 'a', 3.14, "zzz" )

# I wanted this:
#
# ( 3, 'a', 3.14, "zzz" )
#
# not this: 
#
# ( 3, ( 'a', 3.14, "zzz" ) )


print (val,) + tup
```

## Python Image / Thumbnail Resize

See: http://www.pythonware.com/products/pil/index.htm

```python
import os, sys
import Image

size = 128, 128

for infile in sys.argv[1:]:
	outfile = os.path.splitext(infile)[0] + ".thumbnail"
	if infile != outfile:
		try:
			im = Image.open(infile)
			im.thumbnail(size)
			im.save(outfile, "JPEG")
		except IOError:
			print "cannot create thumbnail for", infile
```

## Basic XML DOM parsing

```python
from xml.dom.minidom import parse

dom = parse("foo.xml") # or dom = parseString( "<myxml>Some data <empty/> some more data</myxml>" )

for node in dom.getElementsByTagName('bar'):  # visit every node <bar />
    print node.toxml()
```

# Common code for V2 7 v3

For example

```python
if sys.version_info[0] == 3:
    # Python 3 imports.
    from urllib.parse import urlparse, parse_qs
else:
    # Python 2 imports.
    from urlparse import urlparse, parse_qs
```