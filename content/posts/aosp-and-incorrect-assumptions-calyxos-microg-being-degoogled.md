---
title: "AOSP and incorrect assumptions on calyxos and microg being degoogled"
date: 2022-10-17T21:17:49-07:00
draft: false
tags: ["aosp", "false claims", "facts", "degoogle"]
author: "akc3n"
TocOpen: true
hidemeta: false
description: "False claims by calyxos and microg being degoogled"
aliases: ["/micrognotdegoogled", "/calyxosnotdegoogled"]
canonicalURL: "https://akc3n.page/posts/aosp-and-incorrect-assumptions-calyxos-microg-being-degoogled/"
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
---

AOSP doesn't have proprietary Google apps and services.

CalyxOS does have proprietary Google apps and services bundled and not only via microG.
CalyxOS takes AOSP, and adds Google services to it (microG) along with not replacing Google 
as the provider for non-proprietary services.

microG is a very small subset of Google play services.
What microG does is reimplementing a small subset of Play services in a hacky and incomplete 
way, with less security, because they don't implement features like certificate pinning for 
services and apps (TLS and local components), as well security checks.

The apps that work can stop working at any time, if they start using more of the APIs, 
or microG's implementation stops working with Google's servers.

microG doesn't offer an alternative push service but rather has an incomplete implementation 
of Google's push service. The Firebase Cloud Messaging push does not work reliably.

Note apps can use FCM when available and still have working push without it.

Taking AOSP, which never had Google's services, then adding the same Google's services to it in a different way doesn't make something `degoogled`.

