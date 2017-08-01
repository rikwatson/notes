# JavaScript Object Notation

TODO: Move examples to gists.

A subset of [YAML](./yaml), no comments! (But use `JSMin`) Also see [TOML](./toml)

Though, oddly enough, [not](http://timelessrepo.com/json-isnt-a-javascript-subset) [JavaScript](./javascript.md).

> No string in JavaScript can contain a literal `U+2028` or a `U+2029`.

# Comments

JSON can't include comments, but you can pre-process with JSmin to remove them.

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

# Verification

Use `python -mjson.tool` for basic JSON verificationa and pretty printing.

Given:

## `/dev/null`

```bash
cat /dev/null | python -mjson.tool
No JSON object could be decoded
echo $?
1
```

## `{}`

```bash
echo "{}" | python -mjson.tool
{}
echo $?
0
```

## `{"aa": "bb", "bb": "cc"}`

```bash
echo '{"aa": "bb", "bb": "cc"}' | python -mjson.tool
{
    "aa": "bb",
    "bb": "cc"
}
echo $?
0
```

## `{"aa": "bb", "bb": "cc",}` with trailing comma

```bash
echo '{"aa": "bb", "bb": "cc",}' | python -mjson.tool
Expecting property name: line 1 column 25 (char 24)
echo $?
1
```

# Usage

```bash
doSomeCommand

if [ $? -eq 0 ]
then
  echo "Success"
else
  echo "Failure"
fi
```
