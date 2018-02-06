---
layout: post
title:  "ChromeOS Kiosk Mode"
categories: code web
permalink: /chrome_kiosk_mode
---

 * [Use a ChromeOS as a kiosk](https://support.google.com/chromebook/answer/3134673)
 * [kiosk_enabled](https://developer.chrome.com/apps/manifest/kiosk_enabled)
 * [Single App Kiosk Mode](https://support.google.com/chromebook/answer/3134673)
 * [Create a Chrome kiosk app](https://support.google.com/chrome/a/answer/3316168)
 * `Chrome App Builder` is the toy.
 * My [Developer Dashboard](https://chrome.google.com/webstore/developer/dashboard/g01231776026106733594)
 * [Create a private Chrome app](https://support.google.com/chrome/a/answer/2714278?hl=en)
 * [Packing the extension](https://developer.chrome.com/extensions/packaging)
 * Coesfaen is - `gipgofljpkgeohgbimhjpdbgpmangjid`

If you want to keep the extension ID the same, follow these steps:

 1. Rename the private key that was generated when you created the .crx file to key.pem.
 2. Put key.pem in the top directory of your extension.
 3. Compress that directory into a ZIP file.
 4. Upload the ZIP file using the Chrome Developer Dashboard.