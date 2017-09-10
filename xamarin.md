# Xamarin & Xamarin Forms (XF)

Formally a `.net` / `mono` company, now owned by Microsoft.

Basically a cross platform technology to allow `.net` technology to be used on iOS and Android.

 * [Xamarin Forms / JavaScript Interaction](./xamarin.javascript.md)
 * [Build Cross-Platform Android and iOS UIs with Xamarin Forms](https://www.sitepoint.com/build-cross-platform-android-ios-uis-xamarin-forms/)

## Build Issues with Visual Studio when Cross Compiling with a Mac

The latest version(s) of Visual Studio (2015 & 2017) no longer use a separatly installed Mac host build agent to run [XCode](./xcode.md).

Instead, MS have adopted an [Ansible](./ansible.md) like approach whereby the Windows build device `ssh`'s onto the Mac to perform the build. This is an excellent idea, which will be even better when it works (or at least has better diagnostics).

### Issue 1: You do need to install stuff on the Mac

MS documentatio gives the impression that you don't need to install anything on the Mac & it's all handled by `ssh`. This isn't the case you'll get the following error in `Console.app`  (but no errors from Visual Studio)

```
Jun 16 10:16:33 lounge com.apple.xpc.launchd[1] (com.xamarin.2017-06-16__09-41-37.14988.Broker[2978]): Service could not initialize: 16F73: xpcproxy + 11769 [1505][34964CF1-9965-3B4D-ADC7-6FBC6669C56D]: 0x2
```

You need to install VS for Mac on the Mac. Then...

### Issue 2: Be careful what you do install

The current (2017-06), `Stable Channel` versions of Visual Studio for Mac & Windows are incompatable; which is nice.

The following error will occure when trying to build `The root assembly conflicts with another assembly`.

This can be fixed by installing [xamarin.ios-10.8.0.175.pkg](https://dl.xamarin.com/MonoTouch/Mac/xamarin.ios-10.8.0.175.pkg)


# Next

I would like to automate the build process with something like this:

```
msbuild App1.sln /p:ServerAddress=10.211.55.2 /p:ServerUser=xamUser /p:Platform=iPhoneSimulator /p:ServerPassword=mypassword
```

Details, [here](https://developer.xamarin.com/guides/ios/getting_started/installation/windows/connecting-to-mac/#Command_Line_Support)

----

# A couple ways to submit (publish, upload) a Visual Studio Xamarin.iOS app to the App Store

## Option 1: upload an IPA created via the "Build Adhoc IPA" command

1. Pick the "Ad-Hoc" build configuration.

2. Change the provisioning profile in "project options -> iOS Bundle Signing" to an AppStore provisioning profile.

3. Rebuild the project.

4. Select "Tools -> iOS -> Publish iOS App". This will build the IPA and then automatically open Application Loader on the Mac build host and show the generated IPA.

5. Submit the IPA via Application Loader.


## Option 2: upload a zipped .app bundle

1. Pick the "AppStore", "iPhone" build configuration.

2. Double-check that the provisioning profile in "project options -> iOS Bundle Signing" is an AppStore provisioning profile.

3. Rebuild the project. Then press the "Start" button to perform the remote build step and attempt to deploy to device. Note that the deploy will fail because the provisioning profile is not intended for this usage.

4. Find the resulting `.app` bundle in the build cache folder on the Mac build host:
  ```
  ~/Library/Caches/Xamarin/mtbs/builds/YourAppName/{project-guid}/output/Release/iPhone/YourAppName.app
  ```

5. Zip up the `.app` bundle, for example by running the following command in Terminal.app:
  ```
  zip -r YourAppName.app.zip YourAppName.app
  ```

6. Open Application Loader, click the "Deliver Your App" button, and select the `.app.zip` file when prompted.
----

## React

Is it worth considering what we get from React?

 * [5 Things...](https://medium.freecodecamp.com/the-5-things-you-need-to-know-to-understand-react-a1dbd5d114a3?imm_mid=0ec5a5#.sg5py5ui7)