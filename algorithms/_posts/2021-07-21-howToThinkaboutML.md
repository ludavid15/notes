---
layout: post
title: How to Think About Machine Learning
permalink: /howTomachineLearning/
mathjax: true
except_separator: <!--more-->
categories: algorithms
---

There is so much literature out there on machine learning that it can get pretty overwhelming. This post serves to organize machine learning into a few broad categories, and in doing so, highlight their different strengths. 

<!--more-->

Before going further, it's worth mentioning that many machine learning algorithms are built using optimization. There is almost always something to be optimized (an objective function - error, fitness, etc.), and different ways to run the optimization (genetic, linear, quadratic, etc.). Different algorithms may change the problem, but the name of the game remains the same. Keep this mind, because it might help unify your understanding of this large field. 


### Supervised Learning

Supervised learning algorithms are used when you know the type of output you want, but need to learn the function that will get you there. These algorithms are often implemented with deep neural networks, and are useful for classification tasks. As the name implies, this method absolutely requires having a labeled dataset. If your problem doesn't readily accept labels, this strategy will probably fall short. Try instead to identify if parts of the solution involve identification. 

### Unsupervised Learning

Unsupervised learning algorithms discover patterns in your data. Note that these algorithms are NOT classification algorithms. Instead, they tell you what the likely categories are. In this sense, they are a lot like the statistical regression methods you may have have encountered in high school. Depending on the structure of your data, there are many different strategies which fall under this umbrella, such as:

* K-means Clustering
* Singular Value Decomposition
* Independent Component Analysis
* Autoencoders

Another way to understand unsupervised learning algorithms is that they look for ways to compress your data. If you had fifty (x,y) coordinates which all fall onto the line y = 3x+2, an unsupervised learning algorithm can compress those 100 numbers into fifty x-coordinates and a function. See how we've reduced the total datasize? If you've ever compressed an image or a word document, you've made use of an unsupervised learning technique. 

### Reinforcement Learning

Improvement through natural selection is the general idea of reinforcement learning. For some problems, success is measured by a distant goal, or by some cumulative performance. In these cases, it doesn't make sense to define individual state variables. Here is where reinforcement learning comes in. 

### Knowledge Base or Symbolic AI

Although other algorithms perform well enough, they don't gain any real "understanding" about what they're doing, at least, not in the same capacity as you and me. And when something does goes wrong, it's extremely difficult to identify the cause, especially when you're dealing with NN's that can have millions of weights. 

A knowledge base approach uses logic to make deductions. If I told it that a cat is a type of mammal, and that all mammals are animals, then it could deduce that a cat is a type of animal. These types of system are great for when we need to understand how the machine arrived at a decision. But because they operate on such an abstract level, building up the required database of statements is also a highly abstract task that relies on human input. Furthermore, many topics cannot be described with binary yes/no logic (things like the arts, personal opinions, relationships, etc.).





