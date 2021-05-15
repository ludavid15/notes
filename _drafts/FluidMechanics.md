---
layout: page
title: Fluid Mechanics
permalink: /Fluids/
mathjax: true
date: 2021-05-05
---




### Conservation of Mass

Also known as continuity. Time rate of change of mass in the control volume (CV) is equal to the mass flux through the boundary. Or, in differential form, partial derivative of density plus mass flux is zero.

* Integral
$$\frac{\partial}{\partial t}\iiint\rho dV=-\oiint{\rho\mathbit{u}\bullet\hat{\mathbit{n}}dA}$$
* Conservative
$$\frac{\partial\rho}{\partial t}+\nabla\bullet\left(\rho\mathbit{u}\right)=0$$
* Non-conservative
$$\frac{D\rho}{Dt}+\nabla\bullet\left(\rho\mathbit{u}\right)=0$$

For quasi 1-dimensional steady flow, the mass flow rate can be expressed as the following:

$$\dot{m}=\rho AV$$

For 2D incompressible flow, continuity can be expressed as:

$$\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}=0$$

### Conservation of Momentum
Time rate of change of momentum in the CV is equal to advection term plus forces. Or in differential form, partial of momentum with respect to time plus advection term is equal to forces acting on the fluid element. Note that the right side of the equation is the substantial derivative. You may recognize these as the Navier-Stokes equations. Or another way of thinking about it, the Navier-Stokes equations are just a statement momentum conservation.

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


### Dimensional Analysis
We can re-write an equation with normalized terms to see the relative magnitude of the different variables. For example, we can introduce a variable, keeping in mind to apply the chain rule when we take a derivative:

$$\widetilde{x}=\frac{x}{L}$$

$$\frac{\partial\widetilde{x}}{\partial t}=\frac{1}{L}\frac{\partial x}{\partial t}$$

We can then make the following substitution into the original expression

$$\frac{\partial x}{\partial t}=L\ast\frac{\partial\widetilde{x}}{\partial t}$$


### Bernoulli Equation

Ah who doesn't love Bernoullli's equation. It's so simple. We can derive Bernoulli’s equation from the conservation of energy equations (Euler equations already model adiabatic flow with no viscous forces). Assuming that the flow is also isentropic, steady, and irrotational, Euler’s equations simplify into: 

$$P+\frac{1}{2}\rho U^2+gz=constant$$

Ok, hold on, what are those assumptions again? Let's just go over those one more time: isentropic, stready, irrotational, adiabatic, inviscid.

Oh well.

Unsteady Bernoulli’s (applicable for irrotational flow). Where the integral of ds is taken along a streamline.

$$\int\frac{\partial\left|v\right|}{\partial x}ds+\frac{1}{2}v^2+\int\frac{\partial P}{\rho}+gz=F(t)$$


### 2D Potential Flow
Potential flow theory is the theory of inviscid fluid flow. This is also the limit where Reynold’s number tends to infinity. For two-dimensional inviscid flow, we can define the velocity components in terms of two other functions, the stream function and the potential function.


* Irrotational Velocity Potential $\phi$ 	$$\nabla\times\vec{V}=0$$
* Incompressible Stream Function $\psi$	$$\nabla\bullet\vec{V}=0$$

$$u=\ \frac{\partial\phi}{\partial x}= \frac{\partial\psi}{\partial y}$$

$$v=\ \frac{\partial\phi}{\partial y}=\ -\frac{\partial\psi}{\partial x}$$

$$u_r=\frac{\partial\phi}{\partial r}=\frac{1}{r}\frac{\partial\psi}{\partial\theta}$$

$$u_\theta=\frac{\partial\psi}{\partial r}=\frac{1}{r}\frac{\partial\phi}{\partial\theta}$$

If either of the following is true, we can say that the fluid is both irrotational and incompressible.

$$\nabla^2\psi=0$$

$$\nabla^2\phi=0$$

In assuming incompressibility, mass continuity reduces into a volume continuity equation, where density has dropped out:

$$Volume\ Continuity:\ \ \ \nabla\bullet V=\ \frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}=0$$

## Viscous Flow

#### Reynold’s Number

The ratio between viscous forces and inertial forces and helps show when a flow transitions from laminar to turbulent flow. Where µ is the dynamic viscosity.

$$Re=\ \frac{\rho U_\infty L}{\mu}$$

At very low Re, we get the Stokes equations. At very high Re, we get the Euler equations (potential flow theory).

#### Low Reynold’s Number Flow (Stokes’ Flow)

This is the exact opposite regime of potential flow theory, in which viscous forces dominate over inertia forces. This is usually associated with low velocity, small scale, or highly viscous flows. Some applications can include:

