---
layout: post
title: Fundamentals of Dynamics
permalink: /fundamentalsDynamics/
excerpt_separator: <!--more-->
mathjax: true
---

In dynamics, the goal is to predict the position, velocity, and acceleration of rigid bodies as a function of time through the use of Newton’s second law, F=ma. While the basic principle is simple, the key challenge of dynamics involves the definition of reference frames, vectors, and their relationships. 

<!--more-->

The first idea to introduce is that of a reference frame. References frames are often attached to a rigid body, but this is not required. There are two properties to consider when relating two reference frames. 
1.	Position vector from the origin of one frame to another.
2.	Rotation from one frame to another.

At this point, one may be tempted to take the derivative of the two previous quantities. However, this must be done carefully. This is because there are very specific definitions of angular velocity and velocity. Taking the derivative is non-trivial! We are in the world of 3-dimensions now, so no more thinking in terms of scalars!

### Kinematics

A subset of dynamics, where forces are neglected, and we focus instead on the motion of points and rigid bodies over time.

### Representation of Rotations

As we will see, an angular velocity is one easy way to define the rotation of one frame with respect to another. The angular velocity is defined using a vector and an angle. However, there are other ways to define the rotation. These methods are:
1.	A Rotation Matrix
2.	Euler Angle Rotations
3.	Axis-angle
4.	Quaternions

Each method technically encapsulates all the information you need, and for obvious reasons, some are more useful than others. 

### Vectors

In the context of dynamics, a vector is defined as a construct of direction and magnitude, but do not have an associated location, unless otherwise specified to be a **position vector**. Vectors are typically defined through the use of orthonormal basis vectors. A set of basis vectors is said to span some space/range. (see math section for a more detailed discussion of vectors spaces and linear algebra).

$$V=\sum V_i\alpha_i$$

Where the values of $$\alpha_i$$ are the basis vectors which are defined for a given problem and reference frame, and $$V_i$$ are called the measure numbers (these are scalars).





