## PresentTux

## Project brief description
The idea called "PresenTux". <br>
It's a presentation distribution. A linux for making best presentations ever. <br>
And that's it, basically! <br>

## Project full description
<details><summary>Here's long story, if you like to understand the idea in full (feel free to skip it as well):</summary>

I've tired to see people reconnecting devices and setting up everything every time during presentations.
Sometimes (or for somebody who's prepared) it can take 10 to 20 seconds, while at the other times, if somebody isn't prepared or the hardware used is not-so-popular, it can take 5 or even 10 minutes.
This makes speeches inconsistent. It's okay when you have 1, 2 or 3 speakers - but this is **unbearable** when you do have 20 or 30 of them (this is a normal case for a Hackathon starting or ending sessions, as an example).
So I was thinking it's better to take 60 seconds to prepare for every person (or even less, if possible) rather then take 20 seconds for some of the people but usually 3-5 minutes for most of the people. Total waiting time will be less, and the results will be consistant.
Other than that, while somebody is setting up presentations, you see his/her OS, files, chats, browser, open apps, and other personal stuff, that is sometimes not that good to show.
If you really want to give a good speech - you need to create a constant image.
</details>

Here's what PresenTux should do:
* Boot straight into the presentation, ideally, faster than 30 secs, up to 60 secs is OK too
* Support as WIDE majority of hardware as possible (at least x86_64, but ideally also 32-bit and ARM -> not sure if it's possible)
* While loading, EITHER show some pre-defined LOGO, or the First Slide (plymouth)
* Support auto-detection of AMD, Nvidia, or Intel cards to auto-load the driver (or use some generic VESA? I'm not sure) as well as wifi chipsets if user enters URL
* Main partition (EXT4) with the system root / is read-only and never changes
* Second, writable partition (FAT32) where user could put the presentation file, logo and the setting file which should be read upon booting (settings file can include: logo path, presentation path or URL, network settings - ESSID for WIFI and password for wpa_supplicant, other settings)
* Supported options for presentation: PDF file on USB; Text file for "sent" program from Suckless toolkit; or URL to HTML presentation/google slides/whatever
* If the URL is specified: connect via DHCP with eth0 or to wifi
* Ideally, I would have to write an electron or similar wrapper, which will help user to "generate" his own distribution out of the source image, his presentation file and his logo, and then write all of the files to flash drive (similar to balenaEtcher)
* Support "clickers" or remote mouses (this will work out of the box, I think)

I believe that building from scratch is better than stripping-down some large distro but I am open to all suggestions.

I was taking into the consideration the following distros currently:
 - yocto linux
 - alpine (it has "sent" as well as "xpdf" tools in repos! neat! and it boots super fast! but stuggle with graphics drivers)
 - tinycore
 - porteuskiosk (boot into browser)
 - puppy
 - slitaz
 - q4os
 - slax
 - voidlinux

I was also thinking about "static linux" options but I don't sure I really need them.

...

I am open to suggestions in this github repo (issues) as well as via StackOverflow question here:
https://stackoverflow.com/questions/63884697/using-yocto-linux-as-a-base-distro-for-a-presentation-project

## Author
@sxiii

## License
Preferably the GPLv3, BSD, MIT or similar.

## Links
* Website: N/A
* Github: https://github.com/sxiii/bank-of-ideas/blob/master/software/presentux.md
