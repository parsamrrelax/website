---
# type: docs 
title: Video edtiors problems with footages on external hard drives
date: 2023-10-31T20:49:09+03:30
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
  - Video Editors
  - Problems
images: []
keywords:
  - UDF drives on windows
  - APFS on windows
  - HFS on windows
  - NTFS on Mac
  - video edtior problem
---

  

# External drives are not recogonized either on Windows or MacOS


To better understand why this problem happens we must first understand some basic terms.

## File systems:

File systems are methods that data is stored and retrieved on operating systems. Now this is not a clear explanation if you're not familiar with computing and not tech savvy in general. So let's explain it better.
Basically every operating system (Windows, MacOS, Linux, ...) chooses a variety of file systems to support. This means that each of these operating systems can write and read information in those file system types. 

## Where is the problem in this?

The problem begins when one of these file systems are exclusive to one operating system and you format your hard drive to one of these proprietary ones, then it can not be read in other operating systems.

## Different file systems:

There are many popular filesystems around including NTFS,  FAT32, ExFat, Btrfs and many more. 
NTFS is a propriety file system developed by Microsoft and is exclusive for Windows.
APFS is a propriety file system developed by Apple and is exclusive for MacOS.
HFS and HFS+ are propriety file systems developed by Apple and are exclusive for MacOS.
Above are the known propriety file systems that I know of but these are the most popular ones.
There are some general file systems that almost all operating systems support.
One of the most popular ones in this category is FAT32. Basically everything supports FAT32. *But it has a file size limit of 4GBs* , meaning you can't store files larger than 4GB on drives that have this file system.

## What is the best format for compatibility

You should always format your drives to **exFAT**. That's it. It is supported in Windows, MacOS, and Linux. I have tested this myself.
*So if you're a video editor use exFAT. So you can have cross platform compatibility.*

## What if I can't format my drive now and want access to my files on one of these operating systems?

Say someone copied the footage to your drive and you want to copy the footage in your machine before formatting it. Let's see the solution.

### Windows:

If your operating system is Windows and your drive was working on a Mac but not showing up on your Windows machine.
First check if this is actually a file system issue and not a drive problem. The drive should be powered on, and you should be able to unmount it from the taskbar. If you right click on the Windows start and check disk management, you should see that your external drive is recognized but the file system in not shown like your internal drive which is generally NTFS.
So if it was like this it is probably in APFS or HFS and you need third party software to access it.

Paragon software company has some great products for this issue
Download their software for this issue from their website:

[HFS for Windows](https://www.paragon-software.com/home/hfs-windows/#)

[APFS for Windows](https://www.paragon-software.com/home/apfs-windows/#)

Download these programs and install them. You will see your drive recognized in one of them and mounted as a normal drive from now on. But remember to don't rely heavily on these softwares and format your drive to exFAT after you're done.

### MacOS:

If your operating system is MacOS and your drive was working on a Windows PC but not showing up on your Mac.
First check if this is actually a file system issue and not a drive problem. Do this by running the disk utility app and check if your drive is recognized. If it was and you know it was working on a Windows PC, the drive is probably in NTFS format and you'll need a workaround to make it work.

You can use third party software for this for example from [Paragon](https://www.paragon-software.com/home/ntfs-mac/) but I recommend that you do it from terminal yourself. This is a bit advanced but more reliable and free.

- Open Terminal
- Type this command and press return and enter your password after that
```bash
sudo nano /etc/fstab
```
- Replace "NAME" in this command with your drive name and press return
	*If your drive contains spaces in it's name you should enter them as \040*
```
LABEL=NAME none ntfs rw, auto, nobrowse
```
- Press Control + O then Control + X on Mac keyboard.
-  In Finder, click Go then go to Folder then type: **/Volumes**, and click "Go".
You can now access your drive from here.

