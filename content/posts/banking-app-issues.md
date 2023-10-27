---
title: "Banking app issues"
date: 2022-10-23T16:17:27-07:00
draft: false
tags: ["GrapheneOS", "SafetyNet", "Play Integrity API", "Banking", "Issues", "Solutions"]
aliases: ["/banking-issues"]
author: "akc3n"
TocOpen: true
description: "How to potentially resolve banking app compatibility issues"
canonicalURL: "https://akc3n.page/posts/banking-app-issues"
---

Potential ways to resolve compatibility issues for users encountering either:
- their freshly installed banking app aborting at launch
- a previously functional banking app suddenly stopped working

> Update: Please see https://discuss.grapheneos.org/d/8330-app-compatibility-with-grapheneos for a more up to date list of possible workaround solutions.

## Introduction

Numerous users encountering such circumstances may find it frustrating and challenging at times. However, for most cases, the common solutions provided below may help resolve *some* of these banking app's compatibility issues. 

_It's very important to thoroughly read [GrapheneOS](https://grapheneos.org)'s [usage guides](https://grapheneos.org/usage#usage) on [Banking apps](https://grapheneos.org/usage#banking-apps) and [Sandboxed Google Play](https://grapheneos.org/usage#sandboxed-google-play) for detailed explanations on topic._

Please be sure to check the [banking apps project](https://privsec.dev/posts/android/banking-applications-compatibility-with-grapheneos/)'s [issue tracker](https://github.com/PrivSec-dev/banking-apps-compat-report/issues?q=is%3Aissue+is%3Aclosed) for possible per-app [updates](https://github.com/PrivSec-dev/banking-apps-compat-report/issues/173#issuecomment-1297347651) (example) in user submitted reports.

## Possible solutions

Enabling [native code debugging](https://grapheneos.org/usage#:~:text=try%20enabling%20this%20again%20if%20you've%20disabled%20it%20) and/or the per-app [exploit protection compatibility mode](https://grapheneos.org/usage#:~:text=can%20enable%20our-,exploit%20protection%20compatibility%20mode,-via%20Settings%20%E2%9E%94%20Apps) is the most common solution.

Banking apps obtained from Aurora Store may become problematic, or not work from the start, and could potentially have security risks if using the Anonymous Login feature. Reinstalling from the Play Store using the official (sandboxed) Play Store client has resolved this in these cases.

### Enable native code debugging

To improve the app sandbox, GrapheneOS allows users to disable native code debugging for better security. This could possibly interfere with apps debugging their own code to add a barrier to analyzing the app. If you have it disabled and the banking app you've installed is not working than you should try enabling it. 

To enable native code debugging:  
`Owner profile` → `Settings` → `Security` → `Enable native code debugging`

### Enable exploit protection compatibility mode

If your banking app is still not working after enabling native code debugging and aborts after launching then perhaps switching from hardened_malloc to Android's standard allocator (Scudo) will resolve the issue.

To enable per-app exploit protection compatibility mode:  
`Settings` → `Apps` → `<App-name>` → `Advanced` → `Enable exploit protection compatibility`

Please read our usage guide on [bugs uncovered by security features](https://grapheneos.org/usage#bugs-uncovered-by-security-features) for more details.

### AuroraOSS is problematic 

- It doesn't fully work compared to sandboxed Google Play
- Apps can check if they were installed from the Play Store and can choose to refuse to work if they were not installed from the Play Store.
- Doesn't verify Play Store signature metadata
- Doesn't use a reduced CA set or pinning like the Play Store itself
- i.e., downloaded apps are only secured by HTTPS with every WebPKI CA trusted (isn't very good)
- May cause your [Google Account to be blocked/blacklisted](https://gitlab.com/AuroraOSS/AuroraStore/-/blob/master/DISCLAIMER.md#1-google-accounts)  by Google.
- When using the anonymous mode login:
- Installs the wrong variant of apps by default due to not searching or fetching apps based on device model
- Shared google accounts, i.e., [Anonymous login mode are problematic](https://twitter.com/GrapheneOS/status/1661989816584511489) and gradually break
- Anonymous account usage may have [negative](https://twitter.com/GrapheneOS/status/1716519096727064697) consequences
- The apps downloaded and installed are obtained from the Play Store anyway and use users have the option of using a throwaway account with [Sandboxed Google Play](https://grapheneos.org/usage#sandboxed-google-play)

Numerous apps from the Play Store rely on features like Play Asset Delivery, Play Feature Delivery, app/content licensing checks, in-app payments, and other functionalities unique to the Play Store. All these are compatible with the sandboxed Play Store. The dependency on these features by Play Store apps is steadily increasing

## Additional information

Here is some additional information for the end user and possible further action that can be taken to help contribute and support the GrapheneOS project.

### SafetyNet replaced by Play Integrity API

Due to the [discontinuation](https://developer.android.com/training/safetynet/deprecation-timeline) of the [SafetyNet Attestation API](https://developer.android.com/training/safetynet/attestation), which has been replaced by the [Play Integrity API](https://developer.android.com/google/play/integrity/overview), some banking apps compatibility issues will not be resolved with the suggested solution(s) above.

### Attestation compatibility guide 

A [detailed guide](https://grapheneos.org/articles/attestation-compatibility-guide) for app developers on how to support GrapheneOS with the hardware attestation API is provided for users to be able to take further action.

> GrapheneOS users are strongly encouraged to share this documentation with app developers enforcing only being able to use the stock OS. Send an email to the developers and leave a review of the app with a link to this information. Share it with other users and create pressure to support GrapheneOS rather than locking users into the stock OS without a valid security reason. GrapheneOS not only upholds the app security model but substantially reinforces it, so it cannot be justified with reasoning based on security, anti-fraud, etc.

