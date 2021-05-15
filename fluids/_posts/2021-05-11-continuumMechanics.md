---
layout: post
title: Continuum Mechanics
permalink: /continuumMechanics/
excerpt_separator: <!--more-->
mathjax: true
---

One of the common assumptions we make when working with fluids is that it forms a continuum. The individual atoms of a fluid are assumed to be tightly packed enough that we can approximate the collective molecular interactions. What are these collective molecular interactions? Well, pretty standard stuff actually. We assume that applying a force causes an object to move, or a body to deform. (Technically speaking, that stress is related to strain). And honestly well, that's kinda it. 

The reason this assumption is so powerful is because it makes our model **continuous**. This may seem pretty obvious at a glance, but working with stuff that is continuous is very different from working with stuff that is discrete! The reason as you may already have guessed: derivatives. 

<!--more-->

Alright, so what can we do with continuums? Well, how about mass, momentum, and energy conservation? Sure enough. There are two ways to do this: with either a **control mass** or **control volume**. 

### Conservation of Mass

Also known as continuity. Time rate of change of mass in the control volume (CV) is equal to the mass flux through the boundary. Or, in differential form, partial derivative of density plus mass flux is zero.

* Integral

$$\frac{\partial}{\partial t}\iiint\rho dV=-\oiint{\rho\mathbit{u}\bullet\hat{\mathbit{n}}dA}$$

* Conservative

$$\frac{\partial\rho}{\partial t}+\nabla\bullet\left(\rho\mathbit{u}\right)=0$$

* Non-conservative
$$\frac{D\rho}{Dt}+\nabla\bullet\left(\rho\mathbit{u}\right)=0$$

For (quasi) 1-dimensional steady flow, the mass flow rate can be expressed as the following:

$$\dot{m}=\rho AV$$

For 2D incompressible flow, we need to account for the velocity in two directions. In this case continuity can be expressed as:

$$\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}=0$$

### Conservation of Momentum

Time rate of change of momentum in the CV is equal to the advection term plus forces. Or in differential form, partial of momentum with respect to time plus advection term is equal to forces acting on the fluid element. Note that the right side of the equation is the substantial derivative. You may recognize these as the Navier-Stokes equations. Or another way of thinking about it, the Navier-Stokes equations are just a statement momentum conservation.

* Integral

$$\frac{\partial}{\partial t}\iiint\rho udV=-\oiint\mathbit{u}\left(\rho\mathbit{u}\bullet\hat{\mathbit{n}}\right)dA-\oiint\left(P\hat{\mathbit{n}}\right)dA$$

* Conservative

$$\frac{\partial\rho\mathbit{u}}{\partial t}+\left(\nabla\bullet\rho\mathbit{u}\right)\mathbit{u}=-\nabla P+\rho g+\nabla\tau+\mathbit{F}_{\mathbit{body}}$$

* Non-conservative

$$\rho\frac{D\mathbit{u}}{Dt}=-\nabla P+\rho g+\nabla\tau+\mathbit{F}_{\mathbit{body}}$$

### Conservation of Energy

Time rate of change is equal to advection term plus heat (both volumetrically and through the surface). Note that work done is encapsulated in the P/rho term in the advection integral. Or, the substantial derivative of total enthalpy is equal to time rate of change of pressure (work) and flux of heat. This is also a statement of the 1st law of thermodynamics. (Conservation of Energy).

* Integral

$$\frac{\partial}{\partial t}\iiint{\rho(e+\frac{1}{2}U^2)dV}=-\oiint{\rho\left(e+\frac{P}{\rho}+\frac{1}{2}U^2\right)\mathbit{u}\bullet\hat{\mathbit{n}}dA}+\iiint{\rho\dot{q}dV}-\oiint{\dot{q}^n\bullet\hat{\mathbit{n}}dA}$$

* Conservative

$$\frac{\partial\rho e}{\partial t}+\nabla\bullet\left(\mathbit{u}(\rho e+P)\right)=0$$

