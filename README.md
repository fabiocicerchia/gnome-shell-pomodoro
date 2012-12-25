# Pomodoro extension for GNOME Shell
- Provides a countdown timer in the [GNOME Shell](http://www.gnome.org/gnome-3/) top panel
- Keeps track of completed 25 minute cycles

![Pomodoro image](http://kamilprusko.org/files/gnome-shell-pomodoro-extension.png)

You can read more on pomodoro technique [here](http://www.pomodorotechnique.com).

*This project is not affiliated with, authorized by, sponsored by, or otherwise approved by GNOME Foundation and/or the Pomodoro Technique®. The GNOME logo and GNOME name are registered trademarks or trademarks of GNOME Foundation in the United States or other countries. The Pomodoro Technique® and Pomodoro™ are registered trademarks of Francesco Cirillo.*

# Installation
## Web based (recommended)
https://extensions.gnome.org/extension/53/pomodoro/

## Archlinux
Get from [AUR](http://aur.archlinux.org/packages.php?ID=49967)

## Gentoo
Available at [Maciej's](https://github.com/mgrela) overlay [here](https://github.com/mgrela/dropzone/tree/master/gnome-extra/gnome-shell-extensions-pomodoro). Instructions [here](http://mgrela.rootnode.net/doku.php?id=wiki:gentoo:dropzone).

## Direct from source
1. Get zipball
    * [for GNOME Shell 3.4](https://github.com/codito/gnome-shell-pomodoro/zipball/gnome-shell-3.4)
    * [for GNOME Shell 3.6](https://github.com/codito/gnome-shell-pomodoro/zipball/gnome-shell-3.6)
    * [Unstable – our master branch](https://github.com/codito/gnome-shell-pomodoro/zipball/master)

2. Build it and install

        ./autogen.sh --prefix=/usr
        make zip
        unzip _build/gnome-shell-pomodoro.0.6.zip -d ~/.local/share/gnome-shell/extensions/pomodoro@arun.codito.in

    To install it system-wide, you could do

        ./autogen.sh --prefix=/usr
        sudo make install

    …and after a successful installation remove the local extension

        rm -R ~/.local/share/gnome-shell/extensions/pomodoro@arun.codito.in

3. Enable the extension using `gnome-tweak-tool` (Shell Extensions → Pomodoro) or via following commandline:

        gsettings get org.gnome.shell enabled-extensions
        gsettings set org.gnome.shell enabled-extensions [<values from get above>, pomodoro@arun.codito.in]

4. Press *Alt + F2*, and `r` in command to restart GNOME Shell

# Usage
- Use toggle switch (or Ctrl+Alt+P) to toggle timer on/off
- You can configure behavior of the extension in *Options* menu

For a list of configurable options, please refer [wiki](https://github.com/codito/gnome-shell-pomodoro/wiki/Configuration)

# License
GPL3. See COPYING for details.

# Thanks
- Contributors: https://github.com/codito/gnome-shell-pomodoro/contributors

# Changelog
**Unstable**

+ Czech translation
+ Support for GNOME Shell 3.6
+ 

**Version 0.6**

+ New translation: Persian (thanks @arashm)
+ Feature: Support for GNOME Shell 3.4
+ Breaking change: Dropped support for older gnome-shell versions due to incompatible APIs
+ Feature: Support for "Away from desk" mode
+ Feature: Ability to change IM presence status based on pomodoro activity
+ Fixed issues #38, #39, #41, #42, #45 and [more](https://github.com/codito/gnome-shell-pomodoro/issues?sort=created&direction=desc&state=closed&page=1)

**Version 0.5**

+ Bunch of cleanups, user interface awesomeness [Issue #37, Patch from @kamilprusko]
+ Config options are changed to more meaningful names [above patch]

**Version 0.4**

+ Sound notification at end of a pomodoro break [Issue #26, Patch from @kamilprusko]
+ System wide config file support [Patch from @mgrela]
+ Support to skip breaks in case of persistent message [Patch from @amanbh]
- Some minor bug fixes, and keybinder3 requirement is now optional
