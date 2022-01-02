# dwm - dynamic window manager

## dwm is an extremely fast, small, and dynamic window manager for X.


![image](https://user-images.githubusercontent.com/62089940/147846815-362030e1-72ab-4e0c-a073-1e03e4edba42.png)


This is my patched version of Suckless's (in)famous window manager. 

- The top-bar works well with glyphs and emojis.
- Keyboard controlled volume, brightness etc are already patched in.
- Highly recommend to use NerdFonts to properly display glyphs, emojis etc. 
- For wallpapers, use `feh` and source `~/.fehbg &` from your `.xinitrc`
- Default terminal emulator is set as kitty (can be changed in config.h).
- Screenshots using `flameshot`. Install it using your package manager.

## Requirements
<!-- ------------ -->
In order to build dwm you need the `Xlib` header files.

dmenu, another Suckless utility, is used to launch applications. It is available in most package managers or can be built from source.

You also will need a patched version of `libxft` as it does not have emoji support baked into it.
If you are on Arch Linux, you can get the patched version `libxft-bgra-git` from the AUR.
(i use arch, btw)


## Installation
<!-- ------------ -->
Edit config.mk to match your local setup (dwm is installed into the `/usr/local` namespace by default).

Afterwards enter the following command to build and install dwm (if necessary as root):

    make clean install


## Running dwm
<!-- ----------- -->
Add a `dwm.desktop` file in your `/usr/share/xsessions` directory with the following contents if you are using gdm (Gnome Desktop Manager):

```
[Desktop Entry]
Encoding=UTF-8
Name=Dwm
Comment=Dynamic window manager
Exec=dwm
Icon=dwm
Type=XSession
```

Or add the following line to your .xinitrc to start dwm if you are using startx:

    exec dwm

In order to display status info in the bar, checkout my other repo: dwmblocks
You can customize required modules in the top (battery, time, volume etc.) bar by simply editing shell scripts.

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

Or, you can use `arandr` (GUI client for `xrandr`) to configure your displays.


## Configuration
<!-- ------------- -->
If you want to further customize this version, it is done by creating a custom config.h and (re)compiling the source code.

## To-Do
<!-- ------------- -->
- Add clickablity to the top bar by applying appropriate patches.
- Add a better notification management system.
- Add a compositor for transparency. 

## Resources
The documentation for dwm and all its patches is extremely good.

[Luke Smith](https://www.youtube.com/c/LukeSmithxyz), [Mental Outlaw](https://www.youtube.com/c/MentalOutlaw) and [DT](https://www.youtube.com/c/DistroTube) are great people with amazing tutorials.

