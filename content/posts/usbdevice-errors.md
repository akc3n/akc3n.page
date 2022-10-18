---
title: "USBDevice Errors"
date: 2022-10-17T22:36:18-07:00
draft: false
tags: ["USBDevice", "WebUSB", "error", "installation"]
author: "akc3n"
TocOpen: true
hidemeta: false
description: "GrapheneOS installation error code meanings and procedure for resolving issues"
aliases: ["/usbdevice"]
canonicalURL: "https://akc3n.page/posts/usbdevice-errors"
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
---

_**Work in progress! Updating this as time permits. Once complete, I will be adding this as well to our [discussion forum](https://discuss.grapheneos.org)**_.


## Access denied

`Error: Failed to execute 'open' on 'USBDevice': Access denied`

What this means is that `udev-rules` have not been [installed](https://grapheneos.org/install/web#flashing-as-non-root).
> USB devices cannot be used as non-root without udev rules for each type of device

**Solution**:  
- Arch Linux: `pacman android-udev`
- Debian/Ubuntu based distros: `apt install android-sdk-platform-tools-common`  
- Reboot the computer

> Connect the phone to the computer. On Linux, you'll need to do this again if you didn't have the udev rules set up when you connected it.

**Note**: Pop!_OS has no known fix

## Unable to claim interface

`Error: Failed to execute 'claimInterface' on 'USBDevice': Unable to claim interface`

## Write the product

`Error: Failed to execute 'transferOut' on 'USBDevice': Write the product`

## No device selected

`Error: Failed to execute unlocking bootloader on USBDevice: No device selected`

## Array buffer allocation

`Error: Array buffer allocation failed`

What this means is that your phone or device has ran [out of memory](https://grapheneos.org/install/web#prerequisites)!
> _You should have at least 2GB of free memory available and 32GB of free storage space._

**Solution**:  
- Reboot the installer phone or use a different device or PC.
- Reboot the installee phone back into the bootloader.

