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

## OEM carrier unlocking

One way to check (also provided in our [installation instructions](https://grapheneos.org/install/web#enabling-oem-unlocking)):

Enable the developer options menu by going to Settings ➔ About phone and repeatedly pressing the build number menu entry until developer mode is enabled.

Next, go to Settings ➔ System ➔ Developer options and toggle on the 'OEM unlocking' setting. This requires internet access on devices with Google Play services as part of Factory Reset Protection (FRP) for anti-theft protection.

However, if OEM unlocking is disabled (greyed out - unable to toggle it on or off), then you won't be able to install GrapheneOS on said device.

Another way you can confirm, is by turning on USB debugging, plug your phone in (if you have a laptop with you and the cli tools installed).
In adb run: 
`adb shell getprop ro.boot.cid`. 
If it returns ANY value except `000000`, return that handset as it is Locked.

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
<!-- TODO Add small description and include citations-->

| HOSTNAME | TYPE | TTL | DATA |
| :--- | :--- | :--- | :--- |
| `<domain.tld> `| TXT | `600` | `"v=spf1 -all"` |
| `*._domainkey` | TXT | `600` | `"v=DKIM1; p="` |
| `_dmarc` | TXT | `600` | `"v=DMARC1; p=reject; sp=reject; adkim=s; aspf=s;"` |
| `<domain.tld>` | MX | `600` | `0 .` |

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