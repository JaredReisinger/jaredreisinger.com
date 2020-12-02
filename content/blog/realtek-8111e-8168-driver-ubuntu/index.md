---
title: "(Re-)Installing the Realtek 8111e/8168 Driver on Ubuntu"
date: 2020-12-02T13:44:05-07:00
# draft: true
#tile?

# tileImage: https://unsplash.com/photos/40XgDxBfYXM
# tileAttrib: Jordan Harrison

banner:
  enabled: true
# imageRef: <span>Photo by <a href="https://unsplash.com/@jordanharrison?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Jordan Harrison</a> on <a href="https://unsplash.com/s/photos/network?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>
---

_**TL;DR:** Install the `r8168-dkms` package **immediately** once you get your machine on the network._

After upgrading my Ubuntu box to a "new" motherboard and CPU---one that's only 5 years old, instead of 10 years old---I found that it stopped seeing the network. Digging in a little, I discovered that the networking on the newer motherboard used the Realtek 8111E chip, which needs the r8168 kernel driver... and that the r816**9** driver that Ubuntu uses by default _will not work at all_. The combined knowledge of the internet came to the rescue and I found [an updated---as of 2016---guide to installing the r8168 driver](https://tuxbyte.com/how-to-get-your-realtek-rtl8111rtl8168-working-updated-guide/).

Everything was humming along for about two weeks, and then _poof_, that machine stopped seeing the network again.

Back to the internet, and that same guide, but this time I noticed a comment I hadn't before, in the "automatic" way of installing the driver _(**emphasis** added)_:

> After you enable the missing package repository, you will be ready to install
> the driver. This can be easily done with the following command:
>
> ```
> sudo apt-get install r8168-dkms
> ```
>
> The procedure will take some time depending on your CPU, because the driver will be built for your working kernel. The good side is that **if any kernel updates happen on your machine, the driver will be rebuilt against the new kernel automatically after the update because of the use of dkms.**
>
> {{<cite person="tuxbyte" work="How To get your Realtek RTL8111/RTL8168 working (updated guide)" href="https://tuxbyte.com/how-to-get-your-realtek-rtl8111rtl8168-working-updated-guide/" after="(with some small editorial corrections to fix verb tense, etc.)" >}}

I completely passed over this the first time around because I simply _couldn't_ use `apt-get` to install the driver, since `apt-get` itself needed the network! And sure enough, just before the network stopped working, I'd done a `sudo apt upgrade` that had updated the kernel, breaking the previously-built driver.

Running through the manual steps brought the driver and network back online, but this time I _also_ performed the automatic steps afterwards, to ensure that the system now has the automatically-rebuilt `r8168-dkms` package.
