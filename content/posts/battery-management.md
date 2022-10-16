---
title: "Battery Management"
date: 2022-10-15T22:45:36-07:00
tags: ["GrapheneOS", "Battery management"]
author: "JollyRoger"
TocOpen: true
hidemeta: false
description: "Power Management For Power Users"
canonicalURL: "https://akc3n.page/posts/battery-management"
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
---

## Introduction

A recurring question we get at the GrapheneOS IRC Channel is how to maximize the healthy lifespan of your phone's the battery. The official answer we have to this is very simple if you'd like to ensure your phone's battery lasts the longest:

That answer is to keep your phone plugged in to the original charger that it came with, with the original cable that it came with, 24 hours a day, 7 days a week, 365 days a year.

*Gasp!*

Yes, you heard that right. If you want to keep your phone's battery health in the best possible condition it possibly could be in, you must use the Google charger and cable and keep them all plugged in around the clock. *"But Peter,"* I hear you saying already *"Isn't the best thing to do to completely discharge the battery before recharging it/charging only to 80%/using wireless charging/unplug when fully charged/only using slow charging/sacrificing a small animal to the machine God/using adaptive smart charging with Cloud based Blockchain AI?"*

No, here's why:

## Don't limit charging to 80% or actively avoid leaving your phone plugged in

Back in 2005, gadgets with built-in lithium batteries, did not have their own onboard battery management which necessitated manual battery management. At the time, some gadgets started offering options that included shutting off at 80% of capacity to maximize the lifespan of the battery.

It's not 2005 anymore.

Sixteen years later, phones with built-in batteries have their own computers onboard the device, which can take into account the number of charge cycles the battery has undergone and automatically reallocate overprovisioning as required to ensure they automatically and transparently set the charging and cutoff thresholds to give the best health of the battery over time. This makes the old school of thought of charging to 80% obsolete.

Not only that, but when your phone's battery is reported at 100% and charging, the battery enters idle maintenance, which ensures that the battery is not going to self-discharge, without overcharging it. In this state, the phone can remain on and be powered off external power from USB, rather than using the battery. This is important to the health of your battery by reducing the amount of demand you're placing on it.

So the long story short, if you decide you want to charge to only 80%, and then unplug your phone once it's reached that threshold, you're not doing your battery any favours; it's not making use of idle maintenance, and instead of running on external power on idle maintenance, the demand is now being placed on the battery, and you're using valuable charge cycles when otherwise your phone would be running on external power.

This can *greatly* reduce the lifespan of your battery. Depending on your use patterns and how often you micromanage your phone's power, this can more than *double* the wear on your battery. In short, it could reduce your battery's effective lifespan by *half* of what it should be!

## Don't deep cycle your battery

Nickel Cadmium (NiCd), and to an extent Nickel Metal-Hydride (NiMH) batteries are prone to suffering "Memory Effect." If they were recharged prior to being discharged fully, their capacity would often be permanently reduced. They had to be deep-cycled in order to maintain their health because that was just how their chemistry worked. Nickel Cadmium batteries were prone to requiring manual management and often offered far fewer charge cycles. Back in those days, Nickel Cadmium batteries were more or less ubiquitous because better alternatives did not exist for the average consumer, and that lead to popular advice being to never charge your battery until it was dead.

Nickel Cadmium Batteries are now obsolete and were largely phased out of the market at the end of the 1990's, and Nickel Metal-Hydride batteries aren't going to be far behind thirty years later. Nickel Cadmium batteries were banned in some countries outright roughly a decade ago because they contain large amounts of extremely toxic Cadmium metal.

The last phones to use Nickel Cadmium batteries were car phones, which were large, cumbersome affairs that haven't been produced since the 1980's. Since the 2000's, mobile phones have instead relied on lithium polymer batteries, which are entirely unrelated to the old fashioned Nickel Cadmium batteries and have nothing in common with them chemically. They are an entirely different technology, and must be handled entirely differently; for instance, Nickel Cadmium batteries must be stored completely discharged, but doing the same to a lithium polymer battery will cause the electrolyte in it to crystallize, which will permanently damage a lithium polymer battery.

