# iOS Device Id

As well as a serial number, every iOS device has a unique _Device Id_, or _UUID_. This identifier can be by developers to create specific build of applications targetted to a given iOS device or set of devices.
Applications built this was an be installed outside of AppStore and the application simply needs to be [copied](./ios.installing.md) onto the iOS device via iTunes or Xcode.

## How to find the device's UUID

Due to  changes in iOS the UUID can no longer be found programmatically, instead eithe iTunes or a service like [whatsmyudid.com](http://whatsmyudid.com/) must be used.