* Fully developed duct flow
* Flow about immersed bodies (i.e. small particle dynamics)
* Lubrication theory
* Flow through porous media (mostly used for civil engineering)

Under the above assumption, the momentum equation reduces to the following:

$$\nabla P\approx\mu\nabla^2V$$

#### Low Reynold’s Number Flow Over a Sphere

By solving stokes equations with the boundary conditions for viscous flow past a sphere, the following stream function can be calculated:

$$\psi=\frac{1}{4}Ua^2{sin}^2(\theta)\left[\frac{a}{r}-\frac{3r}{a}+\frac{2r^2}{a^2}\right]$$

This can be compared to the stream function found by applying potential flow theory about a sphere:

$$\psi=\frac{1}{2}Ur^2{sin}^2(\theta)\left[1-\frac{a^3}{r^3}\right]$$

Solving the first equation for shear and pressure drag, we find an expression for the total drag on a sphere in the low Reynold’s number limit:

$$F=4\pi\mu Ua+2\pi\mu Ua$$

Where the first term is the viscous contribution to drag, and the second term is the pressure contribution to drag. This is normalized by the area and dynamic pressure to find the drag coefficient.

$$C_d=\frac{2F}{\rho U^2\pi a^2}=\frac{24}{Re}$$

This equation underpredicts drag for Reynold’s numbers larger than 1, since separation and wakes introduce greater pressure drag.

#### Steady Flow between Infinite Plates

A class of problem in which viscous forces dominate. We take the bottom plate to be stationary and assume some steady velocity for the top plate. There can also be a pressure gradient in the direction parallel to the plates. 

In the limit that the top plate’s velocity tends to zero we get a Hagen-Poiseuille flow problem (pressure gradient driven flow). In the limit that the pressure gradient tends to zero we get a Couette flow problem (velocity of the top plate drives flow). 
The general solution of the velocity profile is expressed below. The first equation is the general solution, while the second equation takes the lower wall to be stationary. Where τo is the shear stress at the wall where y=0, and uo is the velocity at the wall where y=0.

$$u\left(y\right)=\ -\frac{1}{2\mu}\left(-\frac{dP}{dx}\right)y^2+\frac{\tau_o}{\mu}y+u_o$$

$$u\left(y\right)=\ +\frac{1}{2\mu}\left(-\frac{dP}{dx}\right)y(h-y)+U\frac{y}{h}$$

We can also solve for the volume flow rate per unit span by integrating over y.

$$Q=U\frac{h}{2}+\frac{h^3}{12\mu}\left(-\frac{dP}{dx}\right)$$

#### Unsteady Flow & Infinite Plates

There are two problems within this category, known as Stokes 1st problem (an impulsively started plate) and Stokes’s 2nd problem (an oscillating plate).

##### 1st Problem:

$$\frac{u(y,t)}{U}=1-\erf{\left(\frac{\eta}{2}\right)}$$

$$\erf{\left(x\right)}=\ \frac{2}{\sqrt\pi}\int_{0}^{x}{e^{-x^2}dx$$ 

$$\eta=\ \frac{y}{\sqrt{\nu t}}}$$

As time increases, the penetration height will increase. At infinite time, the entire fluid moves with velocity U. The above solution represents a non-dimensionalized solution, where η represents the ratio of position to penetration height scaling.

##### 2nd Problem:

Motion of the bottom plate is defined as the following:

$$U\left(t\right)=\ U_o\cos\funcapply(\omega t)$$

The velocity profile above the plate and the stress at the wall can be solved to show the following:

$$u\left(y,t\right)=U_oe^{-y\sqrt{\sfrac{\omega}{2v}}}cos\left(\omega t-y\sqrt{\sfrac{\omega}{2v}}\right)$$

$$\tau_{wall}=\mu\frac{\partial u}{\partial y}=U_o\sqrt{\rho\mu\omega}sin\left(\omega t-\sfrac{\pi}{4}\right)$$

The amplitude of the velocity oscillation decreases with distance from the plate. The ratio of viscosity to frequency determines the penetration height. Note that this ratio also affects a phase lead/lag, which changes with height, represented within the cosine term.

#### Hagen-Poiseuille Circular Pipe Flow Model

Pressure driven viscous pipe flow. Given L is the length of pipe, Q is the volume flow rate, and some known diameter, we can find the pressure drop. Assumes laminar flow.

$$∆P= 8μLQπR4$$

$$u\left(r\right)=\ -\frac{1}{4\mu}\left(-\frac{\partial P}{\partial x}\right)\left(r_o^2-r^2\right)$$

$$Q=\ \frac{\pi R^4}{8\mu}\left(\frac{\partial P}{\partial x}\right)$$

