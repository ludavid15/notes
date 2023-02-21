---
layout: post
title: Astrodynamics
permalink: /astrodynamics/
excerpt_separator: <!--more-->
mathjax: true
categories: dynamics
---

Astrodynamics is a lot like any other field of dynamics, except we now have an additional equation to consider: the law of universal gravitation. This leads to some strange and counterintuitive results - like slowing down to catch up! 

<!--more-->

### Kepler’s Laws of Planetary Motion

As good a place to start as any. These are more a set of observations than a theoretical explanation for celestial motion.

1.	All planets move in elliptical orbits, with the Sun at the focus.
2.	A line that connects a planet to the Sun sweeps out equal areas in equal times.
3.	The period of an orbit is proportional to the root of the cube of the semimajor axis.

### 2D Orbits

The two-dimensional orbital frame is also known as the perifocal frame (i.e. periapsis and apoapsis vectors are in the plane). We also assume that one body is significantly larger than the other. Given θ as the true anomaly of your orbit, orbital radius from a focus point is:

$$r=\ \frac{h^2}{\mu}\frac{1}{1+e\cos(\theta)}$$

Where µ is the gravitational parameter of the larger body being orbited. Standard values for objects in our solar system can be found [here](https://en.wikipedia.org/wiki/Standard_gravitational_parameter).

For each orbit, we can also define the specific angular momentum $$\vec{h}$$:

$$\vec{h}=\vec{r}\times\vec{v}$$

Where $$\vec{r}$$ and $$\vec{v}$$ are the position vector and velocity vector at a point in time. The total angular momentum remains constant through the orbit. If the orbit is elliptical, we can define an apoapsis distance, periapsis distance, and semimajor axis distance.

$$2a=\ r_a+r_p$$

The eccentricity (measure of how elliptical an orbit is) can also be calculated with:

$$e=\ \frac{r_a-r_p}{r_a+r_p}$$

Through conservation of energy we arrive at the Vis-Viva equation. An orbit with a specific energy of zero is defined to be on a parabolic orbit. A positive specific energy means that it is on an escape trajectory, while a negative value means it is captured by the planet’s gravity (circular or elliptical). 

### Vis Viva Equation

This equation relates the current velocity and radius of an object in orbit to the total energy, or semi-major axis of it's orbit. This is very useful for computing Hohman transfers.

$$\frac{v^2}{2}-\frac{\mu}{r}=-\frac{\mu}{2a}=\varepsilon$$

### Orbital Period

The orbital period is the total time is takes to complete a single revolution

$$\left(T\right)=2\pi\sqrt{\frac{a^3}{\mu}}$$

Using the energy equation, we can show that for a circular orbit, where r = a, the circular orbit velocity is simply:

$$V=\ \sqrt{\frac{\mu}{r_1}}$$


### Low Thrust Transfers

In general, there is no way to algebraically solve for a low thrust trajectory. Instead, for problems of this type we need to solve for x(t) and u(t) through trajectory optimization. 

An initial estimate for the delta V cost of a low thrust transfer orbit can be obtained by assuming that the resulting transfer path is made up of many circular orbits with gradually increasing radius. This applies when the initial and final orbits are circular and transfer time is long. 

$$∆V= \sqrt{\frac{μ}{r_1}}-\sqrt{\frac{μ}{r_2}}$$

Derivation: 

We start with Newton’s first law, relating forces to acceleration.

$$m\frac{d\vec{V}}{dt}=\vec{T}-\frac{\mu m}{r^3}\vec{r}$$

We assume T is aligned with velocity. Both sides of the expression are dotted with V.

$$\vec{V}\bullet\left(m\frac{d\vec{V}}{dt}\right)=\vec{V}\bullet\left(T\ast\hat{V}-\frac{\mu m}{r^3}\vec{r}\right)$$

$$\frac{1}{2}\frac{d}{dt}V^2=\frac{T}{m}\vec{V}-\frac{1}{2}\frac{\mu}{r^2}\frac{d}{dt}r^2$$

We re-write the thrust in terms of the mass flow rate and the exhaust velocity and integrate.

$$T=\ \dot{m}U_{ex}$$

$$\frac{d\vec{V}}{dt}=-\frac{d}{dt}\ln{\left(m\right)}U_{ex}-\frac{\mu}{r^2}\frac{dr}{dt}\frac{1}{V}$$

$$∆V=-U_{ex}ln\frac{m_f}{m_o}-\int_{t_o}^{t_f}\frac{μ}{r^2}\frac{dr}{dt}\frac{1}{V}dt$$

With a circular approximation, we can substitute the magnitude of velocity in with the radius.

$$V=\sqrt{\frac{\mu}{r}}$$

Integrating the “gravity drag” term from inner radius to outer radius yields the circular transfer approximation equation. 

For short transfers, low thrust trajectories result in a much higher time of flight, but as the transfer distance increases, EP transfer times become better than traditional impulsive options, due to a higher achieved maximum velocity from long periods of sustained thrust.


### Lagrange Points

A lagrange point is a stable orbit position where the gravitional pull and centrifugal force from two other bodies is at an equilibrium. In a three-body system, there are 5 lagrange points. 

> The James Webb Space Telescope is at the Earth-Sun Lagrange point L2!