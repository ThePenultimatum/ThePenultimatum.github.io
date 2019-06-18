---
layout: post
title: DIY Localization Sensor Network
description: DIY Microcontroller Ultrasonic Sensor Network for Trilateration and Localization
image: assets/images/angleFans1.JPG
nav-menu: true
---

## Overview
This project aims to use HC-SR04 ultrasonic sensors in conjunction with NU32 boards using PIC32 microcontrollers and XBee radio tranceivers in a sensor network for localization of a mobile robot. The goal is to allow the mobile robot to navigate a simple space in limited sensor circumstances.

The ultrasonic sensors are hooked up and receive a >=5 millisecond pulse of 5V from the PIC32, and then the returned signal is timed for a time of flight distance measurement. This is done by all nodes in the network, and they transmit their measurements in AT mode to a central node. This central node aggregates and processes the distances for trilateration of an object in the network's measurement area. This object can be a mobile robot enabled with an XBee RF module which receives a measure which it can then minimize toward a known goal location within the network. Instead of using UART3 to send data to a computer, this would require sending data back over UART2 to the XBee radio tranceiver directly to the XBee on the mobile robot.

The project along with a deeper explanation, videos, and a how-to guide on how I built and developed the project (and its ongoing developments) can be viewed [here](https://github.com/ThePenultimatum/mdyehouseWinterProject)