$$C_f=-\frac{\tau_w}{\sfrac{(1}{2})\rho{U_{ave}}^2}=\frac{16}{Re_D}$$

Note that this may not be valid for short pipes, flow near the entrance, and fluids with low viscosity, or flow in a wide pipe. If flow is turbulent, you should switch over to the Darcy-Weisbach approach.

#### More Realistic Pipe Flow Analysis

For flow (both laminar and turbulent) in a pipe of constant diameter D, we can express the pressure across a given length as:
$$∆PL=fd(12)ρU2D$$

Where fd is the Darcy friction factor. In the laminar regime, the Darcy Friction factor is equal to $$\sfrac{f_D=64}{Re}$$. For turbulent regime values, the friction factor is dependent on the surface roughness. Look up results in a Moody Diagram.


More commonly, pressure loss per unit length is replaced with head loss per unit length, S, where head loss is calculated as:
$$∆h= ρg∆P$$

$$S=∆hL=fd12gV2D$$

Note that the friction factor in the turbulent regime can be calculated with turbulent flow theory and is not simply an empiric fit!

#### Colebrook Interpolation Formula (Turbulent & Transition Regime)

Provides an easy way to find the friction factor for a given surface roughness and Reynold’s number. $$\Lambda$$ here is the friction factor.

$$\frac{1}{\Lambda^{1/2}}\approx-2.0\log_{10}{\left(\frac{k/D}{3.7}+\frac{2.51}{Re_D\sqrt\Lambda}\right)}-0.8$$

#### Hydraulic Diameter

For non-circular pipes, an equivalent diameter can be found, known as the hydraulic diameter. This allows you to analyze the pipe as if it were circular.

### Boundary Layers

Boundary layer theory provides a way to account for viscous forces near the wall, after having analyzed inviscid fluid flow with potential flow theory/Euler equations. Assuming the fluid is incompressible, we define the boundary layer height, displacement thickness, and momentum thickness. 

>Velocity Thickness= $$\frac{u(y=\ \delta,t)}{u_\infty}=0.99$$

>Displacement Thickness= $$\delta^\ast=\int_{0}^{\delta}{1-\frac{\rho u}{\rho_\infty u_\infty}dy}$$

>Momentum Thickness= $$\theta=\int_{0}^{\delta}{\frac{\rho u}{\rho_\infty u_\infty}\left(1-\frac{u}{u_\infty}\right)dy}$$

>Skin Friction Coefficient= $$c_f=\frac{2\tau_w}{\rho_\infty{u_\infty}^2}=2\frac{d\theta}{dx}$$

The displacement thickness is the distance by which a streamline in the free stream will be displaced due to the boundary layer. This is found by applying conservation of mass.

 

#### Shape Factor

The shape factor is defined as the ratio of displacement thickness to momentum thickness and is useful to characterize boundary layer properties.

$$H\left(y\right)=\ \frac{\delta^\ast}{\theta}$$

#### Prandtl 2D Boundary Layer Equations

These equations are a simplified version of Navier-Stokes and continuity equations, having through dimensional analysis eliminated negligible terms. In creating these equations, we’ve assumed that the Reynold’s number is much larger than 1. This means the boundary layer is thin, and that the velocity in x is much smaller than the velocity in y in the boundary layer. Note that due to the assumption of high Reynolds number, boundary layer theory is distinct from the low Reynold’s number assumption of the creeping flow model.

Incompressible, 2D flows in the boundary layer are described by the following: (where v is the kinematic viscosity and is distinct from the y component of velocity, v). The second two equations are the same (statement of conservation of momentum). 

$$\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}=0$$

$$\rho\left(\frac{\partial u}{\partial t}+u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}\right)=-\frac{\partial P}{\partial x}+\mu\frac{\partial^2u}{\partial y^2}$$

$$\left(\frac{\partial u}{\partial t}+u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}\right)=U\frac{\partial U}{\partial x}+\mathbit{v}\frac{\partial^2u}{\partial y^2}$$

Boundary Conditions:
* No slip at the wall across all time and (x)
* Uniform velocity far from the wall across all time and (x)
* Some initial velocity at (x) equals zero and (t) equals zero which is maintained through the problem

Notice that pressure is a function of (x) and is invariant with (y) in the boundary layer equations. It we be re-written in terms of the free stream characteristics:

$$\rho\left(\frac{\partial u_e}{\partial t}+u\frac{\partial u_e}{\partial x}\right)=-\frac{\partial P}{\partial x}$$

#### 2D Boundary Layer Similarity Solutions

In most cases, it is easier to create the following similarity variables, defined using the velocity potential:

$$u=\ \frac{\partial\psi}{\partial y}$$

