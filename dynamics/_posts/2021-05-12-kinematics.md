---
layout: post
title: Kinematics
permalink: /kinematics/
excerpt_separator: <!--more-->
mathjax: true
---


A subset of dynamics, where forces are neglected, and we focus instead on the motion of points and rigid bodies over time. At the core of this topic are a series of rules about positions, velocities, accelerations, and how to find them amid a potentially messy system of reference frames and motion constraints. 

<!--more-->

## Derivatives

In the world of 3D dynamics, derivatives get complicated. 


### Derivative of a Vector

The derivative of a vector must always be defined with respect to some reference frame. Given a reference frame A, and basis vectors $$\alpha_i$$, and measure numbers $$V_i$$, the derivative of vector V in frame A is defined as:

$${_\ ^A}\frac{dV}{dt}=\sum\frac{dV_i}{dx}\alpha_i$$

Thus, one way to take the derivative of vector V is to express the vector in terms of the A basis vectors first, and then derive the measure numbers. 


### Angular Velocity

The angular velocity is defined as a vector function such that the cross of it with any vector fixed in the frame yields the derivative of that vector in a new frame. Let's break this down a little bit. 

1. Define a world frame **A**, and local frame **B**. 
2. Define a vector $$b_1$$, that is fixed in **B**, and defined in **B** (understand the difference between fixed in **B** vs defined in **B**).
3. An angular velocity term relates the original vector defined in B, to it's velocity defined in A.

In other words, the angular velocity describes the rotation of one frame in another. 

$${_\ ^A}\omega^B\times V={_\ ^A}\frac{dV}{dt}$$

$${_\ ^A}\omega^B=b_1\left(\dot{b_2}\bullet b_3\right)+b_2\left(\dot{b_3}\bullet b_1\right)+b_3(\dot{b_1}\bullet b_2)\$$

This is a convenient tool for finding the derivative of a vector without first doing a complex change of reference frame calculation. Angular velocities can be added linearly. That is:

$${_\ ^A}\omega^D=\ {_\ ^A}\omega^B+{_\ ^B}\omega^C+\ {_\ ^C}\omega^D$$

Angular velocities can also be taken in inverse by applying a negative value in front:

$${_\ ^A}\omega^B=\ -{_\ ^B}\omega^A$$


### Rules about Derivatives

There are a few rules to keep in mind when taking derivatives of vectors. First, it is that the order of differentiation matters when taking a double differential. That is to say,

$${_\ ^B}\frac{d}{dt}\left({_\ ^A}\frac{d}{dt}V\right)\neq{_\ ^A}\frac{d}{dt}\left({_\ ^B}\frac{d}{dt}V\right)$$

Some other rules are shown below for differentiation of sums and products

* $${_\ ^A}\frac{d}{dt}\left(V_1+V_2\right)=\ {_\ ^A}\frac{d}{dt}V_1+{_\ ^A}\frac{d}{dt}V_2$$

* $${_\ ^A}\frac{d}{dt}\left({sV}_1\right)=\ {_\ ^A}\frac{ds}{dt}V_1+s{_\ ^A}\frac{d}{dt}V_1$$

* $${_\ ^A}\frac{d}{dt}\left(V\bullet W\right)=\ {_\ ^A}\frac{dV}{dt}\bullet W+V\bullet{_\ ^A}\frac{dW}{dt}$$

$${_\ ^A}\frac{d}{dt}\left(V\times W\right)=\ {_\ ^A}\frac{dV}{dt}\times W+{_\ ^A}\frac{dW}{dt}\times V$$


### Simple Angular Velocity

If there is a vector (k) fixed in both frame A and frame B over an interval of time, then B is said to have simple angular velocity in A during that time interval. This simplifies the expression of the angular velocity of B in A to:

{_\ ^A}\omega^B=\ \dot{\theta}k

This is a more precise way of defining the case where an “axis” of rotation may exist, but note that generally speaking, an axis does not need to exist for us to be able to define an angular velocity.

> Euler angles (Roll, Pitch, Yaw) are often used as a way to define the attitude of a vehicle. In our kinematics framework, each euler angle represents a case of simple angular velocity. We could combine all three into a single angular velocity term, but it would not longer be simple. 


### Derivative in Two Reference Frames

The derivative of the same vector with respect to two different reference frames A and B can be related by the angular velocity of B in A. 

$${_\ ^A}\frac{dV}{dt}=\ {_\ ^B}\frac{dV}{dt}+{_\ ^A}\omega^B\times V$$

