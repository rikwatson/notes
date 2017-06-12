# Fastlane

## Overview

[Fastlane](https://github.com/fastlane) is a set of CI tools to help build, test and deploy Android and iOS on macOS.

## Install

First install Xcode (From the Mac App Store), then install the Xcode command line tools via:


```bash
xcode-select --install
```

After Xcode & its tools have been installed, `fastlane` itself can be installed (as a Gem).

```bash
sudo gem install fastlane --verbose
gem cleanup
```

## Updates

Fastlane if frequently updated, so it's worth checking for updates often

```bash
sudo gem update fastlane
```


TODO: `gym --use_legacy_build_api`

 * [Fastlane](https://github.com/fastlane/fastlane) is a CI dream.
 * [Tutorials](https://www.raywenderlich.com/116065/fastlane-tutorial-getting-started)

## Change to `fastfile`

Need to parameterise te following

 * LOGIN_KEYCHAIN
 * LOGIN_KEYCHAIN_PASSWORD
 * TAG_NAME_PREFIX

```ruby
lane :unlock do
	#unlock keychain
	unlock_keychain(path:"/Users/ci/Library/Keychains/login.keychain",password:"ci")
end
```

```ruby
lane :tagAndPush do |options|	
	version = options[:version]

	#Commit plists
	git_commit(path:VERSION_FILES, message:"Version Bump: #{version}")
	
	#As we have a detached head, we will checkout a local branch 
	sh("git checkout -f -b #{BRANCH} || true")
	
	#Try to push to branch	
	tagName = "CI.Nightly.#{version}"
	
	add_git_tag(tag: tagName)

	push_to_git_remote(remote_branch:"#{BRANCH}")	
end
```

## Building from the command line

This following can be added as a [Jenkins](./jenkins.md) step.

```bash
#!/bin/bash -l
export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8
export LANGUAGE=en_US.UTF-8

cd src

export WORKSPACE="my-app.xcworkspace"
export EXPORT_METHOD="enterprise"
export TEAM_ID="DEADBEEFGY6"
# export IPA_NAME="my-app.ipa"
# export IPA_NAME="my-appUITests.ipa"

# Also --scheme my-appUITestsWebViewStatus or my-appUITests


gym --workspace "$WORKSPACE"          \
    --scheme "Debug"                  \
    --silent                          \
    --clean                           \
    --export_method "$EXPORT_METHOD"  \
    --export_team_id "$TEAM_ID"       \
    --include_bitcode false           \
    --include_symbols false           \
    --output_name "my-app.ipa"        \
    --use_legacy_build_api
```



### Uploading to AWS Device Farm

Via `aws_device_farm.rb`

{% gist 07749a6aa97b274b189b787377892036 %}


### Update

`sudo gem update fastlane`

## Quick Start

```bash
cd [your_project_folder]
fastlane init

fastlane actions
fastlane list

fastlane ios test
```

# scan for UI testing

`scan --device "iPhone 6"`

or as part of a lane

`fastlane ios test`

# `snapshot` for screenshots

`fastlane` is written in `Ruby`.

Here is a list of Simulator types.

iPhone 4S
iPhone 5
iPhone 5S
iPhone 5C
iPhone 6
iPhone 6 Plus
iPhone 6S
iPhone 6S Plus
iPad 2
iPad 3
iPad 4
iPad Air
iPad Air 2
iPad Pro
iPad Mini
iPad Mini 2
iPad Mini 3
iPod Touch 5G

```javascript
simulators = ["iPhone 4S", "iPhone 5", "iPhone 5s", "iPhone 5C", "iPhone 6", "iPhone 6 Plus", "iPhone 6s", "iPhone 6s Plus", "iPad 2", "iPad 3", "iPad 4", "iPad Air", "iPad Air 2", "iPad Pro", "iPad Mini", "iPad Mini 2", "iPad Mini 3", "iPod Touch 5G"]
```

Then in `Fastfile`

```ruby
  desc "Runs all the tests"
  lane :test do
  
    simulators = ["iPhone 4S", "iPhone 5", "iPhone 5s", "iPhone 5C", "iPhone 6", "iPhone 6 Plus", "iPhone 6s", "iPhone 6s Plus", "iPad 2", "iPad 3", "iPad 4", "iPad Air", "iPad Air 2", "iPad Pro", "iPad Mini", "iPad Mini 2", "iPad Mini 3", "iPod Touch 5G"]

    simulators.each do |dev|
      puts dev
      scan(device: dev)
    end
    
    # scan(device: "iPhone 6")
  end
```

So we can do a `fastlane ios test` and get the following o/p.

```
...
[12:00:50]: Successfully generated report at '/Users/richard.watson/Dropbox/work/my-app/mobile/iOS/Unit Testing/PercentageCalculator/fastlane/test_output/report.html'
[12:00:51]: Successfully generated report at '/Users/richard.watson/Dropbox/work/my-app/mobile/iOS/Unit Testing/PercentageCalculator/fastlane/test_output/report.junit'

+------+-------------------------------------+-------------+
|                     fastlane summary                     |
+------+-------------------------------------+-------------+
| Step | Action                              | Time (in s) |
+------+-------------------------------------+-------------+
| 1    | Verifying required fastlane version | 0           |
| 2    | default_platform                    | 0           |
| 3    | scan                                | 21          |
...
| 19   | scan                                | 42          |
| 20   | scan                                | 30          |
+------+-------------------------------------+-------------+
```

edit `./fastlane/Snapfile` to chose which screenshot you need (Including localisation)


# [frameit](https://github.com/fastlane/fastlane/tree/master/frameit) for frames round screenshots

Need `imagemagick` - so, `brew update && brew install imagemagick`

First run of `frameit` will advise to grab the images from [here](https://developer.apple.com/app-store/marketing/guidelines/#images) & place in `~/.frameit/devices_frames`

`frameit --help`

`vim ./fastlane/screenshots/Framefile.json`
