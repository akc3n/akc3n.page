---
title: "Gists"
date: 2022-10-13T00:05:16-07:00
tags: ["gists", "configs", "code"]
author: "akc3n"
TocOpen: true
hidemeta: true
description: "akc3n's gists"
canonicalURL: "https://akc3n.page/gists"
hideSummary: false
searchHidden: false
ShowReadingTime: false
ShowBreadCrumbs: true
ShowPostNavLinks: false
ShowWordCount: false
---

## DNS

### Protect parked domain without email

| HOSTNAME | TYPE | TTL | DATA |
| :--- | :--- | :--- | :--- |
| `<domain.tld> `| TXT | `600` | `"v=spf1 -all"` |
| `*._domainkey` | TXT | `600` | `"v=DKIM1; p="` |
| `_dmarc` | TXT | `600` | `"v=DMARC1; p=reject; sp=reject; adkim=s; aspf=s;"` |
| `<domain.tld>` | MX | `600` | `0 .` |

## EXIF

`exiftool -a -u -g1 -ee3 -api RequestAll=3 IMG_20220723_114829_848.jpg`

Reading meta data information from a file using `exiftool`. The [application documentation](https://exiftool.org/exiftool_pod.html#READING-EXAMPLES) states the following:

> Print all meta information in an image, including duplicate and unknown tags, sorted by group (for family 1). For performance reasons, this command may not extract all available metadata. (Metadata in embedded documents, metadata extracted by external utilities, and metadata requiring excessive processing time may not be extracted). Add -ee3 and -api RequestAll=3 to the command to extract absolutely everything available.

Created a function `chckheader()` added to `$ZSH_CUSTOM/function.zsh`.

```bash
function chckheader () {
    curl "$@" --silent --head --write-out '%{http_code}' | pygmentize -g # json_pp # | xml_pp | pygmentize -l xml
}
```
