---
# type: docs 
title: CFast cards not working in Windows
date: 2023-10-31T22:44:26+03:30
featured: false
draft: false
comment: false
toc: true
reward: false
pinned: false
carousel: false
series:
categories:
  - Windows
  - Mac
  - Problems
  - Video Editors
tags:
  - Windows
  - Mac
  - Problems
  - Video Editors
images: []
keywords:
  - Cfast on windows
  - arri cfast windows
  - cf card reader windows
  - cf not working on windows
  - udf device not working on windows
---


# CF cards only working on MacOS

If you're a video editor working with footage from Alexa Minis or Alexa LFs, you have probably heard this sentence before. CF cards only work on Mac.
This is simply **not true** and we'll go through what is the problem here.

## Connection Ports
These CF drives are extremely fast drives and therefore require require fast ports to be connected to. Arri suggest using Thunderbolt 3 at least for CFast 2.0 cards which are the newer ones typically by the AngelBird Company. But if your Cfast card reader has a normal USB instead of USB type C, you should use USB 3.2 Gen 2x2 or 2x1 (very confusing naming). So search for your laptop model or for your motherboard model on the web and see if it has those ports to get the most out of your Cfast. However if there is power being delivered to your CFast card reader then your usb generation should only affect your speed not it working or not. (except for Thunderbolt 2 and USB 2 ports which can't deliver power to CFast 2.0 cards at all.)

## UDF formatting
These CF cards or CFast cards are UDF formatted. These drives are well supported on Mac and were supported on Windows 10 and Windows 11 at one time. However an "update" for Windows apparently broke this feature on Windows and it's being solved for the past 2 years.
### What can you do in this case?

This is temporary solution and  the main fix will come from Microsoft, but you should rollback your updates to a point which it was before this update from Microsoft.
To this search for rolling back updates on the web or on your windows search and you'll see what you should do.
However rolling back updates means rolling back security updates as well, Which is not recommended. but if you have to you have to.

### The advanced solution for Windows 10

What the update broke is a file called partmgr.sys located in C:/Windows/system32/drivers/:

- Take a backup of that file (add a .back to the end of the file name).
- Download [this file](https://github.com/parsamrrelax/partmgr.sys/releases/download/partmgr/partmgr.sys) and put it in the same directory.
	- Replace the old version if it asks you to.
- Change the permission of the file to administrator from the properties.
- Reboot

*Note that every Windows Update breaks this function again and you should repeat the process*