$$v=\ -\frac{\partial\psi}{\partial x}$$

$$\psi\left(y,x\right)=\ U_\infty l\left(x\right)f(\eta)$$

$$\eta=\frac{y}{l(x)}=\frac{y}{x}\sqrt{\frac{Ux}{v}}=\frac{y}{x}\sqrt{Re}$$

$$l\left(x\right)\cong\ \sqrt{\frac{\nu x}{U_\infty}}$$

Here, l(x) is proportional the height of the boundary layer, making η a normalized value for our position in the boundary layer. In addition, f(η) and η are both dimensionless. We should also be able to see that:

$$f\left(\eta\right)\cong{\psi$$

$$f}^\prime\left(\eta\right)\cong{u,\ v$$
 
$$f}^{\prime\prime}\left(\eta\right)\cong\tau$$

Re-writing the Prandtl boundary layer equations in terms of our similarity variables, we find an exact solution:

$$\dddot{f}\left(\eta\right)+f\left(\eta\right)\ddot{f}\left(\eta\right)=0$$

#### Falkner-Skan 2D Solution

The Falkner-Skan solution describes boundary layer flow over a wedge. It is a generalization of the Blasius flat plate boundary layer. Using the same similarity definition as above, the exact solution takes the following form. As with the Blasius solution, a numerical approach is required to find a solution.

$$\dddot{f}+f\ddot{f}+\beta(1+{\dot{f}}^2)=0$$
 
The velocity in the free stream (i.e. ur in the direction of πB) can be represented by the following equation, as a function of the turning angle:

$$u_e=Kx^m$$

$$\beta=\frac{2m}{1+m}$$

In the limiting case where B = 0, you get the Blasius flat plate general solution. In the limit that B = 1, you get stagnation point flow. There are tabulated values for the velocity thickness, displacement thickness, momentum thickness, and friction coefficient for a range of B values.

 
#### Blasius Solution a 2D Flat Plate (1st Order Solution)

The Blasius solution is an exact differential solution of the boundary layer equations for flow over a flat plate, however, solving it requires a numerical approach. 

$$\frac{\delta}{x}=\frac{5}{\sqrt{Re}}$$

$$\frac{\delta^\ast}{x}=\frac{1.72}{\sqrt{Re}}$$

$$\frac{\theta}{x}=\frac{0.664}{\sqrt{Re}}$$

$$c_f=\frac{0.664}{\sqrt{Re}}$$

#### Approximate Solutions to 2D Boundary Layer

Thwaites method uses the Von-Karman integral equations to approximate the boundary layer characteristics. The Von Karman integral relation (steady flow with impermeable wall):

$$\frac{c_f}{2}=\frac{d\theta}{dx}+(2+H)\frac{\theta}{U}\frac{dU}{dx}$$

This equation is still an exact relationship. Thwaites method is to make the following approximation: (where P(x) is any generic function of x, and is there to characterize the changes in the velocity profile shape in the boundary layer as a function of the x position)

$$u(x,y)\approx U\left(x\right)f(\eta,P\left(x\right))$$

In the case of Thwaites method, the following parameter is defined:

$$\lambda=\left(\frac{\theta}{\delta}\right)^2\frac{\delta^2}{v}\frac{dU_e}{dx}=\frac{\theta^2}{v}\frac{dU_e}{dx}$$

The Von-Karman integral relation can then be re-written, and we see that the terms of the original expression are going to be proportional to the parameter defined above.

$$\frac{\tau_w\theta}{\mu U}=\frac{U\theta}{v}\frac{d\theta}{dx}+(2+H)\frac{\theta^2U^\prime}{v}$$

$$\frac{\tau_w\theta}{\mu U}\approx Shear\ Factor\ Correlation=S(\lambda)$$

$$H=\ \frac{\delta^\ast}{\theta}\approx Shape\ Factor\ Correlation=H(\lambda)$$

For an external flow problem, the following expression for momentum thickness can be derived:

$$\theta^2=\frac{0.45v}{U_e^6(x)}\int_{0}^{x}{U_e^5(x\prime)}dx\prime$$

The displacement thickness can be solved by using the following shape factor correlation, as a function of λ. 

$$\delta^\ast=\theta H\left(\lambda\right)$$

$$H\left(\lambda\right)=2+4.14z-83.5z^2+854z^3-3337z^4+4576z^5$$

$$z=0.25-\lambda$$

The laminar boundary layer separates when λ = -0.09. 

#### Pressure Gradient Effects

There are three regimes for the pressure gradient term: favorable (less than zero), adverse (greater than zero), and neutral (equal to zero). 
 
An adverse pressure gradient can cause boundary layer separation. Separation occurs at the point where the wall shear stress is equal to zero (slope of the velocity profile is zero), that is:

