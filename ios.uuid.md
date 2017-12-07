# iOS Device Id


*TL;DR* Want to help test an app on iOS, you'll need your device(s) UDID's (Unless you're using TestFlight)

*UDI-what*? -  Unique Device Id. A long hexadecimal number which uniquely identifies your iOS device.

As well as a serial number, every iOS device has a unique _Device Id_, or _UUID_. This identifier can be by developers to create specific build of applications targetted to a given iOS device or set of devices.

Applications built this way can be installed outside of the AppStore and the application simply needs to be [copied](./ios.installing.md) onto the iOS device via iTunes or Xcode.

## How to find the device's UUID

Due to changes in iOS the UUID can no longer be found programmatically, instead either iTunes or a third party service must be used.
 
## Via iTunes

* Open iTunes (the Mac or PC app, not iTunes on your iPhone).
* Plug in your iPhone, iPod touch or iPad.
* Click its name under the devices list.
* Ensure you’re on the Summary tab.
* Click on the text that says Serial Number. It should change to say Identifier (UDID).
* Select Copy from the Edit menu.
* Your UDID is now in the clipboard, so you can paste it into an email or message.
 
## Install a (temporary) profile.
 
Visit [udid.io](http://get.udid.io/) or [SuperUDID](https://betafamily.com/superudid) from Safari on your iOS device and install the profile (which you can delete after) and email me the UDID.