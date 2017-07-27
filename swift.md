# Swift

Code currently Swift 3, undoubtedly this will change

TODO: Populate

 * [WkWebView](./swift.wkwebview.md)

## File I/O


In `info.plist` add

```xml
<key>UIFileSharingEnabled</key>
<true/>
```

Code

```swift
// Save data to file
let fileName = "Test"
let DocumentDirURL = try! FileManager.default.url(for: .documentDirectory, in: .userDomainMask, appropriateFor: nil, create: true)

let fileURL = DocumentDirURL.appendingPathComponent(fileName).appendingPathExtension("txt")
print("FilePath: \(fileURL.path)")

let writeString = "Write this text to the fileURL as text in iOS using Swift"
do {
    // Write to the file
    try writeString.write(to: fileURL, atomically: true, encoding: String.Encoding.utf8)
} catch let error as NSError {
    print("Failed writing to URL: \(fileURL), Error: " + error.localizedDescription)
}

var readString = "" // Used to store the file contents
do {
    // Read the file contents
    readString = try String(contentsOf: fileURL)
} catch let error as NSError {
    print("Failed reading from URL: \(fileURL), Error: " + error.localizedDescription)
}
print("File Text: \(readString)")
```