$$\tau_w=\mu\frac{du}{dy}=0$$

Axis-Symmetric 3D Boundary Layers

The boundary layer equations for an axisymmetric steady flow without swirl can be shown to be equal to the following:

$$\frac{\partial(r_ou)}{\partial x}+r_o\frac{\partial v}{\partial y}=0$$

$$\rho\left(u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}\right)=\rho u_e\frac{\partial u_e}{\partialx}+\mu\frac{\partial^2u}{\partial y^2}$$

The above equations can be transformed into an equivalent set of 2D boundary layer equations with the Mangler Transformation of the coordinate frame.


#### Laminar Free Stream Shear Flow (Jets, Wakes, Mixing Layers) 

A class of problems involving a large unbounded region and either excess momentum (i.e. a jet or plume) or a momentum deficit (i.e. wake). This section will be completed at a later date. 


#### Fanno Flow

Associated with one dimensional flow with friction. Friction tends to drive flow eventually towards sonic conditions, regardless of whether flow starts out subsonic or supersonic. Given conditions at a point (1) in a pipe, you can solve for the sonic conditions (*). If you then know something about conditions at another point (2), you can use the sonic conditions to backtrack and find all other properties at that second point. In a Fanno flow table, you will usually find the following relations:

$$M_1\ \ \ \ \ \frac{fL}{D}\ \ \ \ \ \frac{P}{P^\ast}\ \ \ \ \ \ \frac{T}{T^\ast}\ \ \ \ \ \ \frac{P_0}{P_0^\ast}$$

#### Rayleigh Flow

Like Fanno flow, where heat addition tends to drive flow towards sonic conditions, regardless of initial velocity. Knowing heat input can allow you to find change in total temperature between two points. From there you can backtrack and solve for all other properties at those two points like how you would do it for Fanno flow.

$$T_{t,2}=\frac{q}{c_p}+T_{t,1}$$


## Turbulent Flow

In general, turbulent flow is modeled statistically. Averages values are used instead of exact ones. Before laminar flow becomes fully turbulent, it experiences transition. Transition begins with flow instability. The point at which a flow trips into instability (critical point) is distinct from the point at which flow transitions fully to turbulence (transition point). 

#### Squire’s Law
For two-dimensional parallel flow, the minimum critical unstable Reynold’s number occurs for a two-dimensional disturbance propagating in the same direction. Really all that this Law states is that a turbulence is tripped in the direction of disturbances.

#### Orr-Sommerfeld Equation
The equation describing the velocity distribution of a two-dimensional disturbance propagating in the same direction as a two-dimensional parallel flow can found to be exactly:

$$\left(U-c\right)\left(\phi^{\prime\prime}-\alpha^2\phi\right)-U^{\prime\prime}\phi+i\frac{\mathbit{\nu}}{\alpha}\left(\phi^{\prime\prime\prime\prime}-2\alpha^2\phi^{\prime\prime}+\alpha^4\phi\right)=\ 0$$

$$\Psi\left(x,y,t\right)=\ \phi\left(y\right)exp\left(i\left[\alpha x-\beta t\right]\right)$$

$$c=\sfrac{\beta}{\alpha}$$

Where U is the velocity of the free stream, α is the wavenumber, c is the wave speed, and the frequency, ω = αc. The primes denote differentiation with respect to y. This is a fourth order linear differential equation. Disturbances must vanish at walls and an infinity. The temporal growth and spatial growth of disturbances are functions of the following form:

* Temporal: $$f\left(Re,\ \alpha,\ c_r,\ c_i\right)=0$$
* Spatial: $$g\left(Re,\ \alpha_r,\ \alpha_i,\ \omega\right)=0$$

Temporal neutral stability occurs when ci is equal to zero, while spatial neutral stability occurs for αi equal to zero. Instability begins at ci greater than zero. A full analytical solution of the Orr-Sommerfeld equation is non-trivial. In general, a non-dimensionalized version of the Orr-Sommerfeld equation can be written and can be plotted. 
 
#### Wavenumber

The wavenumber is the waves per unit space. It is distinct from frequency, which is the waves per unit time.

#### Rayleigh Inviscid Stability Theory

This is the limiting case where the viscous term in the Orr-Sommerfeld equation is neglected. In particular, the following five theorems are outlined:

* It is necessary for instability that the velocity profile have a point of inflection.
* It is further necessary for instability that the numerical value of U’ of the vorticity be a maximum at the point of inflection.
* If a point of inflection exists, it is further necessary that U’’(U-UPI) < 0 somewhere on the profile. 
* If U(y) possesses an inflection point, a neutral disturbance may exist who phase velocity is given by cr.
	The phase velocity of an amplified disturbance must always lie between the minimum and maximum values of U(y).


 

