# Visual Studio Code

VS Code [Can do that](http://vscodecandothat.com/)
_c.f._

 * [ToM](http://taoofmac.com/space/apps/Visual%20Studio%20Code)

My default settings are:

```json
// Place your settings in this file to overwrite the default settings
{
    "workbench.colorTheme": "Default Light+",
    "git.confirmSync": false,
    "git.enableSmartCommit": true,
    "workbench.welcome.enabled": false,

    // Controls how folders are being reopened after a restart. Select 'none' to never reopen a folder, 'one' to reopen the last folder you worked on or 'all' to reopen all folders of your last session.
    "window.reopenFolders": "all",

    // Controls auto save of dirty files. Accepted values:  "off", "afterDelay", "onFocusChange" (editor loses focus), "onWindowChange" (window loses focus). If set to "afterDelay", you can configure the delay in "files.autoSaveDelay".
    "files.autoSave": "afterDelay",

    // Controls the delay in ms after which a dirty file is saved automatically. Only applies when "files.autoSave" is set to "afterDelay"
    "files.autoSaveDelay": 1000,


    // Disable IntelliSense for words.
    // https://code.visualstudio.com/docs/editor/intellisense
    // Enable word based suggestions
    "editor.wordBasedSuggestions": false
}
```

See Gist - 5e1466108c7146ffa224f5d35e61b4a1 

`<CTRL-P> ext install vscode-solarized`, then ` File > Preferences > Color Theme. (Code > Preferences > Color Theme on Mac)`

Some [notes](https://calebmcelrath.wordpress.com/2017/02/01/thankful-for-integrated-terminals-in-visual-studio-code/) on Terminal.
