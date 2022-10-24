---
title: "Banking app issues"
date: 2022-10-23T16:17:27-07:00
draft: false
tags: ["GrapheneOS", "SafetyNet", "Play Integrity API", "Banking", "Issues", "Solutions"]
aliases: ["/banking-issues"]
author: "akc3n"
TocOpen: true
hidemeta: false
description: "How to potentially resolve banking app compatibility issues"
canonicalURL: "https://akc3n.page/posts/banking-app-issues"
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
---

Possible solutions for users experiencing issues with banking apps not working on their GrapheneOS devices.

Current list of working _international_ banking apps that are compatible with GrapheneOS is located on the `Banking apps project`, which can be found at [PrivSec.dev](https://privsec.dev/banking).

# Introduction

Encountering compatibility issues with banking apps can sometimes be resolved by enabling [native code debugging](https://grapheneos.org/usage#:~:text=try%20enabling%20this%20again%20if%20you've%20disabled%20it%20) and/or enabling our per-app [exploit protection compatibility mode](https://grapheneos.org/usage#:~:text=can%20enable%20our-,exploit%20protection%20compatibility%20mode,-via%20Settings%20%E2%9E%94%20Apps).

Please read our usage guide on [banking apps](https://grapheneos.org/usage#banking-apps) for more details.

## Possible solutions

There are a couple options that may allow for your banking app to work on GrapheneOS.

### Enable native code debugging

To improve the app sandbox, GrapheneOS allows users to disable native code debugging for better security. This could possibly interfere with apps debugging their own code to add a barrier to analyzing the app. If you have it disabled and the banking app you've installed is not working than you should try enabling it. 

To enable native code debugging:  
`Owner profile` → `Settings` → `Security` → `Enable native code debugging`

### Enable exploit protection compatibility mode

If your banking app is still not working after enabling native code debugging and aborts after launching then perhaps switching from hardened_malloc to Android's standard allocator (Scudo) will resolve the issue.

To enable per-app exploit protection compatibility mode:  
`Settings` → `Apps` → `<App-name>` → `Advanced` → `Enable exploit protection compatibility`

Please read our usage guide on [bugs uncovered by security features](https://grapheneos.org/usage#bugs-uncovered-by-security-features) for more details.

### SafetyNet deprecated 

Due to the [discontinuation](https://developer.android.com/training/safetynet/deprecation-timeline) of the [SafetyNet Attestation API](https://developer.android.com/training/safetynet/attestation), which has been replaced by the [Play Integrity API](https://developer.android.com/google/play/integrity/overview), some banking apps compatibility issues will not be resolved with the suggested solution(s) above.

A [detailed guide](https://grapheneos.org/articles/attestation-compatibility-guide) for app developers on how to support GrapheneOS with the hardware attestation API is provided for users to be able to take further action.

> GrapheneOS users are strongly encouraged to share this documentation with app developers enforcing only being able to use the stock OS. Send an email to the developers and leave a review of the app with a link to this information. Share it with other users and create pressure to support GrapheneOS rather than locking users into the stock OS without a valid security reason. GrapheneOS not only upholds the app security model but substantially reinforces it, so it cannot be justified with reasoning based on security, anti-fraud, etc.