#### Predicting Instability & Transition in Practice
It was found that for many different profiles and conditions, the critical transition Reynold’s number seems to depend only on the shape factor. Thus, if the shape factor can be found, one can predict the point of instability and transition. 
Several models have been proposed to find an equivalent transition point. Wazzan uses a similar approach to instability and finds a transition Reynold’s number as a function of the shape factor. There is no universal curve that accounts for free stream turbulence.

#### Improving Stability
A favorable pressure gradient (decreasing pressure) delays the onset of instability, or in cases bring a flow back into stability. Boundary layers in gases are stabilized by cooling the wall, while boundary layers in liquids are stabilized by heating the wall. 

### Transition to Turbulence
The steps leading to fully developed turbulence are as follows:
* Instability
* Non-linear development waves (Tollmien-Schlichting Waves)
* Three-dimensional instability and streamwise vortices
* Formation of turbulent spots
* Fully developed turbulence

### Reynolds-Averaged Navier Stokes Equation (RANS)

These are time averaged forms of the Navier-Stokes equations. Properties of the fluid are expressed in terms of an average and fluctuation term. An especially interesting result is the resultant equation for local stress.

$$\tau=\ \mu\left[\frac{\partial\bar{u}}{\partial\bar{y}}+\frac{\partial\bar{v}}{\partial\bar{x}}\right]-\rho\bar{u\prime v\prime}$$

The first term is the laminar stress, while the second term is an equivalent turbulent “Reynolds Stress”. Importantly, note that it is independent of viscosity. This means that in regions dominated by the Reynold’s stress, viscosity of the fluid is unimportant.

#### Wall Bounded Turbulent Flow

Near the wall, fluctuations must be near zero, so laminar contributions are more important. Away from the wall, turbulent stress dominates. The velocity profile from a wall then has three components, a viscous dominates inner layer, a turbulent dominated outer layer, and an overlap layer. First, we define the friction velocity:

$$v^\ast=\sqrt{\frac{\tau_w}{\rho}}$$

The average velocity and position are also re-written.

$$u^+=\frac{\bar{u}}{v^\ast}$$

$$y^+=\frac{\rho v^\ast y}{\mu}$$

The following is equation can then model the inner layer, overlap layer, and outer layer.

$$u^+=\frac{1}{k}\ln{\left(y^+\right)}+B+\frac{2\Pi}{k}f(\eta)$$

$$f\left(\eta\right)=\sin^2{\left(\frac{\pi}{2}\eta\right)}$$

Where k and B are universal constants equal to 0.41 and 5.0 respectively. The first term captures the logarithmic relationship in the overlap section, while the second capture the diverging effect in the outer layer. 
 
Very, very near the wall, viscous and laminar forces dominate. The velocity profile in this region is linear and proportional to the wall stress. It is called the viscous sublayer.

$$\tau_w=\mu\frac{\bar{u}}{\bar{y}}$$

$$u^+=y^+$$

#### Turbulent Pipe Flow

Using the above model, you can actually derive an expression for the Darcy-friction factor from the flow equation. Note that this is for a smooth pipe, and so when possible, you should still reference a moody chart. In any case, the following is useful for seeing that the Darcy-Friction is not just an empirically derived fit.

$$\frac{1}{\Lambda^{1/2}}=2.0\log_{10}{\left({Re}_D\Lambda^\frac{1}{2}\right)}-0.8$$

$$Notably the following trends come out:$$

$$\tau\approx0.0396\rho^{3/4}\mu^{7/4}D^{-1/4}{U_{avg}}^{7/4}$$

#### Turbulent Boundary Layers

Using the wall bounded turbulent model, the skin coefficient term can be approximated in terms of the boundary layer thickness Reynolds number. Meanwhile, the momentum thickness is evaluated by using a one-seventh power law profile taken from pipe flow data.

$$C_f=2\frac{d\theta}{dx}$$

$$\frac{\bar{u}}{U_e}\approx\left(\frac{y}{\delta}\right)^{1/7}$$

$$C_f\approx0.020{Re}_\delta^{-1/6}$$

$${Re}_\delta\approx0.16{Re}_x^{6/7}$$




## Compressible Flow

While viscous flow deals with liquids, or flows that are very slow, compressible flow is for your rockets and airplanes. In this Reynold's number regime, the density of a fluid cannot assumed to be constant, but luckily we can ignore viscous effects.


#### Stagnation Properties

For any steady state fluid in motion, we can define stagnation/total properties. These reflect the actual values if the fluid were brought to rest isentropically. 

