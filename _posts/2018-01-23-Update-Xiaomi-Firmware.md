---
title: Update Xiaomi Firmware
categories:
  - posts
tags:
  - Links  
---

[Fastboot method to update firmware](https://forum.xda-developers.com/showpost.php?p=72402783&postcount=15)

1. Go to Xiaomis Fastboot Update Page. http://en.miui.com/a-234.html
1. Download latest Fastboot ROM. Like latest China dev.
1. Extract the content
1. Run Terminal cd to the folder that has the firmware files, like /images for example. (cd pathToExtractedStuff/images)
1. Boot your phone to Bootloader Mode. Vol Down and Power. Until Fastboot shows up
1. Run each of these commands (thx to Luk) in terminal while the folder with the firmwares is the current working folder

    fastboot flash dsp adspso.bin
    fastboot flash bluetooth BTFM.bin  
    fastboot flash cmnlib64 cmnlib64.mbn
    fastboot flash cmnlib64bak cmnlib64.mbn
    fastboot flash cmnlib cmnlib.mbn
    fastboot flash cmnlibbak cmnlib.mbn
    fastboot flash devcfg devcfg.mbn
    fastboot flash aboot emmc_appsboot.mbn
    fastboot flash abootbak emmc_appsboot.mbn
    fastboot flash hyp hyp.mbn
    fastboot flash hypbak hyp.mbn
    fastboot flash keymaster keymaster.mbn
    fastboot flash keymasterbak keymaster.mbn
    fastboot flash logo logo.img
    fastboot flash modem NON-HLOS.bin
    fastboot flash pmic pmic.elf
    fastboot flash pmicbak pmic.elf
    fastboot flash rpm rpm.mbn
    fastboot flash rpmbak rpm.mbn
    fastboot flash splash splash.img
    fastboot flash tz tz.mbn
    fastboot flash tzbak tz.mbn
    fastboot flash xbl xbl.elf
