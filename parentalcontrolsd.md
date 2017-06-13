# parentalcontrolsd

The `parentalcontrolsd` process is a bugger.

So,

```bash
$ sudo su
```

Create `/var/root/kill_parentalcontrolsd.sh`

```bash
#!/bin/bash
# this is not following best practices
# removing explicit familyControlsEnabled keys to mitigate high parentalcontrolsd cpu usage
rm -rf /Library/Managed\ Preferences/com.apple.applicationaccess.new.plist
rm -rf /Library/Managed\ Preferences/*/com.apple.applicationaccess.new.plist
if pgrep 'parentalcontrolsd'; then
    killall parentalcontrolsd
fi
```

`crontab -e` -> `*/15 * * * * /var/root/kill_parentalcontrolsd.sh`