$$\frac{T_{Total}}{T}=\ \left(\frac{P_{Total}}{P}\right)^\sfrac{\gamma-1}{\gamma}=\left(\frac{\rho_{Total}}{\rho}\right)^{\gamma-1}=1+\left(\frac{\gamma-1}{2}\right)M^2$$

Note that the stagnation properties are frame dependent and thus not intrinsic thermodynamic properties.

### Waves
In the context of fluid dynamics, a wave is simply a disturbance which propagates. This disturbance can have many properties and effects on the fluid as it passes through:

* It can increase/decrease a property of the fluid (density, pressure, etc.)
* It can change the velocity of the fluid
* The magnitude of the change can be large or small
* The shape of the disturbance can be continuous or discontinuous
* It can be isentropic/increase entropy
* It can propagate faster than the local acoustic speed or at the acoustic speed.

By this definition, a shock is a type of wave. Although shocks are often introduced as “stationary” objects, this is because we have shifted our frame of reference such that this the case. A shock can be stationary (like at the inlet of a ramjet), or a shock can propagate (like out from an explosion). 

### Acoustic Wave Theory

An acoustic wave is the propagation of wave with small magnitude through a medium. This wave travels at the local acoustic speed of the medium and is adiabatic (i.e. the energy of the medium before and after the wave has passed through remains constant). 
Given the initial conditions about the displacement and rate, the solution for the propagation of that disturbance can be found (d’Alembert’s Formula). 

$$∆px,t=0=fx$$

$$∂∆p∂tx,t=0=gx$$

$$∆px,t=fx-a∞t+fx+a∞t2+12a∞x-a∞tx+a∞tgsds$$

The fundamental result is that the initial disturbance splits into a left running and right running portion. The fluid velocity, pressure and density can also be related to one another.

$$∆u= ±a∞ρ∞∆ρ$$

$$∆ρ= ±1a∞2∆P$$

$$∆ρ= ±1ρ∞a∞∆P$$

In deriving the above equation, we’ve assumed small amplitudes, meaning that the local speed of sound remains constant through the disturbance. 

If we remove this assumption, the local speed at which the disturbance propagates will be proportional to the magnitude and shape of the disturbance. This leads to finite strength waves and the method of characteristics.


### Method of Characteristics

Alright here's where it get complicated. It turns out that when we no longer assume a constant speed of sound, the equations are a tad unsolvable as they are. To this end, mathemeticians have defined a way around this. Instead of solving the entire system for every point in space, we can define some *characteristic lines*. We can apply a constraint (i.e. some property is constant along the line), and this gives us the final equation we need to solve the system. Then if we define many lines, we can nearly cover the entire region we are solving for. By applying constraints at their intersection points, we can solve a big system of equations and have an approximate solution to our problem.

#### 1D Unsteady MOC

Ok, well I've outlined the principle behind it, but I need to actually write the section on how to do this. :(

#### 2D Steady MOC




#### Minimum Length Nozzle Calculation using MOC

With MOC, it is possible to design a nozzle such that the local curvature exactly cancels any incident expansion waves (these result from the diverging section right after the throat). 
 
### Normal Shocks
Across a normal shock: total temperature remains constant, total pressure decreases, but static pressure and static temperature increase. Density increases, speed decreases. 
Derivation of Normal Shock Equations:

* Continuity Equation: 				$$\rho_1u_1=\rho_2u_2$$
* Momentum Conservation Equation:		$${P_1+\rho}_1{u_1}^2=P_2+\rho_2{u_2}^2$$
* Energy Conservation Equation		$$h_1+\frac{1}{2}u_1^2=h_2+\frac{1}{2}u_2^2$$
* Ideal Gas Law					$$PV=nRT$$
* Calorically Perfect Gas Assumption		$$h=\ C_pT$$

The above represents 5 equations with 5 unknowns (assuming we know the properties at state 1, upstream of the shock). They can be solved to show the following equations:

$$\frac{P_2}{P_1}=1+\frac{2\gamma}{\gamma+1}\left(M_1^2-1\right)$$

$$\frac{T_2}{T_1}=\left[1+\frac{2\gamma}{\gamma+1}\left(M_1^2-1\right)\right]\left[\frac{2+(\gamma-1)M_1^2}{(\gamma+1)M_1^2}\right]$$

$$\frac{\rho_2}{\rho_1}=\frac{u_1}{u_2}=\frac{(\gamma+1)M_1^2}{2+(\gamma-1)M_1^2}$$

$${M_2}^2=\frac{1+\frac{\gamma-1}{2}M_1^2}{\gamma M_1^2-\frac{\gamma-1}{2}}$$

 
### Oblique Shocks