Where V does not have to be a vector fixed in B. Note that if V is fixed in B, the derivative of V with respect to B goes to zero, leaving just the cross product of the angular velocity and V yielding the derivative in A. 


### Angular Acceleration

The angular acceleration of a vector is defined as the derivative of an angular velocity vector function in *any frame*. Note that the frame in which we take the derivative does not matter. 

$${_\ ^A}\alpha^B=\ {_\ ^A}\frac{d}{dt}{_\ ^A}\omega^B={_\ ^B}\frac{d}{dt}{_\ ^A}\omega^B\$$

We can prove this second fact by applying the rule of differentiation in two reference frames, noting that a vector crossed by itself is always equal to zero.

$${_\ ^A}\frac{d\omega}{dt}=\ {_\ ^B}\frac{d\omega}{dt}+{_\ ^A}\omega^B\times{_\ ^A}\omega^B$$


### General Velocity and General Acceleration

To define general velocity, we need to define a position vector. A position vector must start from a fixed point in the frame of differentiation. Any fixed point can be taken, as long as it is in the frame.

$${_\ ^A}V^P=\ {_\ ^A}\frac{d}{dt}P^{P/N}$$

The above is an expression for the velocity of point P in the reference frame A, where the vector P goes from point N fixed in A to a point P not fixed in A. The definition of acceleration of point P in frame A is then found by taking the second derivative of the velocity vector.

$${_\ ^A}a^P={_\ ^A}\frac{d}{dt}{_\ ^A}V^P$$

### V2PTS and A2PTS

Consider two points (P and Q) fixed in a rigid body B, that has some angular velocity in frame A. We can relate the velocities of these two points in frame A as:

$${{_\ ^A}V}^Q={{_\ ^A}V}^P+{{_\ ^A}\omega}^B\times R^{Q/P}$$

Where R is a vector that points to Q from P. Similarly, we can relate the acceleration of these points if we know the angular acceleration of body B in frame A.

$${{_\ ^A}a}^Q={{_\ ^A}a}^P+{{_\ ^A}\omega}^B\times\left({{_\ ^A}\omega}^B\times R^\sfrac{Q}{P}\right)+{{_\ ^A}\alpha}^B\times R^\sfrac{Q}{P}$$

### V1PTS and A1PTS

Consider a point P that has some velocity in frame B. Frame B itself moved with angular velocity in a reference frame A. The velocity and acceleration of point P in frame A is defined as:

$${{_\ ^A}V}^P={{_\ ^A}V}^{B_p}+{{_\ ^B}V}^P$$

$${{_\ ^A}a}^P={{_\ ^A}a}^{B_p}+{{_\ ^B}a}^P+2{{_\ ^A}\omega}^B\times{{_\ ^B}V}^P$$

Where Bp is defined as a point of B coincident with P at some time, t*. This is convenient because we can define Bp to be stationary in B. 


## Configuration Constraints

Consider a system of points, where each point is defined by position vector, where each vector has three measure numbers. A constraint configuration constraint is a function of these measure numbers that is equal to zero. Configuration constraints are also known as “holonomic constraints”.

$$P_1,P_2,\ldots,\ P_n\rightarrow vectors$$

$$f\left(P_{11},\ P_{12},\ P_{13},\ldots,\ P_{n1},\ P_{n2},P_{n3}\right)=0$$

Next, we are going to define what are known as generalized coordinates and speeds. The main objective of this function is to simplify later when we have to define and solve the F = ma equation.

### Generalized Coordinates

Instead of using configuration constraints, we can define a set of (n) generalized coordinates. The total number of generalized coordinates is equal to:

n=3v+6\eta-m

Where v is the number of points, $$\eta$$ is the number of rigid bodies, and m is the number of configuration constraints we have defined in the original problem. Generalized coordinates are usually defined with the letter q.

$$q_1,q_2,q_3,\ldots q_n$$


### Generalized Speeds

Generalized speeds are defined as linear combinations of the time derivative of the generalized coordinates. We define these both with the sum notation, and in matrix notation. 

$$u_r=\sum_{s=1}^{n}{Y_{rs}{\dot{q}}_s}+Z_r\ \ \ \ \ \ r=(1,\ \ldots n)$$

$$u=Y\dot{q}+Z$$

Thus, we can also invert the matrix expression to arrive at an expression for the kinematic differential equations as follows:

$$\dot{q}=Y^{-1}u-Y^{-1}Z$$

Generalized speeds are useful because they give us the flexibility to simplify our expression for velocity. We define as many as are necessary to fully describe the problem. 


### Motion Constraints

