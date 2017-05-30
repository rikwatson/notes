# Unix Command Line Tools

## bash

 * [The Art of the Command Line](https://github.com/jlevy/the-art-of-command-line)
 * [Tips](http://www.doknowevil.net/2010/10/23/tips-for-using-bash-in-the-linux-terminal-part-1/)

### File name extraction

{% gist 405c13943dff1f6410c35ad01cc4559b %}


### Run in same directory

{% gist 16500c65c387daf03b383a721539b898 %}


But this won't work if there are spaces in the directory spec.

## `uname` System Info

```
uname -a
Darwin Riks-Laptop.local 15.4.0 Darwin Kernel Version 15.4.0: Fri Feb 26 22:08:05 PST 2016; root:xnu-3248.40.184~3/RELEASE_X86_64 x86_64
```

## `pkill`

To kill all processes call `fred`.

```pkill -f fred```

## `finger`

```finger -s kzhfmk```

Unix [oneLine][one liners] at Quora

[10 Tools](http://lifehacker.com/5935869/top-10-tools-that-are-better-in-the-command-line)

[oneLine]: http://www.quora.com/What-are-the-most-useful-Swiss-army-knife-one-liners-on-Unix


## `wget`
### Redirect wget to STDOUT

The following command runs wget and sends the output to STDOUT instead of to a file. Useful for testing a URL's output.

`wget -q -O - http://www.example.com/file.html`

## `find`
### Empty Directories

`find . -type d -empty`

## Files containing a string

`find . -print | xargs grep -il "somestring"`

## Files not containing a string

`find . -print | xargs grep -iL "somestring"`

TODO

`find . -type f -name "*.swift" -print | xargs grep -iL "APPLE"`

or

`find . -type f -name "*.swift" -exec grep -iLH "APPLE" {}  \;`

We can't use the `/dev/null` trick as if will never match; instead replace with `-H` (Can add `'n` for line number too).

# `grep`

`find . -exec grep -i "hi rik" '{}' /dev/null \; -print`

# `scp`

`scp myfile.txt hope@computerhope:myfile.txt`

The above example would copy the file myfile.txt to the computer hope server under the name hope.

`scp remote:/home/hope/* .`

Copy files in the remote machine in the /home/hope directory to your local computer.

## Disk Space

	du -sh *
	du -hsc ./*
    
# `tar`

 * c - Create
 * x - Extract

 * f - specifies the filename (which follows the f) used to tar into or to tar out from; see the examples below.
 * z - use zip/gzip to compress the tar file or to read from a compressed tar file.
 * v - verbose output, show, e.g., during create or extract, the files being stored into or restored from the tar file.


## tar a directory

`tar cvzf foo.tgz {directory}`

then:

`tar xvzf foo.tgz`

## List the contents of a tar file

`tar tvf file.tar`

## List the contents of a tar.gz file

`tar -ztvf file.tar.gz`

## List the contents of a tar.bz2 file

`tar -jtvf file.tar.bz2`

*	t: List the contents of an archive
*	v: Verbosely list files processed (display detailed information)
*	z: Filter the archive through gzip so that we can open compressed (decompress) .gz tar file
*	j: Filter archive through bzip2, use to decompress .bz2 files.
*	f filename: Use archive file called filename

# Using diff

OS-X diff is called Filemerge (From the command line), c.f. `xcode`.

# `du`

This is what `du -sk * | sort -nr` shows in work area.

du --max-depth=1

[more](http://www.linfo.org/du.html)

# `screen`

[Tutorial](http://www.rackaid.com/resources/linux-screen-tutorial-and-how-to/)

Using GNU screen (/usr/bin/screen) in ReadyNAS by tweaker � Fri Nov 21, 2008 9:18 am

	1. install with apt: apt-get install screen

	2. add all non-root users supposed to run /usr/bin/screen to the tty group

	3. change permissions on /dev/ptmx: chmod 664 /dev/ptmx
	(step 3 avoids error messages like "No PTY found, sorry! screen terminated")

	(optional: 4. adjust /etc/screenrc to fit you needs)
	Caution: I'm still unsure, if step 3 is enough once or if it has to be done on every reboot.
 
----
# `ssh`
## Using ssh in webOS

`C:\Program Files\HP webOS\SDK\bin`.  See the screenshot below for newbies.

Now, connect your phone to your computer via the USB cable.

Once connected, type this on your command prompt that's still open:
	novacom -t open tty://
	cd /media/cryptofs/apps/usr/palm
	tar cvzf applications.tgz applications
	exit

Then
	novacom get file://media/internal/application.tgz > applications.tgz

## Copying files

`scp -r -P 10022 root@localhost:/usr/palm/applications/ DESTINATION_DIR_HERE`
Apps located `/usr/palm/applications`
`ssh -p 5522 root@localhost`
scp 

>> `scp -P 5522 file.mp3 root@localhost:/media/internal`

On real device 3rd party applications are stored in `/media/cryptofs/apps/usr/palm/applications`.

Note: When running in the browser, you can bring up the AppMenu by using the keystroke combination

 CTRL + `

Use `tar` with real device - `tar cvzf foo.tgz cps100`

will tar the directory `cps100` (and its files/subdirectories) into a tar file named foo.tgz.

To see a tar file's table of contents use: `tar tzf foo.tgz`

To extract the contents of a tar file use: `tar xvzf foo.tgz`

Then copy .tar file to /media/internal