# Using a Raspberry PI as Web Kiosk

## TODO

 * [raspi-dashboard](https://github.com/nils-werner/raspi-dashboard)
 * [ArchLinux|ARM](https://archlinuxarm.org/platforms/armv6/raspberry-pi) -> ArchLinuxARM-rpi-latest.tar.gz
 * https://www.raspberrypi.org/blog/arch-linux-arm-available-for-download/
 * 

## But Wait, _cf._

Chromebooks and Chromeboxes support [Kiosk Mode Apps](./chrome_kiosk_mode).

----

Recently I've been using a Raspberry PI as a Web Kiosk. This was quite an interesting project with a few subleties over the usual.

Firstly what is a Kiosk. `Kiosk Mode` is a term for a mode in a web browser wherby the browser's chrome is locked down in such a was as to 
only display a single web page - i.e. there is no address bar or menu accessible. This mode is usually used with a SPA (Single Page App) to provide a 
locked down 'kiosk'.

This particular project, for a hotel, had a number of extra interesting features:

 * The pages diplayed could be modified by a Google Spreadsheet  
   Some of these site would not be under our control.
 * The kiosk had a `night mode` when it would display a simple clock & weather widget
 * When in `night mode`, the display could be woken via a PIR detector
 * The display was mounted behind a half silvered mirror, so was effectivly invisble when not in use.

There were some limitations on what pages could be displayed - no Flash etc.

Chrome (or the Chromium project), was the obvious choice for the browser as it provided all the necessary functionality as would run quite well on 
a `Raspberry PI B+`.

Because the hardware would be installed by a third party and there would be no scope for site visits it was necessary to make as much of the `RaspPI`s
configuration remotly held, so that if necessary a simple reboot could be used to update it.

## Hardware
### Raspberry PI

 * Raspberry PI B+
 * 8Gb Micro SD card, class 4 or class 6 - thought 4Gb should be sufficient for our distro, these items are very cheep

### PIR

The PIR switch was quite simple to interface to the `RaspPI` a USB games controller was modified (`hacked`) to receive input from the PIR and
convert them into USB key presses (The games controller looks like a USB keyboard to a PC).

This had a number of advantages:

 * The PIR could be tested quite separaly from the software  
   It could simply be connected to a computer to monitor its inputs
 * There was no hardware modification to the `RaspPI`
 * The SPA running under Chrome could be tested on an machine with Chrome installed (& a keyboard)

## Software
### Distro

The Debian / Raspbian [wheezy][wheezy] distro was chosen which should in theory instal on a 4Gb SD card but, for future expansion,
has been installed on an 8Gb SD card.

#### Obtaining and insstalling basic distro on SD card

The `wheezy` distro can be found [here](TODO), downlosd the xxx.img file and use `dd` to copy to the SD card.

Passsword `pi::raspberry`

Just use sudo for root or see [here][root]

## Resources

 * http://blogs.wcode.org/2013/09/howto-boot-your-raspberry-pi-into-a-fullscreen-browser-kiosk/ 
 * http://raspberrypi.stackexchange.com/questions/2059/disable-screen-blanking-in-x-windows-on-raspbian
 * http://jptoto.jp/geckboard-raspberry-pi/
 * http://lokir.wordpress.com/2012/09/16/raspberry-pi-kiosk-mode-with-chromium/
 * http://www.rs-online.com/designspark/electronics/eng/blog/installing-linux-software-on-raspberry-pi
 * http://www.rs-online.com/designspark/electronics/eng/knowledge-item/raspberry-pi-quick-start-guide
 * http://www.rs-online.com/designspark/electronics/eng/knowledge-item/how-to-create-or-update-your-raspberry-pi-operating-system

#### Via Debian distro

1. Install chromium, x11-xserver-utils and unclutter

	sudo apt-get update && apt-get upgrade -y
	sudo apt-get install chromium x11-xserver-utils unclutter

2. We need to prevent screen from going blank and disable screen saver.

	edit /etc/xdg/lxsession/LXDE/autostart and comment `#` screen saver line and add those lines:

		@xset s off
		@xset -dpms
		@xset s noblank
		@chromium --kiosk --incognito http://coesfaen.herokuapp.com/

[Installing][installing] a image via dd under OS-X

		$ diskutil list

Identify the disk (not partition) of your SD card e.g. disk4 (not disk4s1):
		$ diskutil unmountDisk /dev/<disk# from diskutil>
e.g. diskutil unmountDisk /dev/disk4
		$ sudo dd bs=1m if=image.img of=/dev/DISK
e.g. sudo dd bs=1m if=2014-09-09-wheezy-raspbian.img of=/dev/disk4
This may result in an dd: invalid number '1m' error if you have GNU coreutils installed. In that case you need to use 1M:
		$ sudo dd bs=1M if=image.img of=/dev/DISK
This will take a few minutes.

	$ sudo dd bs=1m if=2014-06-20-wheezy-raspbian.img of=/dev/disk2
	Password:
	2825+0 records in
	2825+0 records out
	2962227200 bytes transferred in 1717.442266 secs (1724790 bytes/sec)
	$

## SPA

The `RaspPI` was configured (see above) to simply boot and then invoke `Chromium` in kiosk mode loading a website hosted on `Heroku`.

This [site](http://coesfaen.herokuapp.com/) becomes the SPA for the kiosk and handled the PIR input, `night mode` and the selection, 
cycling and display of further web sites.

The site has a number of subpages which are displayed in full screen `<iframes>`.

## Heroku

* https://dashboard.heroku.com/login

	Online at http://coesfaen.herokuapp.com (or https://coesfaen.herokuapp.com)
	Deply via https://dashboard.heroku.com/login
	
	NOTE: This page will be refreshed once an hour.
	
	TODO: http://www.youtube.com/watch?v=j6cxZp4ii6c 
becomes

http://www.youtube.com/embed/j6cxZp4ii6c?autoplay=true


Use http, not https for apps, otherwise pages won't load.

 * https://dashboard.heroku.com/apps/screensaver-clock/deploy/dropbox
 * https://dashboard.heroku.com/apps/coesfaen/deploy/dropbox
 * http://screensaver-clock.herokuapp.com
 * http://cycle-pages.herokuapp.com/


## Google Spreadsheet

 * https://spreadsheets.google.com/feeds/list/1t-ESBjG3a9_GcbESfs02S_5od45JSN5SBApW86T-TT4/od6/public/values?alt=json-in-script&callback=rik
 * https://spreadsheets.google.com/feeds/list/1t-ESBjG3a9_GcbESfs02S_5od45JSN5SBApW86T-TT4/od6/public/values?alt=json-in-script&callback=rik
 * https://github.com/GovLab/berrycast/blob/gh-pages/js/script.js is important. Note ..callback=? Converts to JSONP so crossdomain works etc.

You need to do file>Publish to Web then you can see via.

 * https://spreadsheets.google.com/feeds/list/1TinGFwIIufOAzETEL4AbOFOqI_QcF7ie2M3k4-G3hrQ/od6/public/values?alt=json
 * https://spreadsheets.google.com/feeds/list/1TinGFwIIufOAzETEL4AbOFOqI_QcF7ie2M3k4-G3hrQ/od6/public/values?alt=json-in-script&callback=rik

 * https://www.jsoneditoronline.org/#

To edit - https://docs.google.com/spreadsheets/d/1TinGFwIIufOAzETEL4AbOFOqI_QcF7ie2M3k4-G3hrQ/edit#gid=0

Rik, this is what you want, cell based, not list based:

https://spreadsheets.google.com/feeds/cells/1TinGFwIIufOAzETEL4AbOFOqI_QcF7ie2M3k4-G3hrQ/od6/public/values?alt=json


[wheezy]: http://www.raspbian.org/
[root]: http://ekuric.wordpress.com/2013/01/20/raspbian-wheezy-root-password/
[installing]: http://www.raspberrypi.org/documentation/installation/installing-images/mac.md