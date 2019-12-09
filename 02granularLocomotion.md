---
layout: post
title: Robot for Subsurface Granular Material Locomotion
description: Robot with Novel Locomotion Method Inside Granular Materials
image: assets/images/sand.jpg
nav-menu: true
---

## Overview

Granular media are everywhere in the world around us ranging from the sand on beaches to grains in silos and even to the soil we walk on when strolling through a park. Acheiving motion in and on granular media allows us to study the media itself and to reach desired trajectories within the media (such as the shortest path to a deposit of material or information). Some animals and plants have evolved to locomote through sand and soil, growing roots or displacing material in order to reach water, build caverns, and generally travel. Current popular methods of interacting with granualar media to reach goals include drilling and scoop-based displacement digging. Both of these methods have open-mechanical components interacting with the granular media itself. Locomoting through and in a granular media without leaving mechanisms open to the elements   
The goal of this project is to start from theory and prove out, design, build, and test a robot capable of using impulse-based locomotion on and in granular media for three dimensional motion. This impulse-based locomotion is similar in concept to a piledriver and utilizes research on the yield stress of granular materials. Whereas other recent research into digging and locomotion in granular material has focused more on external methods of moving the media in such a way that it is either fluidized or displaced, this project aims to use no external moving parts and rely purely on the impulsed energy from an internal actuator along with buoyant effects in the media.

### Current and Recent Research

#### Surface Motion

In a collaboration between researchers at Carnegie Mellon (Dr. Howie Choset) and Georgia Tech (Dr. Daniel Goldman), a sidewinding snake robot was developed to utilize an animal study in which varying surface contact area in sidewinding snakes enables them to ascend granular slopes.  
Dan Goldman and Dr. Paul Umbanhowar collaborated to produce a robot with flippers taking inspired by the biomechanics of young sea turtles crossing sand to reach the ocean after hatching. A flexible wrist is key in acheiving efficient motion here.  
NASA JPL's hopping hedgehog robot utilizes internal flywheels to jump, roll, and tumble on uneven terrain.  
Dr. Jeffrey Aguilar and Dan Goldman collaborated to produce a hopping robot in a study into the roles actuation phase and frequency of a mass-spring system play in acheiving optimal jumps.

#### Subsurface Motion
Dr. Chen Li et al Studied terradynamics of legged locomotion in and on various granular media, yielding valuable information regarding stresses on objects during penetration and extraction in granular media.  
Dr. Anette Hosoi and her former student Amos Winter developed a digging robot based on razor clam locomotion that utilizes fluidization of the surrounding granular media during and following specific quick movements.  
Stephanie Chang, an MS in Robotics alumnus from Northwestern previously worked with Paul Umbanhowar to develop an auger-based robot for locomotion in granular media.  
Dr. Tilman Spohn and a team of researchers developed and built the HP<sup>3</sup> sensor for the InSight rovor to study temperature fluctuations in the Martian regolith. The device is described as a self-hammering nail and uses an internal impact-based locomotion mechanism with a conical tip on a cylindrical body.

### Feasibility

There are two important parts of the impact and resultant motion to consider.One is the part during which the impactor is still moving toward the chassis andapproximate elastic deformation is occurring.  The chassis reaches a maximum velocity due to the impact and then the second stage takes over.  During thesecond stage, the motion of the entire chassis is governed by the initial maximumvelocity and the pressure applied by the granular material.
From the work done by Chen Li et al in which yield stresses of granular materials were characterized, they found that the yield stress &sigma; linearly increases with depth. Treating the materials in impact as a spring and mass, we can find an acceleration and in turn an impact time.  
&Delta; t<sub>impact</sub> = &radic;(<sup>m<sub>impactor</sub> L<sub>impactor</sub></sup> &frasl; <sub>EA<sub>impactor</sub></sub>)  
Using this time along with the accelerations on the inside and outside of the chassis of the system, we can calculate the expected change in position.  
Performing some test calculations with common and likely materials showed expected changes in position within an order of magnitude of the grain size of common granular materials such as medium-grain sand and poppy seeds. Based on these sample calculations, building out prototypes to test the understanding of the impacts and accelerations the chassis will undergo is beneficial to a design of the whole robot.
  
