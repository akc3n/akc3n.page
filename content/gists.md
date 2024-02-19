---
title: "Gists, snippets and code"
date: 2022-10-13T00:05:16-07:00
tags: ["gists", "configs", "code"]
author: "akc3n"
TocOpen: true
hidemeta: true
description: "Collection of useful information that I find valuable"
canonicalURL: "https://akc3n.page/gists"
hideSummary: false
searchHidden: false
ShowReadingTime: false
ShowBreadCrumbs: true
ShowPostNavLinks: false
ShowWordCount: false
---

## OEM unlocking

Please read [avoid carrier variants of device](https://grapheneos.org/install/web#:~:text=avoid%20carrier%20variants%20of%20the%20devices) first!  

There are a couple ways to check if the device's bootloader can be unlocked.  
> *A device can be carrier unlocked, but not bootloader unlocked. They are two different things. 99% of people only know about carrier unlocking, meaning the device will work on any carrier. — Carrillo*

If you are _here_ and reading this snippet, then _you_ have **not** followed our web method [installation guide](https://grapheneos.org/install/web) accurately!

### Follow GrapheneOS instructions

Please read the instructions carefully and follow the step for [Enabling OEM unlocking](https://grapheneos.org/install/web#enabling-oem-unlocking)!

This requires internet access from the Stock OS with Google Play services as part of `Factory Reset Protection` (`FRP`) for anti-theft protection:  
    1. Connect to Wi-Fi or use your mobile data.

Enable developer mode:  
    2. `Settings` → `About phone`  
    3. Tap `Build number` 7 times → `Enter your pin/pass` → `You are now a developer!`

Enable OEM unlocking:  
    4. `Settings` → `System` → `Developer options` → `OEM unlocking` 

Note:  
- It may take several minutes after connecting to the internet before the `OEM unlocking` toggle is active.
- For [Pixel 6a users](https://grapheneos.org/install/web#:~:text=by%20a%20carrier.-,for%20the%20pixel%206a,-%2C%20OEM%20unlocking%20won't): 
> *For the Pixel 6a, OEM unlocking won't work with the version of the stock OS from the factory. You need to update it to the June 2022 release or later via an over-the-air update. After, you've updated it you'll also need to factory reset the device to fix OEM unlocking.*

### Alternative method via CLI

Using the terminal to verify if the device's bootloader may be unlocked.

Turning on USB debugging:
1. Enable developer mode.  
2. `Settings` → `System` → `Developer options` → `Debugging` → `USB debugging`

<!-- TODO: For your information Linux users need [udev rules](https://github.com/M0Rf30/android-udev-rules) in order to access USB devices. -->

3. Open `Terminal`:

```bash
adb shell getprop ro.boot.cid
```
4. If it returns ANY value except `000000` **than the handsets bootloader is locked**.

### Conclusion

OEM unlocking is disabled (greyed out - unable to toggle it on or off) and value returned is not `000000` from `getprop ro.boot.cid` means you won't be able to install GrapheneOS on that device.

---

## Sieve e-mail filtering

Sieve filter to reject non-encrypted E-mail(s) when using [Protonmail's custom domain](https://proton.me/support/sieve-advanced-custom-filters) by checking `X-Pm-Content-Encryption` header for end-to-end encryption and respond with an automated message

```sieve
require ["reject", "imap4flags", "envelope"]; 
if allof (
    envelope :domain "to" "example.ca",
    not header :matches "X-Pm-Content-Encryption" "end-to-end"
) { 
    reject "Input your response reason for rejecting recipients mail.";
}
```

---

## DNS

### Protect parked domain without email

| HOSTNAME | TYPE | TTL | DATA |
| :--- | :--- | :--- | :--- |
| `<domain.tld> `| TXT | `600` | `"v=spf1 -all"` |
| `*._domainkey` | TXT | `600` | `"v=DKIM1; p="` |
| `_dmarc` | TXT | `600` | `"v=DMARC1; p=reject; sp=reject; adkim=s; aspf=s;"` |
| `<domain.tld>` | MX | `600` | `0 .` |

#### Explanations

**SPF hardfail**

`-all` is the only value in the record, since no other value is specified, the SPF test will always fail. This is a side effect of SPF specified in [Administrator's Considerations](https://www.rfc-editor.org/rfc/rfc7208#section-10.1.2) section.

**NULL MX**

`.` is a special value from [RFC2782](https://www.rfc-editor.org/rfc/rfc2782) (see `Target` and `Usage rules` section) indicating that the "service is decidedly not available at this domain" (p. 4 in `Target` section). Further reading at [RFC7505](https://www.rfc-editor.org/rfc/rfc7505) for NULL MX.

**DKIM p=**

See [3.6.1](https://www.rfc-editor.org/rfc/rfc6376.html#section-3.6.1) and [6.1.2](https://www.rfc-editor.org/rfc/rfc6376.html#section-6.1.2) sections.

In short, the `p=` value normally holds a base64-encoded public key. If this variable is empty, then the key has been revoked and the DKIM test fails.

**DMARC**

Because you set hardfail SPF and DKIM with revoked key, DMARC will always fail. If an attacker tries to spoof your domain, DMARC **will** reject these mails, thus not delivering them *(assuming an attacker has managed to get around SPF somehow, since `"v=spf1 -all"` will normally rejects those mails in the first place)*. Further reading at [RFC7489](https://datatracker.ietf.org/doc/html/rfc7489).

---

## EXIF

```bash
exiftool -a -u -g1 -ee3 -api RequestAll=3 picture.jpg
```

Created a function `chckexif()` added to `$ZSH_CUSTOM/function.zsh`.

```bash
function chckexif(){
    exiftool -a -u -g1 -ee3 -api RequestAll=3 "$@"
}
```

Reading meta data information from a file using `exiftool`. The [application documentation](https://exiftool.org/exiftool_pod.html#READING-EXAMPLES) states the following:

> _Print all meta information in an image, including duplicate and unknown tags, sorted by group (for family 1). For performance reasons, this command may not extract all available metadata. (Metadata in embedded documents, metadata extracted by external utilities, and metadata requiring excessive processing time may not be extracted). Add -ee3 and -api RequestAll=3 to the command to extract absolutely everything available._