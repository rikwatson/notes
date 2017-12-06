 # Unix Bash

 * [Unix](./unix.md), in general
 * Unix [File Processing](./unix.file_processing.md)
 * Unix [Tools](./unix.tools.md)

 * [The Art of the Command Line](https://github.com/jlevy/the-art-of-command-line)
 * [Tips](http://www.doknowevil.net/2010/10/23/tips-for-using-bash-in-the-linux-terminal-part-1/)

## Standard shebang

```bash
#!/usr/bin/env bash
```

## Update Bash profile

```bash
echo 'export PATH="/some/path:$PATH"' >> ~/.bash_profile
```

## Run `bash` script in the directory it is in

```bash
#! /bin/bash
#
cd $(dirname "$0")
```

## Extract filename etc

```bash
filename=$(basename "$fullfile")
extension="${filename##*.}"
filename="${filename%.*}"
```

## Alias's

```bash
# Q: Why isn't alias working ?
# A: Because  don't work in non interactive mode.
#
#
shopt -s expand_aliases
alias chrome="/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome"
alias chrome-canary="/Applications/Google\ Chrome\ Canary.app/Contents/MacOS/Google\ Chrome\ Canary"
alias chromium="/Applications/Chromium.app/Contents/MacOS/Chromium"
```

## Adding help

```bash
#
# captureScreenshots
#
usage() {
    cat <<EOM
    Usage:
    $(basename $0)  URL filename-without-extension

EOM
    exit 0
}


if [[ ( $@ == "--help") ||  $@ == "-h" ||  $@ == "-?" ]];
then
  usage;
  exit 0
fi
```



## Defaulting parameters

```bash
url=${1-https://ontaap.herokuapp.com/demo/index.html}
filename=${2-screenshot}
```

### Fetch and run a gist

```bash
function curlsource() {
	    f=$(mktemp -t curlsource)
	    curl -o "$f" -s -L "$1"
	    source "$f"
	    rm -f "$f"
	}
	
curlsource https://raw.githubusercontent.com/DEADBEEF/raw
```

## Yes / No input

```bash
#!/bin/bash

read -p "yes or no: " RESPONSE

case "$RESPONSE" in
  yes|y|Yes|Y)
    echo "blah is yes"
    ;;
  no|n|No|N)
    echo "blah is no"
    ;;
  *)
    echo "You need to say yes or no, start over!"
    exit 1
    ;;
esac
```