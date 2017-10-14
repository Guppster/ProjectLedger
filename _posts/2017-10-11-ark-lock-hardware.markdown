---
layout: post
title: "ARK Lock Hardware Setup"
date: "2017-10-11 01:40:30 -0400"
---

In this article I'll be documenting the process of choosing and constructing
hardware to use for my ARK Lock project.

## What is ARK Lock? 

The ARK-Lock project is an effort to use the <a href="http://www.ark.io" target="_blank">ARK blockchain</a> 
to manage a smart deadbolt lock. To see some explanation in to why this is being attempted and high level design visit
the <a href="{{ site.baseurl }}/2017/10/12/ark-lock-project.html" target="_blank">ARK-LockDesign</a> article.

## Major Hardware Required

- **Processing Unit: Raspberry Pi / Arduino**
This could really be anything with wifi and pwm support as the lock module will
need to be able to send HTTP requests and then use the response to control
a servo

- **Hardware to support RFID**
Some chip to support RFID. Most likely a PN532 NFC/RFID Controller 

- **Hardware to support WIFI**
It's ideal to have wifi as this lock wouldn't look great with an ethernet cable
attached to it but this does make the setup process more complex

- **Physical deadbolt and door assembly**
I plan on constructing a small demo-door with the lock and hardware attached.
You can follow the build in the 
<a href="{{ site.baseurl }}/2017/10/12/ark-lock-project.html" target="_blank">SmartLock Demo Door Build article</a> 

- **Servo to control deadbolt mechanism**

- **Enclosure for Lock**
