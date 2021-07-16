---
layout: post
title: Path Planning
permalink: /pathPlanning/
mathjax: true
except_separator: <!--more-->
categories: algorithms
---

Get to where ya want to be.

### Sampling Methods

As the name implies, these methods sample the free space for feasible paths. Active methods like Rapidly-Exploring Random Trees (RRT) expand outwards and only add new paths to existing paths (thus keeping everything connected). Meanwhile passive methods like Probabilistic Roadmaps (PRM) fill the feasible space and then must find a connected path. Sampling methods tend to be the most simple, but most do not guarantee a global optimum, nor do they typically consider things like dynamic feasibility, or visibility.

### Node or Heuristic Based Searches

Node based algorithms implement a search strategy to optimize some cost function. In this sense, they represent a form of dynamic programming. Fundamental to this category are methods like Dijkstra's algorithm, A*, and D* []. As with sampling methods, the location of the drone and obstacles in the environment must be known ahead of time.   

### Mathematical Modeling

Mathematical modeling is a more comprehensive, though computationally expensive strategy. With this approach, the problem is expressed by a cost function subject to kinodynamic constraints. This large optimization problem is then solved using a variety of either direct or indirect methods, i.e. through construction of the Hamiltonian, collocation, shooting methods, etc.

### Machine Learning Methods

These methods involve the use of machine learning to discover an appropriate cost function. Rather than construct a model which tries to capture all the details, data is used to train a network to make the appropriate path decision. It may be more accurate to call the final algorithm a controller, rather than a path planner. 

