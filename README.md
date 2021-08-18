# Hec's build of dmenu


## What is dmenu?
[dmenu](https://tools.suckless.org/dmenu) is a dynamic menu for Xorg, originally made for use in [dwm](https://dwm.suckless.org), but can be used in any other Xorg application.   
This is a very powerful tool since it can be used as many things:
- an application menu
- a power options menu
- many more useful things

Since dmenu is a suckless application, you have to patch it in order to get some more useful functionality out of it. It works perfectly fine without patches, but patching it makes it far more usable.

## patches
These are the following patches used in my build of dmenu:
- [dmenu-border](https://tools.suckless.org/dmenu/patches/border/)
- [dmenu-center](https://tools.suckless.org/dmenu/patches/center/)
- [dmenu-fuzzyhighlight](https://tools.suckless.org/dmenu/patches/fuzzyhighlight/)
- [dmenu-fuzzymatch](https://tools.suckless.org/dmenu/patches/fuzzymatch/)
- [dmenu-numbers](https://tools.suckless.org/dmenu/patches/numbers/)
- [dmenu-lineheight](https://tools.suckless.org/dmenu/patches/line-height/)

These patches are also in the `patches/` folder inside of this git repository.

## How to install my build of dmenu
There are multiple ways of installing my build of dmenu.

### The universal way
This way will work on almost any linux distrobution. You will need the following packages installed:

- libXinerama
- libXft
- make
- git (used to clone the repo)
- gcc
```sh
$ git clone https://github.com/hecknt/dmenu
$ cd dmenu
$ sudo make install
```

From here, you will be able to run `dmenu_run` in your terminal to get an application launcher.

### The archlinux way
[Arch linux](https://archlinux.org) has a tool known as `makepkg`, which can effectively be used to install PKGBUILDS. This repository has a PKGBUILD.  
Install `git` and `base-devel` and run these commands:
```sh
$ git clone https://github.com/hecknt/dmenu
$ cd dmenu
$ makepkg -si
```

This will install `dmenu-hec-git` as a pacman package.
