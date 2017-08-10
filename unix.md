# Unix

 * Unix [File Processing](./unix.file_processing.md)
 * Unix [Tools](./unix.tools.md)
 * Unix [Bash](./unix.bash.md)


### Change file extension on multiple files

```bash
for f in *.markdown; do mv -- "$f" "${f%.markdown}.md"; done
```

## bash

### Standard Header

```bash
#!/bin/bash -l
#
```

### Remove JSON comments

See [JSON](./json.md)

### One line simple Web server (In Python)

```bash
python -m SimpleHTTPServer 8000
```

### Search current folder

```bash
export PATH=$PATH:.
```

And add to `~/.bashrc`

### How to check `bash` exit status

```bash
doSomeCommand

if [ $? -eq 0 ]
then
	echo "Success"
else
	echo "Failure"
fi
```

## What's my (external) IP address ?

```bash
curl -s -H 'Accept: application/json' ipinfo.io \
      | fgrep  '"ip":'                          \
       | tr -dc '[0-9].'
```
----

### File name extraction

```bash
filename=$(basename "$fullfile")
extension="${filename##*.}"
filename="${filename%.*}"
```


### Run in same directory

```bash
#! /bin/bash
#
cd $(dirname "$0")
```

But this won't work if there are spaces in the directory spec.
