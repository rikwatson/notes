# Xamarin Forms / JavaScript Interaction

## Overview

We need a common method to allow the hosting C# app to communicate with the hosted HTML5 application.
It appears that the Xamarin.Forms WebView [API](https://developer.xamarin.com/api/type/Xamarin.Forms.WebView/) doesn't support a common method for JavaScript to invoke C#.

C# to JavaScript is handled by the [Eval](https://developer.xamarin.com/api/member/Xamarin.Forms.WebView.Eval/p/System.String/) method.

There is no (apparent) easy method for the running JavaScript to call the C#. Normally this is done by the JavaScript changing the `window.source` to a "special" URI which is
handled by the C# (but the underlying window is *not* changed).

```javascript
window.source = "NATIVE://some/encoded/method/call" // This won't work
```

Note that these calls are always async.

Perhaps we can run a local webserver on the device (As part of the C# App) so we can replace with:

```javascript
httpRequest("http://localhost:72438/SOMECALL?function=getimdb", function(result){
        callback(result);
    });
```

Implementing a suitable async server in C# should be pretty easy.

Thoughts?

Or just look [here](https://developer.xamarin.com/guides/xamarin-forms/application-fundamentals/custom-renderer/hybridwebview/)


At first you should save it in InstalledLocation folder. We can just use  `file.CopyAsync(htmlFolder, fname + ".html");`

```csharp
StorageFolder htmlFolder = await Windows.ApplicationModel.Package.Current.InstalledLocation.CreateFolderAsync(@"HtmlFiles", CreationCollisionOption.GenerateUniqueName);
IStorageFile file = await htmlFolder .CreateFileAsync(fname + ".html", CreationCollisionOption.GenerateUniqueName);
```

Then you  open the .html file:

```csharp
var fop = new FileOpenPicker();
fop.FileTypeFilter.Add(".html");
var file = await fop.PickSingleFileAsync();
if (file != null)
{
   string myPath = file.Path.Substring(file.Path.IndexOf("HtmlFiles"));
   myWebview.Navigate(new Uri("ms-appx-web:///" + myPath));
}
```

Remember just only from InstalledLocation you can open it with `ms-appx-web:///`

(All in pseudo code). to show dependency injection.

Assuming we have a config.xml file held somewhere then:

### C# Side

```csharp
var configXml = readXmlFile("./Config.xml")

var configAsJsonString = serialiseXmlToJson(configXml)

theWebView.Eval("Config.LoadFromJson("+configAsJsonString+")")
```

### JavaScript

```javascript
var Config = {
    LoadFromJson : function(string){},
    ProcessNewConfig  : function(json){}
}

Config.LoadFromJson = function(JSONString : string){

    this.ProcessNewConfig(stringToJSON(JSONString))

};

Config.ProcessNewConfig = function(JSON : object){

    // Do something with new config

};
    
```

_cf_

 * https://developer.xamarin.com/recipes/android/controls/webview/call_csharp_from_javascript/