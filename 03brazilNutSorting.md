---
layout: post
title: Swarm Sorting
description: Brazil Nut Effect Sorting Simulation with Kilobots
image: assets/images/brazilNutSim.png
image_alt: Swarm Sorting Simulation Image
nav-menu: true
exclude_from_tiles: false
---

## Overview
Based on the paper located [here](https://dl.acm.org/citation.cfm?id=2343599).
I implemented a sorting by size using the Brazil nut effect in a simulation of a swarm of Kilobot robots (built by Prof. Michael Rubenstein at Northwestern University).

## Implementation

Building off of starter infrastructure written in C for visualizing and instantiating digital instances of kilobots, the simulated kilobots combine psuedorandomness with weak sensing and a simulated directional force (to represent gravity) to perform a size sort.

In the image above, the green and red circles represent robots of different radii. Since the green circles have a coded radius of twice that of the red circles (although not represented visually), they end up over time farther from the central area where the gravitational-like force originates and where the majority of the red circles congregate.

## Resources:

* KiloBot starter code from Dr. Michael Rubenstein
* "[Segregation in Swarms of E-Puck robots Based on the Brazil Nut Effect]"(https://dl.acm.org/citation.cfm?id=2343599)

## Author

* **Mark Dyehouse** -[ThePenultimatum](https://github.com/ThePenultimatum)

## Acknowledgments

* Dr. Michael Rubenstein (Northwestern U.)
