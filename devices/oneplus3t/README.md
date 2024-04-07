# OnePlus 3T


## Direct links

[`wget`-_compatible_ file](oneplus3t.txt) to download all related prebuilt software.


## Official firmware

- [site](https://www.oneplus.com/global)
- [download place](https://service.oneplus.com/global/search/search-detail?id=2096329&articleIndex=1)
- [download link](https://oxygenos.oneplus.net/OnePlus3TOxygen_28_OTA_086_all_1911042121_f2d6336ae39a4545.zip)
- release notes:
```
OnePlus 3T

System
• Updated Android security patch to 2019.10
• Updated GMS apps
• General bug fixes and improvements
 'z-var' into z-localization
9.0.6
	November 29, 2019

1.52GB

e4e46aa9eebffdd485071383dcda4218
```


### Initial setup

#### Unlocking

- turn on the device
- skip all the logins/settings
- go to _Settings_ and enable _Developer options_ by openning _About phone_ and clicking multiple times on _Build number_
- go to _Developer options_ and enable _OEM unlocking_ and _USB debugging_

#### Online official OTA

- go to _Settings_ - _System updates_
- download original OTA update (if available):
```
OS Version: Oxygen OS 4.5.1
Update size: 1498MB
```
- click on `REBOOT TO UPGRADE NOW`
- wait for reboot & update install
- wait for another reboot & apps' _optimization_
- wait for _Finishing Android Update_ notification

#### Local official OTA

- upload `9.0.6 OTA` update manually to the device (using adb/local http server)
- move update tarball to the root of `/sdcard` if necessery
- go to _Settings_ - _System updates_ - _"gear"_ - _Local upgrade_, pick tarball and click `UPGRADE NOW`
- wait for reboot & update install




## Custom firmware

### TWRP

- [official site](https://twrp.me) / https://twrp.me

#### APK

- [App page](https://dl.twrp.me/twrpapp) / https://dl.twrp.me/twrpapp
- [APK link](https://dl.twrp.me/twrpapp/me.twrp.twrpapp-26.apk) / https://dl.twrp.me/twrpapp/me.twrp.twrpapp-26.apk ( [md5](https://dl.twrp.me/twrpapp/me.twrp.twrpapp-26.apk.md5) | [sha256](https://dl.twrp.me/twrpapp/me.twrp.twrpapp-26.apk.sha256) )

#### Recovery
TBA
device page
https://twrp.me/oneplus/oneplusthree.html

download place
https://dl.twrp.me/oneplus3/
https://dl.twrp.me/oneplus3/twrp-3.7.0_9-0-oneplus3.img.html

download link
https://dl.twrp.me/oneplus3/twrp-3.7.0_9-0-oneplus3.img

https://dl.twrp.me/oneplus3/twrp-3.7.0_9-0-oneplus3.img.md5
https://dl.twrp.me/oneplus3/twrp-3.7.0_9-0-oneplus3.img.sha256

xda thread
https://xdaforums.com/t/recovery-unified-official-twrp-touch-recovery-for-oneplus-3-3t.3742894/

source tree
https://github.com/TeamWin/android_device_oneplus_oneplus3

minimal build env
https://github.com/minimal-manifest-twrp


### GApps

opengapps (<=11)
https://opengapps.org/

mindthegaps (github)
https://github.com/MindTheGapps

mindthegaps (gitlab)
https://gitlab.com/MindTheGapps


### PixelExperience

Builds

download place
https://get.pixelexperience.org/oneplus3

download link
zip
https://get.pixelexperience.org/changelog/oneplus3/PixelExperience_oneplus3-11.0-20210921-1306-OFFICIAL.zip
b8df266730ffab20659bc51f691fcacd

tutorials
https://wiki.pixelexperience.org/devices/oneplus3/

installation
https://wiki.pixelexperience.org/devices/oneplus3/install

building
https://wiki.pixelexperience.org/devices/oneplus3/build


### LineageOS

Builds

download place
https://download.lineageos.org/devices/oneplus3/builds

download link
zip
https://mirrorbits.lineageos.org/full/oneplus3/20231205/lineage-18.1-20231205-nightly-oneplus3-signed.zip
9e1abcfeafce164f8ddca6c4d754976ece5be97bc77cad088b077eaf2d889bf5

boot.img
https://mirrorbits.lineageos.org/full/oneplus3/20231205/boot.img
daa85b9c67012ec431b4a349ed9c8d0e96667443b30626efc415f220c1c0d2c9

recovery.img
https://mirrorbits.lineageos.org/full/oneplus3/20231205/recovery.img
00b0e108d2b81e1108dd9fb6976821dbabccb7250dbe8909f2cf4df2ae665498

tutorials
https://wiki.lineageos.org/devices/oneplus3/variant2/

installation
https://wiki.lineageos.org/devices/oneplus3/install/variant2

building
https://wiki.lineageos.org/devices/oneplus3/build/variant2




### Building manually

TBA




## Flashing firmware

**CHECK md5/sha256 sums before sending any file to a device**

- configure environment
  - download & set latest adb/fastboot
  - configure rules / permissions
- enable adb on the target android device
- enable `oem unlock` in _Settings_
- attach android device to PC
  - reboot to bootloader: `$ adb  reboot  bootloader`
  - make sure that target device is _active_ and visible: `$ fastboot  devices`
  - initiate bootloader unlocking: `$ fastboot  oem  unlock`
- follow prompts on the screen to unlock bootloader
- device will be wiped & rebooted
- set up device again after first start
- enable adb again in _Settings_
```
adb  reboot  bootloader
fastboot  boot  /path/to/recovery.img // to test & to backup
```
- backup everything using twrp
- transfer backup to reliable storage
- reboot to bootloader
- flash recovery
```
fastboot  flash  recovery  /path/to/recovery.img
```
- reboot to bootloader
- boot to recovery
- wipe everything except system
- reboot to recovery

- sideload

- sideload gapps

TBA


## Rooting

TBA Magisk howto