The technical documents with relevant derivations and theory are available for viewing on Overleaf at this [link](https://www.overleaf.com/read/srybycnmcjgs).

### Impact Mechanisms

#### Solenoid-based

Given that the desired effect is one surface repeatedly linearly impacting another surface which is the chassis of the robot in the direction of travel, one clear option is a solenoid-based impact mechanism. Current in a coil then accelerates a plunger along the access of its magnetic field inside the coil until the plunger impacts or reaches its stroke length. This can be repeatedly actuated in such a way. The resultant motion is a function of current since that is the driving factor in the magnetic field that accelerates the plunger before it impacts the surface. The limitations here are the current and volage limits in the circuit which depend on the specific solenoid actuator and other components in the circuit.

Pros:
* Linear actuation
* Frictionless plunger movement unless off axis forces applied to shaft
* Force modulated by current  
  
Cons:
* Limited to pre-existing plunger impact surface without special modifications
* Low mass impacter while momentum of the impacter is a key factor in theoretical distance traveled

##### Prototype

![Front View of Prototype with Solenoid Actuator](assets/images/solenoidPrototypeUpright.png)
![Top View of Prototype with Solenoid Actuator](assets/images/solenoidPrototypeTop.png)
![Solenoid Actuator](assets/images/solenoid.png)

#### Gear and Motor Planar System

Another option is utilizing a gearing system with a custom tooth set to store potential energy in a spring and use the release to impact a surface with either a custom tooth or an attachment to the gear at the end of the motor-gear system. The system here is limited by its shape since gearing up from the motor to a gear-based impactor has impact forces increasing with the radii of the gear at the end of the connected system. Despite its limitations, it shows that the forces desired in the system can be acheived using the combination of a small motor and physical gear-based impactors.

Pros:
* Rapid prototype iteration
* Impacter path is a nonlinear curve  
  
Cons:
* More than 1-D motion requires intersecting planar mechanisms

##### Prototype
![Side View](assets/images/portraitPlanarGears.png)
![Bottom View for Visibility](assets/images/bottomViewPlanarGears.png)

#### Cylindrical Rotational-to-Linear System

Building on the previous prototypes and ideas, the third prototype uses a motor to transform rotational motion into linear motion to store energy in a spring. Then, the release can be utilized to impact a surface with a component along the spring's axis of compression.

Pros:
* Motor naturally co-axial with impacter
* High impacter surface area to outside chassis surface area ratio  
  
Cons:
* Still need intersecting linear mechanisms for more than 1-D motion

##### Prototype
![Whole Helical Prototype](assets/images/helicalCylinderWhole.png)

### Chosen Design

Given the benefits of having a motor co-axial with the impacter and those of having a low volume to output force ratio with the rotational-to-linear cylindrical impacter system, this became the chosen testbed for further exploration.

#### Components

![Deconstructed Prototype](assets/images/deconstructedGranularRobot.png)

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
* Resistors ( m&Omega;)
* Capacitors ( &mu;F)
* Power Supply
* Bolts ( list size here )
* Nuts ( list size here )

#### Electronics

##### Circuit Diagram
![NU32 IC, Motor Driver, and One Motor](assets/images/circuitDiagramGranularNoSensor.png)

#### Limitations

##### Requirements for Motion:  

In order to move, the stress created by the impact force must be greater than the yield stress (&sigma;) on the surface of the robot in the direction of travel.  

Using the momenta in the system, we can manipulate the equations of motion in order to get an upper bound on depth as a function of the robot geometry, position, and materials.

d &le; <sup>1</sup>&frasl;<sub>&sigma; &pi; r<sub>body</sub><sup>2</sup></sub>  [<sup>E A<sub>impactor</sub> k &Delta; x<sub>compression</sub><sup>2</sup></sup>&frasl;<sub>L<sub>impactor</sub></sub>]<sup>&frac12;</sup> + &frac12; h<sub>body</sub> cos(&theta;)  

Where d represents depth below the surface of the granular material, E is the Young's modulus of the impacter, theta is the angle the body of the robot makes with the z-axis of the world frame, and k represents the spring constant of the spring used.

Discuss the limitations given angles and rises on the helix:
THIS IS THE IMPORTANT PART FROM MY WHITEBOARD CALCULATIONS
The kinetic energy the impactor has depends on how much of the potential energy stored in the spring can be imparted onto the impactor. Since the spring imparts a force during decompression on both the impactor and the chassis in opposite directions, that means that the maximum energy is transferred to the impactor when the chassis is immobilized by forces that will keep it stationary during that decompression. The important part is to make sure that the impactor has enough momentum to allow the yield stress of the granular material in the direction of actuation to be exceeded. 

### Experiments and Characterization

![Diagonal Up Demonstration](assets/images/diagUpPoppy.gif)

#### Impact Force Experiment

##### What This Means

#### Motion Experiments

##### Horizontal Motion, No Additional Mass

![Horizontal, No Additional Mass Demonstration](assets/images/horizNoMass.gif)

###### What This Means

##### Vertical Motion (Up), No Additional Mass

![Vertical, No Additional Mass Demonstration](assets/images/vertNoMass.gif)

###### What This Means

##### Horizontal Motion, Additional Mass

![Horizontal, Additional Mass Demonstration](assets/images/horizMass.gif)

###### What This Means

##### Vertical Motion (Up), Additional Mass

![Vertical, Additional Mass Demonstration](assets/images/vertMass.gif)

###### What This Means

### Discussion

Discuss.

### Next Steps

* Sensorization
* 3-D actuation design (as opposed to current 1-D)
* Construction from metal
* Control based on sensor data and/or pre-calculated trajectories
* Variable speed
* Explore internal center of mass shifting for orientation
* Explore various impact per second speeds and examine behavior as fluidization time grows

Currently in development is a multidirectional version of this robot which aims to utilize several actuators of the actuators used in the cylindrical robot simultaneously. In addition, a mount for an IMU sensor and the PCB is under development, and an interesting expansion would be exploring control using that sensor data. More robust development of the system using machined parts would also allow for more robust studying of the robot behavior in varying granular material conditions. Beyond this, an on-board battery supply system would allow the robot to be untethered. Battery supply has been tested for the motor itself, but power for the control board is still tethered at the moment.

## Acknowledgements

Many thanks to my adviser, Dr. Paul Umbanhowar (Northwestern U.), for his insightful discussions and support throughout this project. I also want to thank Dr. Matt Elwin and Bill Hunt (also at Northwestern) for their encouragement and advice along the way. This project would not have been possible without them and the support of the MS in Robotics program at Northwestern.