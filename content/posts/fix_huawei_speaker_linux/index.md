---
title: Huawei Laptops not playing sound from speakers on Linux
date: 2024-01-20T01:58:21+03:30
featured: false
draft: false
comment: false
toc: true
reward: false
pinned: false
carousel: false
series: 
categories:
  - Linux
tags:
  - linux
  - Problems
images: 
keywords:
  - huawei speaker fix
  - huawei laptop speaker problem on linux
  - linux huawei no audio
  - linux no audio
---

# No audio from device when switching to Linux on Huawei laptops

Huawei laptops actually have many problems with linux. From fingerprint of the device not working to MANY audio problems. Fortunately this one has a fix.

 **Solution:**
 
*Note : This fix is tested on hauwei b3-520 laptop but will probably work on all huawei laptops.*
The solution is to completely switch from Pipewire to Pulseaudio. So my distro is arch-based so I did `yay -R "anything related to pipewire` and after I removed all those packages, I installed pulseaudio alternative to everything I removed. I started with `sudo pacman -S alsa-utils pulseaudio pavucontrol` and continued installing everything from the pipewire that I removed. So if I had `pipewire-jack` I installed `pulseaudio-jack` instead.
This fixed my audio problem with the speakers.

**Huawei not releasing drivers for audio and many other things.**

So although this fixes the speakers problem. I still can't use audio jack of the device. Connecting any headphones to it will result in audio both playing from the headphones and the speakers.
And based on all the research I did, this problem has been here for a while, and is likely to never be fixed.
