---
layout: post
title: Air-Powered Soft Robotics
description: Soft Deformable Snake Robot and Simultaneous Pneumatic Actuation Manifold System
image: 
nav-menu: true
---

## Overview
We are designing and constructing a soft snake robot using components such as McKibben muscles and other pneumatic components made from dragonskin and reinforced muscles. The goal is to explore small and inaccessible spaces with a deformable robot that can more easily navigate them.

To support and enable the acuation of this robot, we designed and built a parallelized pneumatic actuation manifold consisting of 5 units each capable of alternating between closed state, open state, vacuum state, and air pressure state with and without power to an air pump. The supporting code is located at https://github.com/ThePenultimatum/softRoboticsProject where I have written a programming interface to the microcontroller so that the states can be changed by referencing sets of valves and states instead of changing special function registers or pins on the microcontroller.

The microcontroller we used is the PIC32. It is on an NU32 board designed and built by faculty and staff at Northwestern University.

[View the project on github here.](https://github.com/ThePenultimatum/softRoboticsProject)

### Team Members
Andrew Thompson, Victor Stepanov, Yuchen Wang, Joel Meyer, Ethan Park