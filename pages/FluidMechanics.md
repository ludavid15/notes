---
layout: page
title: Fluid Mechanics
permalink: /Fluids/
date: 2021-05-05
---

To be clear, when we talk about fluid mechanics, we are not just talking about the second state of matter. It honestly would make a lot more sense if we called it "flow mechanics", but too many textbooks have been printed now to change that. In any case, we're stuck with the term fluid mechanics, so that's what we'll be working with here.

In most cases, we'll be dealing with so called **Newtonion fluids**. Non-newtonian fluids are weird, and I haven't studied them, so there won't be anything about them here. 

While we're laying down the groundwork here, it's worth mentioning that classical fluids mechanics is treated as a subset of continuum mechanics. This is an assumption we make to simplify the problem.

> Continuums are characterized by the existence of shear, and by being continuous (duh). 

But watch out! When the density is really low, (such as in space) the continuum assumptions fall apart, at which point we must switch back over to modelcular dynamics. This changes the fundemental approach, and in this scenario things like the Navier-Stokes equations do not apply.

### Newtonian Fluid

A Newtonian fluid is defined by a linear relationship between stress and strain rate. 





In general, we want to find the following properties as a function of location and time:

1.	Pressure
2.	Temperature
3.	Density
4.	Velocity
5.	Acceleration

With the above information, we can find things like lift, drag, work, & heat transfer (all very important for engineering applications). In a complete model, all 5 of these properties are closely related. Not surprisingly, it’s also difficult to solve for all 5 properties at once. Thus, the subject of fluid mechanics is further broken up into categories based on assumptions and simplifications. These assumptions allow us to make certain variables independent of other variables. The three most important “categories” are:

1.	Incompressible vs Compressible
2.	Inviscid vs Viscid
3.	Laminar vs Turbulent

Any combinations of the above labels are technically possible:

1.	Compressible, Inviscid, Laminar = Shocks, expansion waves, acoustic waves
2.	Compressible, Viscid, Turbulent = Turbulent boundary layers, supersonic wakes
3.	Compressible, Viscid, Laminar = Hypersonic boundary layers
4.	Incompressible, Inviscid, Laminar = Potential flow theory
5.	Incompressible, Viscid, Laminar = Creeping flow, boundary layer theory

We can solve any of the above scenarios by applying laws and equations such as:

1.	Thermodynamics
2.	Conservation Equations
3.	Gas Laws
4.	Continuum Mechanics
5.	Imposing additional constraints (i.e. isentropic, isobaric, isochoric, isothermal, steady)
