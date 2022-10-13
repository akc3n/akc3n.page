---
title: "GrapheneOS is not a ROM!"
date: 2022-10-12T22:02:57-07:00
tags: ["GrapheneOS", "Not a ROM"]
author: "akc3n"
TocOpen: true
hidemeta: false
description: "GrapheneOS is an Operating System!"
canonicalURL: "https://akc3n.page/posts/grapheneos-is-not-a-rom/"
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
---


[GrapheneOS](https://grapheneos.org) *is* an _**Operating System**_ with a very comprehensive package of many different subprojects that all work together in harmony to improve the security of [AOSP](https://source.android.com/): this includes the [Auditor](https://github.com/GrapheneOS/Auditor) and [Attestation Server](https://github.com/GrapheneOS/AttestationServer), [Hardened Android bionic standard C library](https://github.com/GrapheneOS/platform_bionic), [Vanadium](https://github.com/GrapheneOS/Vanadium), [Camera](https://github.com/GrapheneOS/Camera), [PdfViewer](https://github.com/GrapheneOS/PdfViewer), [Apps](https://github.com/GrapheneOS/Apps), [Hardened malloc](https://github.com/GrapheneOS/hardened_malloc) much of the specific work in the kernel, it's right across the entire stack. 

For more information please visit GrapheneOS's [Features](https://grapheneos.org/features).

## Introduction
    
When it comes to GrapheneOS, the term `ROM` is frequently misused. I wanted to compile a list of all the occurrences with reasons as to why it is an incorrect term to use. Perhaps a portion of users are just unaware, others may be misinformed, while some maliciously utilize the phrase "GrapheneOS *ROM*" to propagate misinformation and undermine the project at every opportunity.   

For the time being, all I intended to do was disclose the primary sources and educate people on the necessity of not using the term `ROM` when referring to the GrapheneOS project.   

I hope that individuals whom wish to learn may find these references useful. 

## Twitter
   
[July 13, 2021, 7:00am - @GrapheneOS](https://twitter.com/GrapheneOS/status/1414947876954857482) | [nitter](https://nitter.eu/GrapheneOS/status/1414947876954857482)

> GrapheneOS is an OS. Only a tiny portion of the firmware exists as a ROM and the OS is definitely not part of it. It's not a ROM.

> Components tend to have a boot ROM which is a tiny little bit of code responsible for loading the rest of the firmware and verifying the signature.

[July 13, 2021, 7:02am - @GrapheneOS](https://twitter.com/GrapheneOS/status/1414948470167900161) | [nitter](https://nitter.eu/GrapheneOS/status/1414948470167900161)

> ROM means that the firmware is read-only and cannot be updated. It's only the tiny portion responsible for verifying/loading the rest of the firmware, since fixing a bug in a ROM would require a new revision of the hardware. Nearly all firmware isn't a ROM so it can be updated.

[August 8, 2021, 12:11am - @GrapheneOS](https://twitter.com/GrapheneOS/status/1424267105420066820) | [nitter](https://nitter.eu/GrapheneOS/status/1424267105420066820)

> It's an OS built from AOSP like the stock OS, not a customized stock OS. It's not described as custom or a ROM in our documentation, and those terms don't make very much sense. It can be shipped on a device as the stock OS rather than replacing it. It's not just a replacement OS.

[August 8, 2021, 12:13am - @GrapheneOS](https://twitter.com/GrapheneOS/status/1424267511374176256) | [nitter](https://nitter.eu/GrapheneOS/status/1424267511374176256)

> ROMs are a read-only firmware component generally providing a tiny bit of code needed to load the first updatable firmware in the boot chain.

> Beyond not being accurate, we don't use that term because it confuses users and gives them the wrong idea about what it is. It's an OS.

[December 6, 2021, 1:28am - @GrapheneOS](https://twitter.com/GrapheneOS/status/1467788138995232768) | [nitter](https://nitter.eu/GrapheneOS/status/1467788138995232768)

> Minor side note:

> We avoid misusing the term ROM to refer to GrapheneOS because it needlessly complicates things for end users and isn't technically accurate.

> ROM refers to read-only firmware/data that cannot be updated and that has never applied to smartphone operating systems.


[December 6, 2021, 1:31am - @GrapheneOS](https://twitter.com/GrapheneOS/status/1467788672464527362) | [nitter](https://nitter.eu/GrapheneOS/status/1467788672464527362)

> It's inaccurate jargon from the Android modding community which is not where GrapheneOS originates. Many users have heard of operating systems. Few users have heard of a ROM and since it's not technically accurate it only serves to mislead them if they search for the term, etc.

---

## IRC

[April 21, 2021, 18:54 - #grapheneos](https://freenode.logbot.info/grapheneos/20210421#c7724772)

> I know that a lot of people who do "Custom ROM" development love to pile on all the buttons, knobs, options, and such and configurations to make their own personal analogue mixing console, but that opens up a horrifying pandora's box of allowing user error that we definitely don't want to open

[April 28, 2021, 18:22 - #grapheneos](https://freenode.logbot.info/grapheneos/20210428#c7809458)

> there's a tiny boot ROM hard-wired into the SoC

> ROM means cannot be changed ... (GrapheneOS is not a ROM)

> > Why do people call custom Androids a ROM anyway...writing to the read-only memory is a misnomer lol

> because they don't know what it means

[June 11, 2021, 20:31 - #grapheneos](https://freenode.logbot.info/grapheneos/20210611#c8215414)

> GrapheneOS isn't a ROM, it's an OS

> the boot ROM on the SoC is a ROM, i.e. tiny a read-only piece of firmware that cannot be updated since it's baked into the SoC and is what loads the next stage

[June 14, 2021, 19:33 - #grapheneos](https://freenode.logbot.info/grapheneos/20210614#c8221494)
  
> it's not a ROM, the only ROMs are the boot ROMs on different components, i.e. read-only firmware built into them used to bootstrap code that can be updated

> by definition we cannot ship ROMs as part of the OS since they can't be written/updated

> all firmware that can be updated (the vast majority of it) is updated by GrapheneOS

> people misuse that term and it's confusing/misleading

---

## Reddit

[Tue, July 02, 2019, 6:23PM](https://www.reddit.com/r/GrapheneOS/comments/c8cdxm/when_is_it_needed_to_flash_the_stock_os/esmwz77/) | [teddit](https://teddit.net/r/GrapheneOS/comments/c8cdxm/when_is_it_needed_to_flash_the_stock_os/esmwz77/)

> It doesn't take the approach of a 'custom ROM' where things are hacked together and updates aren't complete or secure.

[Sun, August 18, 2019, 6:36PM](https://www.reddit.com/r/privacytoolsIO/comments/cs2aa4/comment/exdjt0s/) | [teddit](https://teddit.net/r/privacytoolsIO/comments/cs2aa4/comment/exdjt0s/)

> It's not a 'custom ROM' and isn't part of that community / umbrella. I GrapheneOS doesn't aim to satisfy power users who decide they want an alternative OS on their phone and then seek out an OS for it. That's a misunderstanding, and leads to a lot of strange complaints about not supporting devices that are clearly unsuitable for it.

[Thu, Feb 06, 2020, 3:46AM](https://www.reddit.com/r/GrapheneOS/comments/ezjuwc/comment/fgowdeg/) | [teddit](https://teddit.net/r/GrapheneOS/comments/ezjuwc/comment/fgowdeg/)

> GrapheneOS isn't referred to as a "custom ROM". The terminology doesn't make much sense, gives the wrong impression of the project and is simply wrong because the project is in no way limited to users replacing a stock OS.

[Mon, April 20, 2020, 5:13AM](https://www.reddit.com/r/GrapheneOS/comments/g4i02w/comment/fnz3a9n/) | [teddit](https://teddit.net/r/GrapheneOS/comments/g4i02w/comment/fnz3a9n/)

> GrapheneOS is also not a "custom ROM". It's a production OS and can be shipped on devices as the stock OS. See the site and the official responses here, not whatever sources you've been getting information. GrapheneOS is not aimed at power users and does not add features unrelated to privacy, security or filling in gaps left by not having Play Services (i.e. making AOSP more fleshed out / complete). It's not about tweaks or modding. It has block-based updates and verified boot just like you stock OS. You can't modify it aside from making your own builds signed with your own keys, which people are free to do, but that isn't GrapheneOS.

[Tue, May 26, 2020, 9:58AM](https://www.reddit.com/r/GrapheneOS/comments/gpuwn3/comment/frvy98i/) | [teddit](https://teddit.net/r/GrapheneOS/comments/gpuwn3/comment/frvy98i/)

> To clarify something, GrapheneOS is not considered a 'custom ROM' by the project or core community. It is not limited to replacing a stock OS and can be shipped on a device. It is not a customization of the stock OS either. It's a fork of AOSP. It's just an OS, not a 'custom ROM'.

[Fri, Oct 22, 2021, 9:09PM](https://reddit.com/r/GrapheneOS/comments/qch2x5/grapheneos_2021102020_release/hhkxb6o/) | [teddit](https://teddit.net/r/GrapheneOS/comments/qch2x5/grapheneos_2021102020_release/hhkxb6o/)

> It's not only inaccurate but is in-group jargon that doesn't make sense to other people. It's not used by the GrapheneOS project or community. GrapheneOS is an OS. There's no reason to make things needlessly complicated by misusing the term ROM. If people do use it that way, it's going to be corrected.

Replying to [u/tydog98](https://reddit.com/user/tydog98)'s [parent comment](https://reddit.com/r/GrapheneOS/comments/qch2x5/grapheneos_2021102020_release/hhiopsj/):

> > *If you say ROM in the Android community everyone will know what you mean. While it may not be technically accurate it's the nomenclature the community has decided on.*

[Mon, Dec 06, 2021, 5:12PM](https://www.reddit.com/r/GrapheneOS/comments/r68k08/comment/hnj9cu0/) | [teddit](https://teddit.net/r/GrapheneOS/comments/r68k08/comment/hnj9cu0/)

> Side note: GrapheneOS isn't a ROM but rather an OS. A ROM is read-only firmware/data which can't be updated. We avoid misusing that term particularly since it leads to making things seem more complicated.

---

## Notes

`Auditor app`: comes bundled in with GrapheneOS. For non-GrapheneOS [Device Support](https://attestation.app/about#device-support), the standalone app is available via [GitHub](https://github.com/GrapheneOS/platform_external_Auditor/tree/12/prebuilt) and [Google Play Store](https://play.google.com/store/apps/details?id=app.attestation.auditor).

`AttestationServer`: code for use with the Auditor app. It provides two services: submission of attestation data samples and a remote attestation implementation with email alerts to go along with the local implementation based on QR code scanning in the app. [Device integrity monitoring](https://attestation.app/) describes the process in the [About](https://attestation.app/about) section as well as providing a [Tutorial](https://attestation.app/tutorial) with step by step guide.

`Hardened Android standard C library`: Some of the past hardening has not yet been ported from Marshmallow, Nougat and Oreo to this Android Pie repository. Most is available via [archived tags](https://github.com/AndroidHardeningArchive/platform_bionic) (check both the most recent Oreo and Nougat tags).

`Vanadium` [browser](https://vanadium.app/): is a privacy and security hardened variant of Chromium providing the WebView (used by other apps to render web content) and standard browser for [GrapheneOS](https://grapheneos.org). It depends on hardening and compatibility fixes in GrapheneOS rather than reinventing the wheel inside Vanadium. [Web browsing](https://grapheneos.org/usage#web-browsing) is covered in our Usage Guide.

`GrapheneOS Camera app`: based on [Android's CameraX library](https://developer.android.com/jetpack/androidx/releases/camera). It replaces AOSP Camera for GrapheneOS. Here is the [Camera app prebuilt](https://github.com/GrapheneOS/platform_external_Camera/tree/12/prebuilt) using the latest [official release of the Camera app](https://github.com/GrapheneOS/Camera/releases/).

`Secure PDF Viewer app`: Simple Android PDF viewer based on pdf.js and content providers. The app doesn't require any permissions. The PDF stream is fed into the sandboxed WebView without giving it access to content or files. CSP is used to enforce that the JavaScript and styling properties within the WebView are entirely static. [PdfViewer app prebuilt](https://github.com/GrapheneOS/platform_external_PdfViewer/tree/12/prebuilt) using the latest [official release of the PdfViewer app](https://github.com/GrapheneOS/PdfViewer/releases).

`GrapheneOS Apps`: Our new app repository client is in an early stage of [development](https://github.com/GrapheneOS/Apps) and will only be included once it's robust/secure. It will have 3 sections shown as tabs: our own apps, our hardened builds of open source apps and the mirror of Google Play for using sandboxed Google Play. It works already but it needs to have the code for downloading, caching and verifying apps/metadata largely rewritten before we can ship it. Likely at least a few more weeks. Also needs some minor UX improvements too.  
[GrapheneOS Apps prebuilt repository](https://github.com/GrapheneOS/platform_external_Apps/tree/12/prebuilt).  
**Sources**: [Tweet Feb 06](https://twitter.com/GrapheneOS/status/1490523798268825609) ([nitter](https://nitter.eu/GrapheneOS/status/1490523798268825609)) and [Tweet Feb 09](https://twitter.com/GrapheneOS/status/1491375104353513473) ([nitter](https://nitter.eu/GrapheneOS/status/1491375104353513473)). *Please note this citation will be updated when this is officially released.*

`Hardened_malloc`: Hardened allocator designed for modern systems. It has [integration](https://github.com/GrapheneOS/platform_bionic/commit/20160b81611d6f2acd9ab59241bebeac7cf1d71c) into [Android](https://github.com/GrapheneOS/hardened_malloc#android-based-operating-systems)'s [Bionic](https://github.com/GrapheneOS/platform_bionic) libc and can be used externally with musl and glibc as a dynamic library for use on other [Linux-based platforms](https://github.com/GrapheneOS/hardened_malloc#traditional-linux-based-operating-systems). It will gain more portability / integration over time.

`Credit`: [@JollyRoger](https://github.com/Peter-Easton) for editing a revised opening quote from original [IRC source](https://freenode.logbot.info/grapheneos/20200517#c3905998) via [LogBot](https://freenode.logbot.info/) by [Byron](https://github.com/globau).
