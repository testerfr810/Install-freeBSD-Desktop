# DarkMate 13.0
desktop install script for FreeBSD

## About
This script helps you set up a desktop system on top of FreeBSD 13.0. It will install PKG, X, MATE, a login manager, some additional tools and set up a 'wheel video [cups]' user.

## Usage
1. Install a minimal image of FreeBSD 13.0 in *Bios/MBR* mode (not UEFI), select *with sources* if you plan on using nVidia drivers, and *do not* create any additional users.
2. Boot your new FreeBSD system and log in as root.
3. Navigate to yout TMP directory, fetch the install script from GitHub, and run it:
```
$ cd /tmp
$ fetch --no-verify-peer http://trisymphony.com/darkMate13
$ chmod +x darkMate13
$ sh darkMate13
```
4. Follow the instructions on screen. If you made a mistake, use CTRL+C to abort, then simply run the script again.

### Installation tutorial on YouTube
You can find a step-by-step guide on YouTube which covers creating a FreeBSD installation image, installing the OS, and installing DarkMate: https://youtu.be/1jIoSwwz2ak

## Advanced options
You can launch the script with additional parmeters:

-x skips the Xorg installation<br />
-u forces freebsd-update<br />
-d skips the new dialog UI

## Keyboard Shortcuts
- SUPER+left, SUPER+right: tile windows left/right
- SUPER+up: maximize window
- SUPER+down: minimize window
- SUPER+e: launch file manager
- SUPER+t: launch terminal
- SUPER+b: launch browser
- SUPER+c: launch calculator
- SUPER+m: launch mail

## Wallpaper location
The custom wallpapers can be found in */usr/local/share/backgrounds/fbsd*

## Screenshots
### Grey theme
![PIC Desktop](Screenshots/dm121a.png)
![PIC Desktop](Screenshots/dm121b.png)
### Alternative red wallpaper
![PIC Desktop](Screenshots/dm121c.png)

## Keyboard codes without dialog
If you do not use the new dialog UI, the script will ask you to define your keyboard layout. If you go with the defaults, you will be getting the standard US layout. A full list of language and variant codes can be found here: https://unix.stackexchange.com/questions/43976/list-all-valid-kbd-layouts-variants-and-toggle-options-to-use-with-setxkbmap

The layout can be changed later at any point. 
- For MATE, simply navigate to the Keyboard Settings. 
- For SLiM, edit the file */etc/X11/xorg.conf.d/10-keyboard.conf*

## Untested
- My hardware selection is limited. Only current nVidia drivers and AMDGPU are tested. If you have older hardware and/or intel graphics, please let me know if/how it works.

## Differences to previous version
- dialog UI is the new default
- graphics support for AMD and Intel
- almost all config files are pulled out of the script and have been put on github as separate files, which will be downloaded as needed

## Changelog
- 2021-04-22: options for SLiM and LightDM, fix for user name (pw add -c)
- 2021-03-10: bug fixes, Mint-Y dark themes, new features: keyboard layout/variant selection, dialog, amd, intel, switch to FreeBSD 13.0-rc1
- 2020-05-02: refactoring, printf, new feature: tmpfs directory
- 2020-03-27: DarkMate 12.1 release, switch to FreeBSD 12.1
- 2019-03-29: first DarkMate release, switch to FreeBSD 12
- 2018-01-11: added -x -u parameters, fixes for KDE/VLC, new network check, Xorg installed by default, echo -y removed, added freebsd-update<br />
- 2018-01-02: Initial release for FreeBSD 10/11

## Credits
- dialog by Thomas E. Dickey https://invisible-island.net/dialog/
- icon theme is PAPIRUS https://github.com/PapirusDevelopmentTeam/papirus-icon-theme
- desktop theming guide by olivierd https://forums.freebsd.org/threads/gschema-override-not-holding.69973/#post-422183
- Arc Grey Theme avaialble on https://github.com/pinpox/arc-grey-theme, retrieved from https://www.gnome-look.org/p/1135255/