Likewise, while deep-cycling Nickel Cadmium batteries is necessary for them, this will damage Lithium batteries, often permanently. Newsflash: your Pixel's battery is not a Nickel Cadmium battery, so please don't treat it like one if you want it to last. Don't let your phone's charge get too low, that can very quickly damage it.

## You don't need to slow charge

Popular advice going around has been to slow charge with an older and slower charger rated for less current, to reduce the heat on the battery. This is not necessary; the battery has its own onboard computer that will automatically select the best rate of charging for your battery, and takes into account the current level of the battery, the amount of heat in the handset, and the feedback it gets from the sensors in the battery. If the battery's getting too hot or the battery's own conditions aren't ideal for fast charging, the phone will slow down to preserve the health of the battery.

It's often not spoken of, but Universal Serial Bus is actually an extremely complex protocol, and subsequent generations of it has only increased the amount of complexity it has. USB actually relies on software negotiation between the two devices to determine which device is supplying the power and which device draws it, and then to get the charging the device to supply the correct amount of power that the phone needs at that time. Older, or worse, cheap chargers may not support this properly nor be adequately made to spec. Cheap cables may be insufficiently wired, not have all the necessary wires needing for this, and may not even permit this negotiation to happen at all even on chargers that do.

Not kidding around, but this can lead to *Very Bad Things(tm)* happening, on the list of which are things like short circuits, wrecked batteries, or even lithium fires. This is why we advise using the Google branded charger, and the Google branded cable that came with your phone, which were picked to work with your phone and are known to work with it.

In recent years, induction charging has caught on and is available on the flagship devices, such as the Pixel 3, 4, and 5. There are three advantages to induction or wireless charging: the first is, it saves wear and tear on the small, fragile USB socket being pushed in each night, and pulled out each morning. Mechanically, this is the smallest and weakest spot on your phone and the most likely place where it's going to break from regular use even if you otherwise do everything right. The second advantage to induction charging is that it's convenient and allows for the use of the USB slot while the phone is charging. The last advantage is that induction charging doesn't leave you up the creek without a paddle if all you have is a lightning cable for a device that's USB C, or vice-versa.

## In closing...

To wrap this up, getting the most out of your phone's battery on GrapheneOS is much like getting the most out of GrapheneOS in all other aspects and that the GrapheneOS golden rule applies: *don't try to be a 'power user.'* The devices GrapheneOS supports are thoroughly modern and will manage their own battery health automatically, far better than you ever could manually. They were designed for certain assumptions taking into account certain limitations, and taking into account what most users tend to do. The battery's onboard computer which recieves input from heat sensors and monitors the battery continuously can manage overprovisioning and charge rate to optimize battery health far better than you can with only a percentage that's shown to you by the host.

In the end, feel free to enjoy your phone running Grapheneos knowing that you won't have to get up to hinky charging practices to squeeze a bit more juice out of your battery, and that the Qualcomm SoC and onboard battery computer has your back.

### Addendum
I didn't mention Adaptive Charging, which is new to the Pixel 5. This is because we've felt that it's unnecessary to implement invasive machine learning and habit monitoring to adjust screen brightness and schedule charge times. The phones already include all the standard power management and battery management features, such as going into idle maintenance, slow-charging at higher capacity, intelligent charge throttling, and idle maintenance, which is integrated into the phone's hardware and battery.

---

## Acknowledgment

Thanks and credit to author of this [gist article](https://gist.githubusercontent.com/Peter-Easton/4982f66e93387e02dd2c1d677d71f4f2/raw/4edf9a41ca3a4d053c8ad7bf365f97c923f01c61/battery-management.txt):

```prolog
commit 4edf9a41ca3a4d053c8ad7bf365f97c923f01c61
Author: Peter Easton <Peter@***********.**>
Date: Friday, April 9, 2021
```
### Note

Author of this [gist article](https://gist.githubusercontent.com/Peter-Easton/4982f66e93387e02dd2c1d677d71f4f2/raw/4edf9a41ca3a4d053c8ad7bf365f97c923f01c61/battery-management.txt) is a dear and close friend, [JollyRoger](https://github.com/Peter-Easton/). I do not take any credit for this. I am simply hosting the original Gist as I find it valuable and this makes it easier to share. I've also linked his valuable work in my [resource section](http://akc3n.page/links/#community-driven) for GrapheneOS.

