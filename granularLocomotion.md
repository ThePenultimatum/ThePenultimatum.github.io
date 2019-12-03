---
layout: post
title: Robot for Subsurface Granular Material Locomotion
description: Robot with Novel Locomotion Method Inside Granular Materials
image: assets/images/sand.jpg
nav-menu: true
---

## Overview

The goal of this project is to start from theory and prove out, design, build, and test a robot capable of using impulse-based locomotion on and in granular media. This impulse-based locomotion is similar in concept to a piledriver and utilizes research on the yield stress of granular materials. Whereas other recent research into digging and locomotion in granular material has focused more on external methods of moving the media in such a way that it is either fluidized or displaced, this project aims to use no external moving parts and rely purely on the impulsed energy from an internal actuator along with potential utilization of buoyant effects in the media.

### Current and Recent Research

#### Motion on the surface

* Goldman mass-spring jumping
* Sidewinder snake robot GA Tech and CMU
* Sea turtle flippers Umbanhowar and Goldman
* JPL hopping hedge-hog 

#### Subsurface Motion
* Chen Li legged robotics, yield stress 
* Stephanie Chang MSR auger robot with Dr. Umbanhowar
* MIT razor clam

### Feasibility

The technical documents with relevant derivations and theory (in progress) are available for viewing on overleaf at this [link](https://www.overleaf.com/read/srybycnmcjgs).

### Impact Mechanisms

#### Solenoid-based

Given that the desired effect is one surface repeatedly linearly impacting another surface which is the chassis of the robot in the direction of travel, one clear option is a solenoid-based impact mechanism. Current in a coil then accelerates a plunger along the access of its magnetic field inside the coil until the plunger impacts or reaches its stroke length. This can be repeatedly actuated in such a way.

Pros:
* Linear actuation
* Frictionless plunger movement unless off axis forces applied to it
* Force modulated by current
Cons:
* Limited to pre-existing plunger impact surface
* Low mass impacter while momentum of the impacter is a key factor in theoretical distance traveled

##### Prototype

![Front View of Prototype with Solenoid Actuator](assets/images/solenoidPrototypeUpright.png)
![Top View of Prototype with Solenoid Actuator](assets/images/solenoidPrototypeTop.png)
![Solenoid Actuator(assets/images/solenoid.png)

#### Gear and Motor Planar System

Another option is utilizing a gearing system with a custom tooth set to store potential energy in a spring and use the release to impact a surface with either a custom tooth or an attachment to the gear at the end of the motor-gear system.

Pros:
* Rapid prototype iteration
* Impacter path is a nonlinear curve
Cons:
* More than 1-D motion requires intersecting planar mechanisms

##### Prototype

#### Cylindrical Rotational-to-Linear System

A third option is utilizing a motor to transform rotational motion into linear motion to store energy in a spring. Then, the release can be utilized to impact a surface with a component along the spring's axis of compression.

Pros:
* Motor naturally co-axial with impacter
* High impacter surface area to outside chassis surface area ratio
Cons:
* Still need intersecting linear mechanisms for more than 1-D motion

##### Prototype

### Chosen Design

#### Components

* Motor Casing
* Chassis With Slots
* Slider Mechanism
* Motor Spacer
* Helix Rotator
* Spring Spacer
* Spring
* Motor
* NU32 PCB
* 1 or more Breadboards
* Motor Driver
* Resistors ( mO)
* Capacitors ( mF)
* Power Supply
* Bolts ( list size here )
* Nuts ( list size here )

#### Electronics and Code

##### Circuit Diagram
![NU32 IC, Motor Driver, and One Motor](assets/images/circuitDiagramGranularNoSensor.png)

#### Limitations

describe limitations based on equations first

then limitations based on materials and speed

current board only handles 5 max PWM signals. I can use an IO expander to extend this and use one signal for multiples with a default to low (0% pwm)

### Experiments and Characterization

#### Impact Force Experiment

##### What This Means

#### Motion Experiment

##### What This Means

### Next Steps

idea for variable height of lifts using some screwing method with a motor

use accelerometer data during impacts to get info useful for control

## Acknowledgements

Many thanks to my adviser, Dr. Paul Umbanhowar (Northwestern U.), for his insightful discussions and support throughout this project. I also want to thank Dr. Matt Elwin and Bill Hunt (also at Northwestern) for their encouragement and advice along the way. This project would not have been possible without them and the support of the MS in Robotics program at Northwestern.