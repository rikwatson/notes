# ImageMagick

## Installing On OS-X

`brew update && brew upgrade && brew install imagemagick`

## Example usage

```
convert -size 320x85 xc:transparent -font Bookman-DemiItalic -pointsize 72 \
  -draw "text 25,60 'Magick'" -channel RGBA -blur 0x6 -fill darkred -stroke magenta \ 
  -draw "text 20,55 'Magick'" fuzzy-magick.png

convert -size 250x250 musical_symbol_g_clef.svg x.png
```

http://www.fileformat.info/info/unicode/char/1d11e/index.htm is musical_symbol_g_clef.svg

Also: http://www.fileformat.info/info/unicode/block/musical_symbols/index.htm


## Imagemagick URLs

 * http://www.imagemagick.org/Usage/channels/#mask_creation << Good [Masks etc]
 * http://www.fmwconcepts.com/imagemagick/tidbits/index.php << Good
 * http://www.fmwconcepts.com/imagemagick/tidbits/image.php
 * http://www.fmwconcepts.com/imagemagick/
 * http://sun.cs.lsus.edu/~rmabry/math/rmabry/imagemagick/multireplace/
 * http://studio.imagemagick.org/pipermail/magick-users/2006-May/017672.html
 * http://www.imagemagick.org/discourse-server/viewtopic.php?f=1&t=10430&p=32965

## Create iOS Icons

Apart from `iTunesArtwork` & `iTunesArtwork@2`, the names of the icons no longer matter as they
are saved as `AppIcon` as part of `Assets.xcassets` these days.

Via `./create_ios_icons.sh`

{% gist 163b6074722c6f5fbc2460b21843c0f5 %}


# List of required iOS Icons

<table class="ios-icons">
      <thead>
        <tr>
          <th>
            <p>Name</p>
          </th>
          <th>
            <p>Size (px)</p>
          </th>
          <th>
            <p>Usage</p>
          </th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>
            <p>Icon-Small.png</p>
          </td>
          <td>
            <p>29x29</p>
          </td>
          <td>
            <p>iPad Settings</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-Small@2x.png</p>
          </td>
          <td>
            <p>58x58</p>
          </td>
          <td>
            <p>iPhone Settings, iPad Settings for Retina display</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-Small@3x.png</p>
          </td>
          <td>
            <p>87x87</p>
          </td>
          <td>
            <p>iPhone Settings for Retina display</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-40.png</p>
          </td>
          <td>
            <p>40x40</p>
          </td>
          <td>
            <p>iPad Spotlight results</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-40@2x.png</p>
          </td>
          <td>
            <p>80x80</p>
          </td>
          <td>
            <p>iPhone Spotlight results, iPad Spotlight results for retina
            display</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-40@3x.png</p>
          </td>
          <td>
            <p>120x120</p>
          </td>
          <td>
            <p>iPhone Spotlight results for retina
            display<br>for iPhone 6s, iPhone 6, and iPhone 5 (@2x)</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-60@2x.png</p>
          </td>
          <td>
            <p>120x120</p>
          </td>
          <td>
            <p>iPhone App Icon<br>for iPhone 4s (@2x)</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-60@3x.png</p>
          </td>
          <td>
            <p>180x180</p>
          </td>
          <td>
            <p>iPhone App Icon for Retina display<br>for iPhone 6s Plus and iPhone 6 Plus (@3x)</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-76.png</p>
          </td>
          <td>
            <p>76x76</p>
          </td>
          <td>
            <p>iPad App Icon</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-76@2x.png</p>
          </td>
          <td>
            <p>152x152</p>
          </td>
          <td>
            <p>iPad App Icon for Retina display<br>for iPad and iPad mini (@2x)</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-83.5@2x.png</p>
          </td>
          <td>
            <p>167x167</p>
          </td>
          <td>
            <p>iPad Pro App Icon for Retina display (@2x)</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>Icon-120.png</p>
          </td>
          <td>
            <p>120x120</p>
          </td>
          <td>
            <p>CarPlay App Icon</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>iTunesArtwork.png</p>
          </td>
          <td>
            <p>512x512</p>
          </td>
          <td>
            <p>App Submission</p>
          </td>
        </tr>
        <tr>
          <td>
            <p>iTunesArtwork@2x.png</p>
          </td>
          <td>
            <p>1024x1024</p>
          </td>
          <td>
            <p>App Submission</p>
          </td>
        </tr>
      </tbody>
</table>


### Note

Apps distributed via ad-hoc distribution may also include a 512 x 512 pixel version of their icon in the `CFBundleIconskey`.
The name of this file must be `iTunesArtwork` (with no file extension). The high resolution version of this icon should be 1024 x 1024 pixels and have the name `iTunesArtwork@2x`
(also without file extension). Do not include this icon in your app bundle if you are not distributing your app via ad-hoc distribution.


----

```
convert -size 320x85 xc:transparent -font Bookman-DemiItalic -pointsize 72 \
  -draw "text 25,60 'Magick'" -channel RGBA -blur 0x6 -fill darkred -stroke magenta \ 
  -draw "text 20,55 'Magick'" fuzzy-magick.png

convert -size 250x250 musical_symbol_g_clef.svg x.png
convert -background lightblue -fill blue  -font Helvetica -size 160x160 label:A  -trim  a.jpg
convert -background red a.jpg  -gravity center -extent 160x160 a_.jpg
```


What we did was:

```bash
convert -background lightblue -fill blue  -font Helvetica -size 160x160 label:A  -trim  temp.jpg
convert -background red temp.jpg  -gravity center -extent 160x160 a.jpg
display a.jpg
```


http://www.fileformat.info/info/unicode/char/1d11e/index.htm is musical_symbol_g_clef.svg
Also: http://www.fileformat.info/info/unicode/block/musical_symbols/index.htm

```
convert -background lightblue -fill blue  -font Candice -size 165x70 -gravity center label:Anthony     label_size_gravity.gif`
```

# URLs

```
http://www.imagemagick.org/Usage/channels/#mask_creation << Good [Masks etc]
http://www.fmwconcepts.com/imagemagick/tidbits/index.php << Good
http://www.fmwconcepts.com/imagemagick/tidbits/image.php
http://www.fmwconcepts.com/imagemagick/
http://sun.cs.lsus.edu/~rmabry/math/rmabry/imagemagick/multireplace/
http://studio.imagemagick.org/pipermail/magick-users/2006-May/017672.html
http://www.imagemagick.org/discourse-server/viewtopic.php?f=1&t=10430&p=32965`
```

# Image Overlays

```
rem
rem ToDo: Get the sizes right for a 96x96 pixel image
rem
rem convert folder.jpg -gravity NorthWest overlays/popupnew.png -gravity South overlays/2.5.png -compose ATop -composite out-ATop.1.jpg
rem convert folder.jpg -gravity NorthEast  overlays/popupnew.png -compose ATop -composite folder-gravity.NE.jpg

convert overlays/folder.jpg -resize 96x96 folder.jpg

convert folder.jpg -gravity NorthWest overlays/popupnew.png -compose ATop -composite folder.new.png

convert folder.new.png -gravity South overlays/2.5.png -compose ATop -composite folder.new.2.5.png

rem
rem    ALL PREVIOUS ARE PNG ---- only this one is Jpeg <<<<< **** <<<<<
rem
convert folder.new.2.5.png -gravity NorthEast overlays/tag_blue.png -compose ATop -composite folder.new.2.5.tagged.jpg`
```