* Non-Conservative

$$\rho\frac{Dh_o}{Dt}=\frac{\partial P}{\partial t}+\rho\dot{q}$$

### Conservative vs Non-conservative Form

Conservative equations are valid over discontinuities in the fluid flow. These mathematical models directly stems from applying conservation of mathematical quantities within a control volume.

> Is this related to the idea of a conservative vector field? I'm actually unsure, but I like the question.

Now consider the case where we take a derivative of a multivariable function. Mathematically, we can expand this derivative with the chain rule, but in doing so, we introduce terms that no longer describe a physical quantity. This is known as the non-conservative form. Most importantly, the non-conservative forms are not valid over discontinuities (i.e. shocks).

### Euler Equations

The Euler equations represent conservation of momentum when viscous forces are neglected. This is also associated with the limit as Reynold’s number approaches infinity, and the regime of potential flow theory. In this regime, the no slip boundary condition cannot be applied, instead fluid flow at the wall is always tangential to the wall. The following equations have assumed incompressible flow:

#### Cartesian Coordinates

$$x:\ \ \ \ \rho\left[\frac{\partial u}{\partial t}+u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}+w\frac{\partial u}{\partial z}\right]=-\frac{\partial P}{\partial x}+\rho g_x$$

$$y:\ \ \ \ \rho\left[\frac{\partial v}{\partial t}+u\frac{\partial v}{\partial x}+v\frac{\partial v}{\partial y}+w\frac{\partial v}{\partial z}\right]=-\frac{\partial P}{\partial x}+\rho g_y$$

$$z:\ \ \ \ \rho\left[\frac{\partial w}{\partial t}+u\frac{\partial w}{\partial x}+v\frac{\partial w}{\partial y}+w\frac{\partial w}{\partial z}\right]=-\frac{\partial P}{\partial x}+\rho g_z$$


### Navier-Stokes
Navier-Stokes is a general statement of conservation of momentum. The form presented here includes forces due to pressure, gravity, and viscous forces, but neglects other types of forces. This form has also assumed constant density and viscosity.

#### Cartesian Coordinates

$$x:\ \ \ \ \rho\left[\frac{\partial u}{\partial t}+u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}+w\frac{\partial u}{\partial z}\right]=-\frac{\partial P}{\partial x}+\rho g_x+\mu\left[\frac{\partial^2u}{\partial x^2}+\frac{\partial^2u}{\partial y^2}+\frac{\partial^2u}{\partial z^2}\right]$$

$$y:\ \ \ \ \rho\left[\frac{\partial v}{\partial t}+u\frac{\partial v}{\partial x}+v\frac{\partial v}{\partial y}+w\frac{\partial v}{\partial z}\right]=-\frac{\partial P}{\partial x}+\rho g_y+\mu\left[\frac{\partial^2v}{\partial x^2}+\frac{\partial^2v}{\partial y^2}+\frac{\partial^2v}{\partial z^2}\right]$$

$$z:\ \ \ \ \rho\left[\frac{\partial w}{\partial t}+u\frac{\partial w}{\partial x}+v\frac{\partial w}{\partial y}+w\frac{\partial w}{\partial z}\right]=-\frac{\partial P}{\partial x}+\rho g_z+\mu\left[\frac{\partial^2w}{\partial x^2}+\frac{\partial^2w}{\partial y^2}+\frac{\partial^2w}{\partial z^2}\right]$$


### Reynold’s Transport Theorem

States that the total time rate of change of an extensive property (B) for a system, depends on the rate of change of the intensive property in the control volume and the flux of that property through the control volume. (Extensive = mass dependent and Intensive = mass independent). In other works, it relates the control mass view of a fluid to the control volume view of a fluid.

$$\frac{DB_{sys}}{Dt}=\int_{cv}^{cv}\frac{\partial}{\partial t}(\rho b)dV+\int_{cs}^{cs}\rho b\left(\vec{v}\bullet\hat{n}\right)ds$$