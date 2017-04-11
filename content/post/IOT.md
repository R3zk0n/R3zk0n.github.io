+++
categories = ['IOT', 'exploit']
date = "2017-04-11T20:17:40+10:00"
description = ""
keywords = []
title = "Exploiting IOT Devices"

+++
Lets look into the horrible world of INTERNET OF THINGS!

<!--more-->
<if your reading my source code, you should know why..>

Recently, I have began to look more into Internet Of Things `('IOT')` devices.
These devices are known to horrible security wise, which has been shown multiple ways
including Command Injection flaws on various devices such as televisions, mobile devices, routers, hubs, switchs
and much more

<!-- Make a bigger and better list. -->


- [Command injection on smart TV's](https://www.netsparker.com/blog/web-security/hacking-smart-tv-command-injection)
- [Exploiting OnePlus One via charging cable](https://alephsecurity.com/2017/03/26/oneplus3t-adb-charger/)

A fair few of these devices have low hanging fruit which has not been picked up yet, which means its a good source
to practice and learn new skills.

I began this by attacking a outdated router `NetComm NB16WV-02` This is quite an outdated and no longer supported router from NetComm

I began my attack by reversing enginnering the firmware that was correctly on it, i was able to download the firmware from the NetComm Offical site
this make reversing enginnering it alot easier.

[Router firmware](ftp://ftp.iinet.net.au/pub/iinet/firmware/Netcomm/NB16WV-02)


So i used a tool called [Binwalk](https://github.com/devttys0/binwalk) this tool is great for getting information and getting firmware out of .bin files
```
binwalk dump..
136           0x88            LZMA compressed data, properties: 0x5D, dictionary size: 33554432 bytes, uncompressed size: 3771268 bytes
1249230       0x130FCE        Squashfs filesystem, big endian, version 3.0, size: 8371424 bytes, 1945 inodes, blocksize: 65536 bytes, created: 2014-11-24 06:42:32
9621534       0x92D01E        Squashfs filesystem, big endian, version 3.0, size: 510802 bytes, 329 inodes, blocksize: 65536 bytes, created: 2014-11-24 07:31:47
```
<img src="/blog/images/test.png" alt="Smiley face">
