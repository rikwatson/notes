# HockeyApp

Use for iOS and Android beta testing.

Example Andorid upload (From `build.sh`)

```bash
# A quick helper to upload to HockeyApp
hockeyUpload () {
  echo "$2"
  curl https://rink.hockeyapp.net/api/2/apps/$1/app_versions \
      -F status="2" \
      -F notify="2" \
      -F notes="$2" \
      -F notes_type="0" \
      -F "ipa=@$3" \
      -H "X-HockeyAppToken: deadbeef"
}
```

And for iOS (Which is failing) in `nightly_build.sh` (located in ``)

```bash
function push_product_to_hockeyapp {
	echo "Sending to Hockey"
	# Upload to HockeyApp
	# http://support.hockeyapp.net/kb/services-webhooks-desktop-apps/how-to-upload-to-hockeyapp-on-a-mac
	puck api_token=deadbeef -app_id=01234567890abcdef -submit=auto -upload=all -download=true -notes="Nightly build: 2015-07-14" -tags="mobileteam" -upload=all -download=true -notify=true -force=true -open=notify $PROJECT_DIRECTORY$PROJECT_ARCHIVE_NAME.xcarchive
}
```

