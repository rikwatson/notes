# Electron

_c.f._

Don't forget that people are using [Python](/.python.md) alongside Electron:

 * [Electron as GUI of Python Applications (1)](https://www.fyears.org/2015/06/electron-as-gui-of-python-apps.html) 
 * [Electron as GUI of Python Applications (2)](https://github.com/fyears/electron-python-example)
 * Reddit: [Embedding Python in Electron](https://www.reddit.com/r/Python/comments/3qqz9m/embedding_python_in_electron/)
 * [Rodeo](https://github.com/yhat/rodeo), A data science IDE for Python

## Overview

`Electron` is the html/JavaSript container used by `Atom`, `Visual Studio Code`, `Slack` etc. It can be used to create MAS (Mac App Store) apps.

## Installation

`npm install electron-prebuilt`

## Runing

`electron .`

## References

 * [Quick Start](https://github.com/atom/electron/blob/master/docs/tutorial/quick-start.md)
 * [Fundamentals](http://maxogden.com/electron-fundamentals.html)
 * Creating your [First App](http://tutorialzine.com/2015/12/creating-your-first-desktop-app-with-html-js-and-electron/)
 * [Building a desktop application with Electron](https://medium.com/developers-writing/building-a-desktop-application-with-electron-204203eeb658#.jrj17pcwx)

I've created a few `Electron` Apps which live in `$/work/*/apps/...`

## Mac App Store

 * [electron-osx-sign](https://github.com/electron-userland/electron-osx-sign/wiki/Packaging-and-Submitting-an-Electron-App-to-the-Mac-App-Store)
 * [Mac App Store Submission Guide](https://github.com/electron/electron/blob/master/docs/tutorial/mac-app-store-submission-guide.md)
 * [Some other notes, worth a read](http://liuhao.im/english/2016/01/25/publish-electron-app-to-mac-app-store.html)s

## Structure

```
your-app/
├── package.json
├── main.js
└── index.html
```

### `package.json`

```json
{
  "name"    : "your-app",
  "version" : "0.1.0",
  "main"    : "main.js"
}
```

### `main.js`

```javascript
'use strict';

const electron = require('electron');
const app = electron.app;  // Module to control application life.
const BrowserWindow = electron.BrowserWindow;  // Module to create native browser window.

// Keep a global reference of the window object, if you don't, the window will
// be closed automatically when the JavaScript object is garbage collected.
var mainWindow = null;

// Quit when all windows are closed.
app.on('window-all-closed', function() {
  // On OS X it is common for applications and their menu bar
  // to stay active until the user quits explicitly with Cmd + Q
  if (process.platform != 'darwin') {
    app.quit();
  }
});

// This method will be called when Electron has finished
// initialization and is ready to create browser windows.
app.on('ready', function() {
  // Create the browser window.
  mainWindow = new BrowserWindow({width: 800, height: 600});

  // and load the index.html of the app.
  mainWindow.loadURL('file://' + __dirname + '/index.html');

  // Open the DevTools.
  mainWindow.webContents.openDevTools();

  // Emitted when the window is closed.
  mainWindow.on('closed', function() {
    // Dereference the window object, usually you would store windows
    // in an array if your app supports multi windows, this is the time
    // when you should delete the corresponding element.
    mainWindow = null;
  });
});
```

### `index.html`

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Hello World!</title>
  </head>
  <body>
    <h1>Hello World!</h1>
    We are using node <script>document.write(process.versions.node)</script>,
    Chrome <script>document.write(process.versions.chrome)</script>,
    and Electron <script>document.write(process.versions.electron)</script>.
  </body>
</html>
```

## Making a standalone app

### Packages

 * [Electron Packager](https://github.com/electron-userland/electron-packager)
 * [Electron Builder](https://github.com/loopline-systems/electron-builder)

```bash
git clone https://github.com/electron/electron-quick-start
cd ./electron-quick-start/
npm install
find . -name renderer.js
vim ./renderer.js
npm start
electron-packager .
npm install -g electron-windows-store
```

### Drag & Drop Support

```javascript
// renderer.js
const fs = require('fs')

// This file is required by the index.html file and will
// be executed in the renderer process for that window.
// All of the Node.js APIs are available in this process.
document.ondragover = document.ondrop = (ev) => {
          ev.preventDefault()
}

document.body.ondrop = (ev) => {

        const filename = ev.dataTransfer.files[0].path

console.log(filename)
ev.preventDefault()

fs.readFile(filename, 'utf8', function (err, data) {
        if (err) return console.log(err);

        console.log(data)

});

}
```

[Creat a UWP App](https://electron.atom.io/docs/tutorial/windows-store-guide/)