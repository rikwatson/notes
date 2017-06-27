# Unix

 * Unix [File Processing](./unix.file_processing.md)
 * Unix [Tools](./unix.tools.md)
 * Unix [Bash](./unix.bash.md)




### Change file extension on multiple files

```bash
for f in *.markdown; do mv -- "$f" "${f%.markdown}.md"; done
```

## bash

### Remove JSON comments

```bash
#!/bin/bash -l
#
# Install JSmin
#
brew install jsmin

# Some JSON with a comment..

cat << EOF > ./jsonWithComments.json
{
  "My Beta":                "DEADBEEF2116aecbaefe18d98171e2c",  // This is a comment
  "My Commerce Nightly":    "6DEADBEEF771248cba6aff5f4c972c779",
  "My Commerce Test":       "DEADBEEFe7df43cfaad8fa81f2eaba39",
  "My Experience Nightly":  "DEADBEEFc5dd45ee8d52e0019f0752be",
  "My Experience Test":     "DEADBEEF34ec5133ab2df8adc22d0ae7", // Another (Illegal) comment
  "My Nightly":             "DEADBEEF7485072eada656d6125682f8",
  "My Test":                "DEADBEEF5c11a4990aad6cf8f1c476df"
}
EOF

echo "JSON with comments"

cat ./jsonWithComments.json

cat ./jsonWithComments.json | jsmin > ./jsonWithoutCommenets.json

echo "JSON without comments"

cat ./jsonWithoutCommenets.json

echo "Make it pretty (again)"

cat ./jsonWithoutCommenets.json | python -mjson.tool 
```

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

{% gist 405c13943dff1f6410c35ad01cc4559b %}


### Run in same directory

{% gist 16500c65c387daf03b383a721539b898 %}

But this won't work if there are spaces in the directory spec.
