# macOS nee OS-X


_c.f._

 * My Mac [setup](/mac_setup.md)


# Notes on [macOS](https://developer.apple.com/macos/), nee OS-X

 * [Mountain Tweaks](http://tweaksapp.com/app/mountain-tweaks/) TODO
 * Keyboard [shortcuts](http://support.apple.com/kb/HT1343)
 * [Automation](http://userautomation.com/automator-quick-start.html)

## Open With Multiple Entries

`/System/Library/Frameworks/CoreServices.framework/Frameworks/LaunchServices.framework/Support/lsregister -kill -r -domain local -domain system -domain user`

# RAID

Well, OS X `10.11` (_El Capitan_) removed the ability to use the UI to create a RAID set.
So, now we have to do a:

`diskutil appleRAID create mirror Media JHFS+ disk4 disk5`

Your value of `disk4` & `disk5` may vary, remember.

[`diskutil list`](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man8/diskutil.8.html) is your friend (sometimes).


# Packet Tracing / Sniffing

I'll need to capture network traffic if I'm to do some of the stuff I need to do to work out IP addresses etc.

 * [tcpdump]
 * [packetpeeper] latest is `PacketPeeper_17_08_2008.dmg`
 * [cpa] latest is `CPA_121.dmg`

# Create standalone Mac OS X applications with Python

http://svn.pythonmac.org/py2app/py2app/trunk/doc/index.html

[Running Python in background on OS X](http://stackoverflow.com/questions/9522324)

http://wiki.python.org/moin/MacPython/py2app

 * [Python On The Mac](http://www.python.org/getit/mac/)
 * [Can you create an Mac OS X Service with Python? How?](http://stackoverflow.com/questions/5527899)
 * [Mac OS X specific services](http://docs.python.org/library/mac.html)



[tcpdump]: http://support.apple.com/kb/ht3994
[packetpeeper]: http://packetpeeper.sourceforge.net/
[cpa]: http://www.tastycocoabytes.com/cpa/

# [parentalcontrolsd](./parentalcontrolsd.md)