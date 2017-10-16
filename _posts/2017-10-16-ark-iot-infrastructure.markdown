---
layout: post
title: "ARK IoT Infrastructure"
date: "2017-10-16 09:31:02 -0400"
---

This article will outline a set of software that creates an architecture 
for quick development and smooth operation of IoT applications on the ARK blockchain.

## Components
The three products that will compose the architecture are

- Ark IoT Hub
- Ark IoT Controller
- Ark IoT Module

### Ark IoT Hub

This piece of software is responsible for abstracting the non-essential logic from the IoT modules. Things like signing transactions and
polling for new transactions in an account. This hub device or software will need to be active on the network before IoT modules are activated so they can register with the hub and start using its functionality. I think this is an appropriate approach because other successful smart home items like Philips Hue smart bulbs also require a "Hub" to be running on the network for bulbs to be connected. The hub will abstract away all non-essential blockchain logic so the IoT developer can focus on functional code for their device.

Some basic functionality the Hub will offer IoT modules:

- Sending a message to another address
In this case the message will be put in the vendor field of the transaction that has a token value assigned when initializing the Hub
- Fetching the last transaction received on its own address

Although these may seem like simple tasks that any client should be able to accomplish itself, we cannot assume IoT will support any kind of external crypto libraries and this is stuff the developer shouldn't have to think about when writing code for hardware. This is just the beginning of functionality that we can centralize within a local network of IoT devices to simplify the process of bringing more devices onto the blockchain.

Since these hub devices will be universal and not store any state, you would be able to install them in large networks and scale them easily because all they do is handle processing of transactions for IoT-Modules (for now)

The Hub will host an API with endpoints for each of these tasks because at the very least we can assume an IoT device can connect to the internet, create a JSON structure, and send an HTTP request. 

### Ark IoT Controller

The IoT controller is a way to monitor and interact with any Ark Blockchain connected IoT device that follows this specified architecture. The controller will be in the form of a mobile application and provide the user a Plug-and-Play process from the point of receiving an IoT device to where they can execute actions on the hardware.

The controller app provides the following functionality:

- Ability to register a new IoT device 
- Assume and give away ownership of a device
- Fetch interaction history for a specific device
- Fetch available interaction from an IoT-Module and display them as buttons
- Execute a specified action on a specified device

### Ark IoT Module

The Ark IoT Module is a specification IoT devices should follow to be accepted into the Ark Iot-Hub ecosystem. The strict adherence to this protocol allows the rest of the architecture to function smoothly. 

The requirements for an IoT-Module are:

- Look for an IoT-Hub on initialization
- Only accept interaction transactions that come from the current owner's address
- Initialize its own account with a transaction that has comma separated strings where each string represents an interaction that can be executed on this hardware

The initialization phase will most likely be conducted during manufacturing of the device. Many of these aspects will be extracted into the IoT-Hub's functionality but ultimately the hardware will be responsible for its own Ark account.

### Senario #1

In this scenario I will demonstrate what I imagine the user experience being when purchasing and operating an Ark-IoT device

1. User buys an Ark IoT-Hub and attaches it to their network
2. User buys an Ark IoT-Module and installs it (for this example lets assume a lock
3. User downloads the Ark IoT-Controller App
4. User enters the address and password located on IoT-Module package into the App
5. App fetches account history/transactions
6. App scans transactions looking for an "owner:[address]" vendor field
7. If an owner isn't found App prompts to send transaction and take ownership, else verify ownership.
8. App scans Module's initialization transaction's vendor field and parses available interactions
9. App displays interactions and the user can select one to execute it (in this example: lock/unlock)

### Senario #2

This scenario is from the perspective of the IoT-Module just for further clarification

1. IoT-Module is connected to the network
2. Looks for an Ark IoT-Hub, blocks until it can find one and register
3. Checks for any new transactions on its account by issuing HTTP requests
4. Verifies transaction is from its owner
5. Executes vendor field interaction
6. Waits for more commands

