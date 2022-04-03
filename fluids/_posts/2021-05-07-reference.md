---
layout: post
title: Non-Dimensional Numbers
permalink: /misc/
excerpt_separator: <!--more-->
mathjax: true
categories: fluids
---

Non-dimensional simply means unitless. Why unitless? Because we're taking the ratio of two similar properties and comparing their relative magnitude. 

There’s a whole bunch of these, but here are the main ones that you might come across. 

<!--more-->

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

Ratio of momentum diffusivity to thermal diffusivity. This number relates the size of momentum to thermal boundary layers, or the ratio of convection to conduction. 

#### Nusselt Number		

$$\frac{hL}{k}$$

Ratio of convective to conductive heat transfer. Since a fluid's speed affects the convection coefficient, the Nusselt Number is very similar to the Prandtl number.


#### Stokes Number	

$$\frac{t_0 u_0}{l_0}$$

Ratio of the characteristic time of a particle to a characteristic time of the flow. In other words, the effect of drag on a particle's motion. On on extreme a particle's motion follows the fluid streamlines and on the other extreme, it continues on its original trajectory. 



## Fluid Statics

Forces always act perpendicular to the surface. Given atmospheric surface pressure (free surface) the pressure at a depth (h) will be:

$$P=\ \gamma h$$

Where $$\gamma$$ is the specific gravity of the liquid, (1 for water). For submerged plate of area, A, total resultant force is equal to:

$$F_r=\gamma h_cA$$

Where hc is the depth of the centroid of the plate. This total force DOES NOT act through the centroid however, instead it acts at through a point where the total moment is equal to zero (center of pressure or can think of this as the centroid of the pressure distribution). If the plate is symmetric, this will coincide with the centroid. 
For curved surfaces, use the following force balance approach: