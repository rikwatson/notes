# JaveScript Object Notation

TODO: Move examples to gists.

A subset of [YAML](./yaml), no comments! (But use `JSMin`) Also see [TOML](./toml)

Though, oddly enough, [not](http://timelessrepo.com/json-isnt-a-javascript-subset) [JavaScript](./javascript.md).

> No string in JavaScript can contain a literal `U+2028` or a `U+2029`.

# Comments

JSON can't include comments, but you can pre-process with JSmin to remove them.

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
