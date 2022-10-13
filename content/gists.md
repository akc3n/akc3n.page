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
