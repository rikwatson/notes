# Unix File Processing 
 
 * [Unix](./unix.md), in general
 * Unix [Tools](./unix.tools.md)
 * Unix [Bash](./unix.bash.md)

### Extract filename etc

```bash
filename=$(basename "$fullfile")
extension="${filename##*.}"
filename="${filename%.*}"
```

### Remove all blank lines

```bash
grep '.' 
```

### Remove single blank lines

```bash
cat -s # Remove single blank lines
```

### grep

```bash
find . -exec grep -i "hi rik" '{}' /dev/null \; -print
```

### Use sudo with password as parameter

```bash
# The -S switch makes sudo read the password from STDIN. This means you can do

echo mypassword | sudo -S command
```

### Reading configs in Bash

#### configExample.sh

```bash
# Try to read the configuration from:
#   1. the working directory
#   2. The user's home directory
# (in that order)
config_file=".slack.conf"
if [ -f "$(pwd)/$config_file" ]; then
  source "$(pwd)/$config_file"
elif [ -f "$HOME/$config_file" ]; then
  source "$HOME/$config_file"
fi
```

#### ~/.slack.conf

 Configuration file (`~/.slack.conf`) is of the following format:

```
# Your Slack hook URL
SLACK_HOOK_URL=https://hooks.slack.com/services/BEEF4UP4/BEEF2830/BEEFnA8zI4lbaMjR6zQ8FoWr
```