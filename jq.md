# jq - grep for JSON

## Installation

`brew install jq`

TODO: I need to document this

```bash
#!/bin/bash -l

cat << EOF > ./hockeyNameToIdMapping.json
{
  "My Beta":                "DEADBEEF2116aecbaefe18d98171e2c",
  "My Commerce Nightly":    "6DEADBEEF771248cba6aff5f4c972c779",
  "My Commerce Test":       "DEADBEEFe7df43cfaad8fa81f2eaba39",
  "My Experience Nightly":  "DEADBEEFc5dd45ee8d52e0019f0752be",
  "My Experience Test":     "DEADBEEF34ec5133ab2df8adc22d0ae7",
  "My Nightly":             "DEADBEEF7485072eada656d6125682f8",
  "My Test":                "DEADBEEF5c11a4990aad6cf8f1c476df"
}
EOF

cat ./hockeyNameToIdMapping.json | jq '.["My Beta"]' > hockeyId.txt
```

Obviously `./hockeyNameToIdMapping.json` would usually be living outside the Bash script - a Gist perhaps?

If you want to put comments in JSON then use JSmin to remove them.


```bash
curl -s https://daringfireball.net/feeds/json | jq '.items[].title'
```

See [JSON Feed](https://jsonfeed.org/2017/05/17/announcing_json_feed) for more interesting stuff.

## Some Tutorials

 * https://zerokspot.com/weblog/2013/07/18/processing-json-with-jq/
 * https://stedolan.github.io/jq/tutorial/
 * https://robots.thoughtbot.com/jq-is-sed-for-json
 * https://github.com/stedolan/jq/wiki/Cookbook
 * http://blog.librato.com/posts/jq-json
