# Android

 * [Using Docker for Android Testing](./docker.android.md)
 * [Device fragmentation](./android.fragmentation.md) & the developer

----

# In Camera

## [Apps](./android_apps.md)

## Development

Software development hints & tips.

* [TabHost](android_tabhost.markdown)
* [PhoneGap / WebView](android_webview_phonegap.markdown)
* [Flurry](android_flurry.markdown)
* [Wi-Fi](android_wifi.markdown)
* [Splashscreens](android_splashscreen.markdown)
* [Settings](android_settings.markdown)

## Reading List

* [31 Days](http://chrisrisner.com/31-Days-of-Android) - and [my](android_31_days_notes.markdown) notes.

## Resources

### Dev Tools

 * [Web Dev Apps](http://www.sitepoint.com/free-android-web-development-apps/)

### WWW

* [Think Android](http://thinkandroid.wordpress.com)
* [RoboGuice](http://code.google.com/p/roboguice/) for Android.
* TDD via [Robolectric](http://pivotal.github.com/robolectric/)
* Must have [Libraries](https://www.virag.si/2012/06/must-have-libraries-in-modern-android-developer-toolbox/)
* The Android Weekly [Toolbox](http://androidweekly.net/toolbox)
* Android App [Patterns](http://www.android-app-patterns.com/) c.f. [grids](http://www.android-app-patterns.com/category/grid)
* HTTP [Client](http://turbomanage.wordpress.com/category/android/)

## Podcasts

* CSSE490 In [iTunes](http://itunes.apple.com/gb/podcast/csse490-android-development/id409819366), [calendar](https://docs.google.com/document/edit?id=1BVrqUPsvlq8Ww-HhVD3g1OVc32M6E7xDk3vLP3wJbAo&pli=1) use the book Professional Android 2 Application Development (Reto Meier). Android Wireless Application Development; Hello, Android [Prag Prog]. - References CSSE220 - Java

## Questions

* What is the difference between an Activity & a View?
* How do you display a setting page?

## TODO

### Build the V4 Sample Apps

`C:\self\Dropbox\bin\android-sdk-macosx\samples\android-16\ApiDemos` look at tge README & import jar file.

## Reverse Engineering

Reverse [Engineering](http://code.google.com/p/androguard/) & [Binary XML](http://androguard.blogspot.com/2011/03/androids-binary-xml.html).
Also [android-apktool](http://code.google.com/p/android-apktool/)
a [few](http://code.google.com/p/android-random/) tools here as well.

`c:\and_test\java -jar AXMLPrinter2.jar p1220_symbol_sip.xml > p1220_symbol_sip.txt`

# Android Services

Concerning [AndroidServices](http://www.vogella.com/articles/AndroidServices/article.html).

# Knowledge Bases

* CodeProject's [Knowledge](http://www.codeproject.com/KB/android/) base.
  * http://www.codeproject.com/Articles/113831/An-Advanced-Splash-Screen-for-Android-App
  * http://www.codeproject.com/Articles/107693/Tabbed-Applications-in-Android 
 * http://www.codeproject.com/Articles/392603/Android-addJavaScriptInterface
 * 

## Tabbed WebView resources

TabActivity is [depreciated](http://developer.android.com/reference/android/app/TabActivity.html), use Fragments instead.
However to get something going **quickly** I think we should continue to use TabActivity.

http://android-ed.blogspot.co.uk/2011/03/using-tabactivity-in-android.html


Tabs consists of TabActivities and Tabxxx's

[Tutorial](http://www.codeproject.com/Articles/107693/Tabbed-Applications-in-Android)
[Fragments](http://developer.android.com/reference/android/app/Fragment.html) look cool.


The [Action Bar](http://www.androidpatterns.com/uap_pattern/action-bar) [looks](https://github.com/johannilsson/android-actionbar) [good](http://developer.android.com/tools/samples/index.html)

Holo [Everywhere](http://android-developers.blogspot.co.uk/2012/01/holo-everywhere.html).


* Actions [bar](http://developer.android.com/guide/topics/ui/actionbar.html)
* Options [menu](http://developer.android.com/guide/topics/ui/menus.html#options-menu)

## Nice UI Elements

* [Status Bar Notification](http://android-coding.blogspot.co.uk/2010/12/status-bar-notification.html)
* Native [icons](http://www.yay.se/resources/android-native-icons)

## Misc Stackoverflow Articles

* [displaying-android-asset-files-in-a-webview](http://stackoverflow.com/questions/5320288/)
* LastFM [android-starting-an-activity-for-a-different-third-party-app](http://stackoverflow.com/questions/3518407/)
* [android-how-do-you-display-webview-inside-tabview](http://stackoverflow.com/questions/4160199/)
* [getting-android-sdk-webview-and-tabwidget-to-play-nice](http://stackoverflow.com/questions/1433880/)
* [webview-inside-tabview-fail](http://stackoverflow.com/questions/3591189/)
* [webview-inside-tab-hiding-the-tabwidgets](http://stackoverflow.com/questions/2717750/)
* [android-including-multiple-java-packages-to-manifest](http://stackoverflow.com/questions/3935443/)
* [android-tabactivity-deprecated-using-fragment-instead](http://stackoverflow.com/questions/9062611/)
* Rotation [my-webview-reloads-when-i-change-from-portrait-to-lanscape](http://stackoverflow.com/questions/5628924/) causes reload issues.

# 3rd Party Stuff

## Applications

The [iJetty](http://code.google.com/p/i-jetty/downloads/list) web server.

## Components

## [Maven](http://blog.stylingandroid.com/archives/1067#)

[Android HTTP Server](http://code.google.com/p/android-http-server/)
[Tiny Clound Android HTTP Server](http://www.ibm.com/developerworks/opensource/library/os-tinycloud/index.html) - the native one!
[Async HTTP Client](http://loopj.com/android-async-http/)

----


+ SimpleNote
+ Growl Notification, see [here](http://growl.info/documentation/developer/).
+ Kappa - use [Cling](http://teleal.org/weblog/) & [here](http://teleal.org/projects/cling/) 
& for [Android](http://teleal.org/projects/cling/core/manual/cling-core-manual.html#chapter.Android) for UPnP / DNLA services.


