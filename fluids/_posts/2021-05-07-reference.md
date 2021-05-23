---
layout: post
title: Miscellaneous Topics
permalink: /misc/
excerpt_separator: <!--more-->
mathjax: true
categories: fluids
---

This is a series of random topics, including non-dimensional numbers and fluid statics.

<!--more-->

## Non-Dimensional Numbers

There’s a whole bunch. Here are the main ones that you might come across. 

#### Reynold’s Number

$$\frac{\rho UL}{\mu}$$	

Ratio of viscous forces to inertia forces. Determines flow regime (Laminar, turbulent, etc.).

#### Mach Number

$$\frac{u}{a}$$

Ratio of flow velocity to speed of sound. The higher the Mach number, the more irreversible the flow becomes.

#### Knudsen Number	

$$\frac{\lambda}{L}$$	

Ratio of molecular mean free path to characteristic length. Determines transition from gas dynamics to continuum mechanics.

#### Prandtl Number	

$$\frac{C_p\mu}{k}$$	

Ratio of momentum diffusivity to thermal diffusivity. In other words, ratio of the dominance of convection to conduction. Also relates momentum vs thermal boundary layers.

#### Stokes Number		

#### Nusselt Number		


## Fluid Statics

Forces always act perpendicular to the surface. Given atmospheric surface pressure (free surface) the pressure at a depth (h) will be:

$$P=\ \gamma h$$

Where $$\gamma$$ is the specific gravity of the liquid, (1 for water). For submerged plate of area, A, total resultant force is equal to:

$$F_r=\gamma h_cA$$

Where hc is the depth of the centroid of the plate. This total force DOES NOT act through the centroid however, instead it acts at through a point where the total moment is equal to zero (center of pressure or can think of this as the centroid of the pressure distribution). If the plate is symmetric, this will coincide with the centroid. 
For curved surfaces, use the following force balance approach: