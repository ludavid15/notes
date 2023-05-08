---
layout: post
title: Low Thrust Transfers
permalink: /lowThrust/
excerpt_separator: <!--more-->
mathjax: true
categories: dynamics
---

In general, there is no way to algebraically solve for a low thrust trajectory. Instead, for problems of this type we need to solve for x(t) and u(t) through trajectory optimization. However, this can be a lengthy process, especially if done in a void (i.e without engineering constraints).  

<!--more-->

Nonetheless, we can still make an initial estimate for the delta V cost of a low thrust transfer orbit by assuming that the resulting transfer path is made up of many circular orbits with gradually increasing radius. This applies when the initial and final orbits are circular and transfer time is long. 

$$∆V= \sqrt{\frac{μ}{r_1}}-\sqrt{\frac{μ}{r_2}}$$

### Derivation: 

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