Supersonic flow over an angle. From the conservation equations, there are two equally valid solutions to an oblique shock problem, a strong solution and a weak solution. It is also possible that for a given combination of turning angle and incoming Mach number, there is no solution. Instead, the oblique shock becomes a detached or bow shock.
 
$$M_{n,1}=M_1\sin{\left(\sigma\right)}$$

$$M_2=\ \frac{M_{2n}}{\sin\funcapply(\sigma-\delta)}$$

$$\tan{\left(\delta\right)}=2\cot\funcapply(\sigma)\left[\frac{M_1^2{sin}^2\left(\sigma\right)-1}{M_1^2\left(\gamma+cos\left(2\sigma\right)\right)+2}\right]$$

Unless there is some downstream flow feature to support the strong shock, the weak solution is typically what develops. 
The presence of a shock introduces a sudden change in the fluid properties, including pressure. This leads to the creation of wave drag.
 
There are some important takeaways from the above figure. 
* The red line denotes the maximum shock wave angle that is possible for a given incoming Mach number and deflection angle. If either one is increased while the other is kept constant, the shock will detach.
* After a strong shock, the fluid is always subsonic.
* fter a weak shock, the fluid can be either subsonic OR supersonic. This is the region bounded by the red and blue dotted lines.
* The strong limit is the normal shock.

### Detached Shock

The detached or bow shock is just an oblique shock problem in which a range of deflection angles (0 to 90 degrees) are present. At the centerline, fluid flow is perfectly perpendicular to the bow shock, and so it is treated as a normal shock. Traveling away from the center, the fluid flow has velocity partially parallel to the shock. This is equivalent to an oblique shock at some deflection angle. Infinitely far away, the deflection angle reaches 0 degrees and hence no shock develops.

Notice that there are two regions behind the bow shock, a subsonic flow region, and a supersonic flow region. The dividing line between these two regimes is defined by the point along the bow shock where M2 = 1, or the blue dotted line in the figure above. 

### Expansion Fans
The exact opposite of an oblique shock, in which the boundary curves away from the flow direction. An expansion fan is formed as a continuous spread of Mach/Acoustic waves, each providing some infinitesimal change to the fluid properties. Thus, flow through an expansion fan is isentropic. 

### Prandtl-Meyer Function
The flow angle can be related to the local Mach number by applying continuity and conservation laws across an expansion wave. The resulting expression is the Prandtl-Meyer Function.

$$\theta_2-\theta_1=v\left(M_2\right)-v(M_1)$$

$$v\left(M\right)=\ \sqrt{\frac{\gamma+1}{\gamma-1}}arctan\sqrt{\frac{\gamma-1}{\gamma+1}(M^2-1)}-arctan\sqrt{M^2-1}$$

### Reflections

At a solid boundary, waves reflect in a like manner. That is, a shock reflects as a shock, and an expansion wave reflects as an expansion wave. This maintains the kinematic constraint that flow near a wall must be parallel to it (i.e. no penetration).
At a free boundary, waves reflect in opposite manners. A shock reflects as an expansion wave, while an expansion wave reflects and converges as a shock. Across a free boundary, the pressure must be equal, and the flow in both regions must be parallel.

### Interactions of Shockwaves

TBD 

### Expansion Wave Interactions (Method of Characteristics)

TBD

### Compressible Boundary Layers

The key feature of compressible boundary layers is that temperature and enthalpy changes cannot be decoupled from the velocity profile. Thus, even if the wall is adiabatic, the flow itself is neither adiabatic or isentropic (viscous dissipation). Consider the steady case where Prandtl number is equal to 1 (not a bad assumption with gases). This is also known as the Crocco-Busemann Relations.

$$\Pr{=\ \frac{\mu C_p}{k}}$$

For an arbitrary pressure gradient, the temperature distribution takes the following form. This condition is satisfied for isentropic flow outside the boundary layer.

$$T=T_e\left[1+\frac{\gamma-1}{2}M_e^2\left(1-\frac{u^2}{U_e^2}\right)\right]$$

For this scenario, the adiabatic wall temperature is equal to the stagnation temperature of the free stream. Recovery factor is 1. 

The second scenario is for zero pressure gradient.

$$T-T_w=\left(T_{oe}-T_w\right)\frac{u}{U_e}-\frac{u^2}{2C_p}$$

The similar solution to the adiabatic wall temperature can be found for cases of Prandtl number larger than one with the following expression.

$$T_{aw}=T_e\left[1+\frac{\gamma-1}{2}\sqrt{Pr}M_e^2\right]$$

#### Adiabatic Wall Temperature

This is the wall temperature for a fluid flow such that there is no net heat transfer into or out of the wall. If a system is let to run until equilibrium, this is the steady state temperature the immersed object will reach. 

 
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
  







