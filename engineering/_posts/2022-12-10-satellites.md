---
layout: post
title: Satellite Engineering Fundamentals
permalink: /satellitesIntro/
mathjax: true
except_separator: <!--more-->
categories: engineering
---

Finally we're getting to stuff that I work with. There's a lot to know when it comes to satellites, so in this post we're just going to stick to the basics. 

<!--more-->

Before we design any hardware, first we need to understand our mission objective. Once that's determined, we'll be able to select an appropriate orbit. The orbit is very important because that decides our operating environment (for example, solar intensity, exposure to radiation, available communication stations, etc).

## Orbits

In this post we'll focus on Earth Orbits. For the most part these can be roughly categorized by their altitude, eccentricity, and inclination.

| Name  | Description 
|--     |--
|HEO    | Highly Elliptical Orbit
|       | These have a perigee relatively close to Earth, but have a very high apogee. This means that the satellite spends a lot of time at apogee, but swings through perigee pretty quickly.
|LEO    | Low Earth Orbit
|       | Roughly any orbit below 2000km in altitude. These orbits are convenient and accessible, but have a limited field of view. 
|GEO    | Geosychonous Earth Orbit
|       | These orbits have a period equal to 24 hours, which means they sit over the same spot on earth. 

Orbits will high inclination are typically called "polar" (i.e. they fly over the poles of the Earth). Generally, changing an orbit's inclination is pretty expensive in terms of delta-V, so many polar satellites are launched at higher latitudes (which puts you naturally into a high inclination orbit).


## Hardware

Regardless of where you go, almost every satellite is going to have some form of each of the following.

### Communication

Your comm system will be unique to your application, but in general some kind of antenna will be required. More importantly perhaps, is *what and when* you plan to communicate. A few questions to ponder:

1. Are there specific ground stations you want to point to? Or will you have an omni-directional antenna onboard?
2. What are the security needs? If there's data to protect, you'll probably want some kind of encoding or encryption.
3. How are you going to communicate with the satellite from the ground? Will you have an antenna that points to it? If so, how are you going to track the satellite's position in the sky?
4. What are the signal to noise (S/N) and latency requirements? 

Also worth thinking about is the [OSI Model](https://en.wikipedia.org/wiki/OSI_model). For a satellite's comm system, you'll need to consider all layers. 

Especially for satellites, the distances between your sending and receiving terminal can be significant. You'll want to pay careful attention to the required power of your signal, and balance that against noise and signal degradation. 

Once the main downlink path has been designed, you'll want to think about what actual content you want. Will you have telemetry to monitor the health and status of your system? How often will it be collected and reported? How will it be identified? 

### Propulsion

The propulsion system provides Delta-V capacity to your satellite. This could be used initially for getting into your orbit, but also after the fact for maintaining your orbit, or for emergency collision avoidance maneuvers. 

<p class=message>
Why do orbits need to be maintained? Well, atmospheric drag for one. But also the Earth isn't perfectly spherical and this causes orbits to drift over time (called precession).
</p>

Depending on your design, propulsion thrusters are usually classified in two ways: either as primary thrusters, which provide delta-V, or as attitude control thrusters. The latter needs less thrust, but are used more, so a higher specific impulse would be good.

### Attitude Control

The attitude control system serves effectively the same role as your car's steering. In zero-G however, the only way to control your pointing is to control your momentum. The primary methods are:

| Thrusters |
|--
| This one's pretty straightforward. If you have thrusters that aren't pointed through the center of mass, firing them will create a torque. The obvious downside here is that fuel is a limited resource. 

| Magnetic Torque Rods |
|--
| If you're orbiting the Earth, you have the benefit of orbiting in a magnetic field. If you pass current through a wire, it will interact with this magnetic field and generate a force, which you can harness for attitude control. 

| Wheels or Gyros |
|--
| These are maybe less intuitive. First, we should remember that total momentum is conserved. This means that if we change the momentum of one thing on the spacecraft, something else will change as well to preserve the total. On a satellite, we can change the speed/orientation of a heavy wheel or gyro using an electric motor, which induces a corresponding change in the angular momentum in the rest of the satellite, thereby providing us with a means of attitude control. 

If you've taken a controls class, you may also know that effective controller design requires knowledge of your mass distribution. Some of the more important external placements are going to be your:

1. Solar arrays
2. Comm Antennas
3. Payload
4. Radiator

Which is going to be constrained primarily by your orbit, power needs, thermal needs, and mission needs. In other words, any controller needs are usually going to come second. This is usually fine - it's easier to size up your control mechanism than to realize later that your radiator accidently gets pointed into the sun while pointing the payload!

> Propulsion tanks tend to be placed towards the center of your satellite. This just works overall because tanks tend to be both big and heavy, but also over time as you use up propellant, this minimizes how far the center of mass shifts.

### Attitude Determination

Control doesn't do much good unless you know where you are. For a satellite, two important things to know are your 1) ephemeris (position along the orbit) and 2) attitude. This gets a little bit into the world of controls, which we won't dive into, but you'll always want sensors to collect data. A few options include:

* GPS Receiver
* Star Tracker
* Sun Sensor
* Inertial Measurement or Reference Unit

As for actually determining your attitude and ephemeris from sensor data, you could try some kind of Kalman filter. 

### Power

For Earth orbiting satellites, your primary source of power is almost always going to be solar, it's just too easy not to! 

<p class=message>
The only time you wouldn't use solar is for deep space missions. As you move away from the sun, solar intensity drops proportionally to the inverse square of your distance. So if you were going out to Pluto for example, nuclear power might be a better option.
</p>

If you're in LEO or even HEO orbit, there will likely be times when you are eclipsed by the Earth. You'll need to size your batteries accordingly so you can get through this period without solar power. 

If your position and attitude are changing rapidly, you may also want some way to gimbal your solar panels into or out of the sun, to control the flow of power/heat.

### Thermal

Thermal gets tricky in space, because there's no convection or conduction, only radiation. This means that spacecraft are often subjected to enormous temperature ranges (-100 to 100 deg celsius is not a bad estimate). Heaters are essential to prevent things from freezing, while radiators are just as important to prevent things from overheating. 

For any given piece of hardware, there's usually an operating temperature range, and a survival temperature range. And then on the structural side of things, you may need to think about your coefficients of thermal expansion. This can be a primary source for structural stress.

### Launch Vehicle Intefacing

An equally important piece of your design is your launch vehicle interface. After all, the LV is what takes you into space. Do you have special environmental needs while you're in the fairing? Can you survive the g's during launch? How will you ensure a clean separation? 


## Systems Engineering

In the real world, no task is performed in isolation. A lot of supporting infrastructure goes a long way towards making programs safe, reliable, and effective. A satellite is no different. In addition to hardware to perform the basic functions, we also need hardware to support them. This can look like a number of things:

* Fault Detection and Response 
* Software Updates
* Health and Status Monitoring
* Redundant/Emergency Systems
* Data Verification and Validation
* Security Systems








