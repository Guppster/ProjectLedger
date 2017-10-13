---
layout: post
title: "Ark Lock Project"
date: "2017-10-12 23:44:33 +0000"
---

Creating a smart lock on the ARK blockchain while developing IoT infrastructure.

## The Goal

The main goal of this project is to make the ARK blockchain more accessible to
IoT devices. With a growing amount of ARK libraries avaliable for all the
popular languages it is still difficult to start an IoT project that interacts
with the ARK blockchain. Therefore, I decided to create the first IoT based
project to highlight the difficulties and create infrastructure along the way to
make it easier for others.

## The Plan

I decided to make a smart lock. A lock that will monitor the blockchain for
commands on what it should be doing and also use the blockchain to create
a public record of ownership and activity. 

## Requirements

There are three sections to this project, the user facing software, the software running the lock, and the hardware itself. Below i have written down what I think are the minimal working requirements for this project to be a success.

### User Software

#### Mobile app / Webpage

* Be able to identify a new hardware lock by using it's assigned address
* Can add or relate accounts that are allowed to operate the lock
* Can display interactions with the lock

### Lock Software 

#### Running on ARM host or Arduino itself

* Able to operate the hardware when an approved address sends a transaction to it 
* Identifies the action (lock/unlock) via the vendor field

### Lock Hardware 

#### Servo operating deadbolt assembly

* Be able to control a pre-existing deadbolt assembly
* Independently powered and able to connect to the internet in a small footprint
* Create a latch to control the deadbolt

## Flow Diagram

<amp-img width="810" height="770" layout="responsive" src="{{ site.baseurl }}/assets/images/ArkLockFlowDiagram.png" alt="Flow Diagram"></amp-img> _How I imagine the lock operating_