The motion constraints can be created by separating the generalized speeds into a series of dependent and independent generalized speeds. We denote the first 1 through p speeds as the independent speeds, and p+1 through n as the dependent speeds. The dependent speeds are linear combinations of the independent speeds. The number of independent speeds, p, is also referred to as the degrees of freedom. 

$$u_1,u_2,\ldots,\ u_p,\ u_{p+1},\ldots,\ u_n$$

$$u_r=\ \sum_{s=1}^{P}{A_{rs}u_s+B_r}\ \ \ \ \ r=(p+1,\ \ldots,\ n)$$

Motion constraints are referred to as “non-holonomic constraints”, but this is distinct from the “holonomic” constraints we used to define coordinate constraints (very confusing).

### Partial Angular Velocities and Partial Velocities

The partial angular velocities are defined as those that when multiplied by the generalized speeds produce the original angular velocity expression. Note that there is a remainder term at the end. There are (n) total partial angular velocities. When motion constraints are applied, there are only (p) partial angular velocities – one for every generalized speed. 

$${{_\ ^A}\omega}^B=\left[{_\ ^A}\omega_1^B,\ \ldots,\ {_\ ^A}\omega_n^B\right]\left[\begin{matrix}u_1\\\ldots\\u_n\\\end{matrix}\right]+w_t$$

$${{_\ ^A}\omega}^B=\left[{_\ ^A}{\widetilde{\omega}}_1^B,\ \ldots,\ {_\ ^A}{\widetilde{\omega}}_p^B\right]\left[\begin{matrix}u_1\\\ldots\\u_p\\\end{matrix}\right]+{\widetilde{w}}_t$$

The partial velocities are defined in much the same way. 

$${{_\ ^A}V}^B=\left[{_\ ^A}V_1^B,\ \ldots,\ {_\ ^A}V_n^B\right]\left[\begin{matrix}u_1\\\ldots\\u_n\\\end{matrix}\right]+V_t$$

$${{_\ ^A}V}^B=\left[{_\ ^A}{\widetilde{V}}_1^B,\ \ldots,\ {_\ ^A}{\widetilde{V}}_p^B\right]\left[\begin{matrix}u_1\\\ldots\\u_p\\\end{matrix}\right]+{\widetilde{V}}_t$$

The partial angular velocities can be derived by using our previous definition of the angular velocity in terms of the basis vectors and their derivatives.

$${_\ ^A}\omega^B=b_1\left(\dot{b_2}\bullet b_3\right)+b_2\left(\dot{b_3}\bullet b_1\right)+b_3\left(\dot{b_1}\bullet b_2\right)$$

$$\frac{{_\ ^A}dV}{dt}=\left[\begin{matrix}\frac{\partial V}{\partial q_1}&\ldots&\frac{\partial V}{\partial q_s}\\\end{matrix}\right]\left[\begin{matrix}{\dot{q}}_1\\\ldots\\{\dot{q}}_s\\\end{matrix}\right]+\frac{{_\ ^A}\partial V}{\partial t}=\frac{\partial V}{\partial q}\dot{q}+\frac{{_\ ^A}\partial V}{\partial t}$$

$$\dot{q}=Wu+X$$

$${_\ ^A}\omega^B=\left[b_1\frac{\partial b_2}{\partial q}\bullet b_3+b_2\frac{\partial b_3}{\partial q}\bullet b_1+b_3\frac{\partial b_1}{\partial q}\bullet b_2\right]\left(Wu+X\right)+\frac{{_\ ^A}\partial b_1}{\partial t}+\frac{{_\ ^A}\partial b_2}{\partial t}+\frac{{_\ ^A}\partial b_3}{\partial t}$$

$${_\ ^A}\omega^B=\left[~\right]Wu+\left[~\right]X+\frac{{_\ ^A}\partial b_1}{\partial t}+\frac{{_\ ^A}\partial b_2}{\partial t}+\frac{{_\ ^A}\partial b_3}{\partial t}$$

We now have an expression for the angular velocity which satisfies the format we’ve already defined for the partial angular velocities. Take care to notice everything that goes into the remainder term. 

But why define partial angular velocities at well? Well, in a full dynamics problem, we'll frequently encounter a situation in which an applied force causes a resultant acceleration/velocity in one direction, but not in another. Partial velocities allow us to separate each F = ma statement by direction, greatly simplifying each equation.


### Partial Acceleration and Partial Velocities

We’re going to take the projection of accelerations into the partial velocities and see that it connects to the same result in Lagrange’s Method. I will write more when I understand what’s going on. 