---
title: "Introduction"
description: "Explaination of the Shimmering Bee project, the software and aims."
draft: false
weight: 1
---

## What is Shimmering Bee

Shimmering Bee aims to be a suite of software and libraries which will replace the functionality of devices such as the Phillips Hue bridge or IKEA TRÅDFRI gateway.

The project is initially focusing on Zigbee devices, made available through the Texus Instruments CC253X 2.4Ghz SOC processors. However in the future should be easily expandable to other IOT technologies.

## What can it do?

At the moment early development is underway, much ground work has been done in order to provide a foundation to interact with Zigbee devices. The consume style bridge or gateway does not yet exist, however is due to be started in the near future.

## What makes up the software stack?

The software stack which will make up the bridge/gateway functionality is being written in Go. To a large degree its library structure represents the Zigbee structure.

![Shimmering Bee Controller Stack](/imgs/docs/introduction/controller-stack.png)

### controller

The controller is the Zigbee controller/gateway/hub. It will consume Zigbee events and messages, harmonise those into a standard set of interfaces for devices, and expose them via numerious interfaces. The following interfaces are being considered:

* http/https API
  * **Shimmering Bee**
    To support all potential features, management functions, etc.
  * **Phillips Hue**
    To leverage existing clients and ease adoption.
* secure websocket
  * **Shimmering Bee**
    To support real time communication and changes, likely to mirror http API removing individual connection semantics, simplify authentication and permit push.
* MQTT
  Exposing abstracted devices for interaction with any other home automation systems.

The controller application will be developed with an API first approach, with any native web interface using the APIs.

### zigbee

The `zigbee` library provides standard interfaces and structures for controller to communicate to Zigbee devices. Providing another library uses the same interfaces, supporting Zigbee devices other than the CC253X should be trivial.

### zcl

The `zcl` library is an implementation of some parts of the Zigbee Cluster Library, this is a standarised set of interfaces on Zigbee nodes. This provides a translation layer from bytes from a frame to a easy to use struct.

### zstack

The `zstack` library is the software side of a Zigbee Network Processor, the other being made up of the hardware and firmware on a CC253X coordinator. Specifically `zstack` refers to Texas Instruments implementation. This library handles the logistics around interacting with the Texas Instruments interfaces, providing a clean easy to use interface, as defined in the `zigbee` library.

### unpi

The `unpi` library is a communications library used to communicate with the CC253X SOC, the Unified Network Processor Interface is common to many other Texas Instruments devices.

### bytecodec

The `bytecodec` library provides an easy to use marshal and unmarshal capability converting between struct and byte arrays with ease. 
