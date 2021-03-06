# Building iOS Apps

`.app` in `~/Library/Developer/Xcode/DerivedData`

How to convert *app to *ipa

1. Create a folder called Payload
2. Place the .app folder inside of that
3. Zip up the Payload folder using normal compression
4. Then rename the file with a .ipa extension

Gist [create_ipa.sh](https://gist.github.com/rikwatson/cb88c497790fd84a8d3cf9baea2587e4)

Usage `/path/to/script/apptoipa.sh MyFabulousApp.app App\_1\_0\_45`

```bash
#!/bin/bash

if [ -d "Payload" ]; then
  rm -fr Payload/*
else
  mkdir Payload
fi
# if you'd rather copy the .app file, then replace the next line with:
# cp -r $1 Payload
mv $1 Payload
zip -r $2.ipa Payload
rm -fr Payload
```


How to install an `.ipa` file ...

Via [S3](./aws.upload-to-s3.md) etc.

## Code Signing and "fastlane match".

Go and read this [Codesigning Guide](https://codesigning.guide/), then come bask here.

[This](http://artsy.github.io/blog/2017/04/05/what-is-fastlane-match/) article is worth a read.

```ruby
lane :setup_for_app_store do
  app_name = "eigen"
  signing_root = "signing"

  `git clone https://github.com/artsy/mobile_code_signing.git #{signing_root}`

  # prints out the codesigning identities
  system "security find-identity -v -p codesigning"

  # Install the iOS distribution certificate, -A
  system "security import #{signing_root}/ios_distribution.cer  -k ~/Library/Keychains/login.keychain -A"

  # Move our provisioning profile in
  profile_path = File.expand_path("~") + "/Library/MobileDevice/Provisioning Profiles/"
  destination = profile_path + "/" + app_name + ".mobileprovision"
  profile = Dir.glob(signing_root + "/profiles/" + app_name + "/*").first

  # Ensure folder exists
  unless File.directory?(profile_path)
    FileUtils.mkdir_p(profile_path)
  end

  # Migrate it in
  FileUtils.copy profile, destination
  puts "Installed Profile"

  # Install the key
  key = Dir.glob(signing_root + "/keys/" + app_name + "/*").first
  system "security import #{key} -k ~/Library/Keychains/login.keychain -P #{ENV['MATCH_PASSWORD']}  -A "

  # prints out the codesigning identities
  system "security find-identity -v -p codesigning"

  # Clean-up
  `rm -rf #{signing_root}`
end
```