# DRAFT

Notes on setting up environment (tools & configs) in GNULinux/Ubuntu for Android firmware & app development


## Android source

If access to local copy of sources only is needed as fast as possible (using `LineageOS` _18.1_ as example)

install essentials to download:
$ sudo  apt  install  python-is-python3  curl  git-lfs

download and configure repo:
$ curl  https://storage.googleapis.com/git-repo-downloads/repo  >  ~/.local/bin/repo
$ chmod  a+x  ~/.local/bin/repo
$ source  ~/.profile

configure git:
$ git  config  --global  user.name "Your Name"
$ git  config  --global  user.email "your@email"
$ git  config  --global  trailer.changeid.key  "Change-Id"

setup directory for sources:
$ mkdir  -p  devel/android/los/18
$ cd  devel/android/los/18

init repo:
$ repo  init  -u https://github.com/LineageOS/android.git  -b lineage-18.1  --git-lfs

download sources:
$ repo  sync  -c  -j8

Time saving hint: download can be put and left unattended while the rest of android env setup is taking place


## Platform tools (adb & fastboot)


### Android Studio

TBA


### Standalone tarball

Good guide: https://wiki.pixelexperience.org/help/adb-fastboot-guide/
TODO: create short howto based on the guide

binary platform tools/GNULinux: https://dl.google.com/android/repository/platform-tools-latest-linux.zip
adb/udev howto: https://wiki.archlinux.org/title/Android_Debug_Bridge
https://github.com/M0Rf30/android-udev-rules#installation

**plugdev**


## Build environment

TBA


## Compilation

TBA


## Flashing

TBA


## Emulation

TBA


## Internals

### Filesystem

TBA


