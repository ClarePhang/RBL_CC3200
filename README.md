# RedBearLab CC3200 Wi-Fi Series

Last updated: 2015/07/24

## Introduction

[RBL CC3200 and WiFi Mini](http://redbearlab.com/) are development boards with low power WiFi capability, they are designed for fast prototyping of IoT projects.

This repository contains the resouces for RBL CC3200 WiFi development boards.  The add-on allows you to start development using the [Energia](http://energia.nu/download/) IDE for these two boards on Windows, Mac OSX and Linux platforms.

It is for Energia version 0101E0015 or before, if you are using 0101E0016 (highly recommended), the IDE already supports these two boards by default, so you do not need this add-on.

## Getting Started

Follow this getting started guide to test the board out of the box:

  http://redbearlab.com/getting-start-with-cc3200/

## Install the Add-on Package (only required for Energia version 0101E0015 or before)

To start doing your own firmware development for the CC3200 boards, follow these steps:

1. Download and install the [Energia](http://energia.nu/download/) on your PC.
2. Clone or download the RedBearLab CC3200 add-on package for Energia.
3. Navigate to "Energia/hardware/cc3200", copy the file "boards.txt" and the folder "variants" to under the path "\<Energia installing path\>\hardware\cc3200", replacing the existing "boards.txt" and merging the folder "variants". It whould not change the existing boards' configuration.
4. Now you can select the RedBearLab CC3200 Wi-Fi boards on Energia IDE.

## Install USB CDC Driver (Windows Only)

Get [this driver](https://mbed.org/media/downloads/drivers/mbedWinSerial_16466.exe) and install it if you are using Windows, so that you can use the USB CDC (Virtual COM Port).  

## Install CC3200 LaunchPack Driver (Windows Only)

The uploader program -- cc3200prog.exe requires ftdxx.dll to run, already included in this add-on, but if you have any problems, download and install [CC3200 LaunchPack Driver](http://energia.nu/guide/guide_windows/) to try.

**Note that you do not need any driver for OSX and Linux platforms.**

## Start Coding

Now you can develop the RedBearLab CC3200 firmware using Energia IDE. Enjoy it!

## Known Issues (fixed in Energia version 0101E0016 already)

Since we are using MK20 as the interface chip, there are some issues and will be fixed soon.

1. Version 0101E0015 of Energia will show some error messages after uploading sketches, however, the sketches should be actually uploaded to the CC3200 correctly.

2. Version 0101E0015 of Energia, after uploading sketch, you need to press the reset button to run. This has been fixed by updating the MK20 interface firmware.
 
## Updating MK20 Interface Firmware

The MK20 firmware provides USB CDC to the system to download sketch to the CC3200. 

Steps to update the firmware:

1. Download the firmware from
    https://github.com/RedBearLab/RBL_CC3200/tree/master/MK20

2. Press and hold the button on the board, connect it to an USB of your PC, it will enter to the MK20 bootloader mode

3. The PC will prompt a drive named "bootloader", the LED on the board will flash slowly

4. Drag and drop the firmware (.bin) to the drive, after that, the LED on the board will flash very fast
    For Mac OSX (e.g. 10.10.3), you need to use command line (Terminal) with the follow command:
      sudo mount -u -w -o sync /Volumes/BOOTLOADER ; cp -X ~/Downloads/CC3200_MK20.bin /Volumes/BOOTLOADER/

5. Remove it from the USB and use it as normal to upload sketches

## Resources

TI CC3200 Official Forum

https://e2e.ti.com/support/wireless_connectivity/f/968

TI CC3200 Official Wiki

http://processors.wiki.ti.com/index.php/CC31xx_%26_CC32xx

RBL CC3200 Boards Support Forum

https://redbearlab.zendesk.com/forums/21199609-RBL-CC3200-WiFi-Mini

Energia Forum

http://forum.43oh.com/forum/28-energia/
