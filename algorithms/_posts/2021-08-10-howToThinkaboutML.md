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

Before going further, it's worth mentioning that many machine learning algorithms are built using optimization. There is almost always something to be optimized (an objective function - error, fitness, etc.), and different ways to run the optimization (genetic, linear, quadratic, etc.). Different algorithms may change the problem, but the name of the game remains the same (for example, the "learning rate" and "search step size" refer to the same thing!) Keep this mind, because it helps to simplify this large field. 

For any machine learning algorithm, we should be able to identify three distinct aspects:
1. **The architecture**, or relationship between inputs and ouputs, which influences the
2. **Cost function**, which we minimize by using different
3. **Optimization techniques**.

For a more mathematical discussion of machine learning algorithms, check out the [original ML post]({% post_url /algorithms/2022-03-30-machineLearning %})!

### Supervised Learning

When we know the type of output you want, but need to learn the function that will get us there, we use supervised learning. These algorithms are implemented with deep neural networks, and are useful for classification tasks. As the name implies, this method absolutely requires having a labeled dataset. If your problem doesn't readily accept labels, this strategy will probably fall short. Try instead to identify if *parts* of the solution involve identification. 

### Unsupervised Learning

Unsupervised learning algorithms discover patterns in your data. Note that these algorithms are NOT classification algorithms. Instead, they tell you what the likely categories are. In this sense, they are a lot like the statistical regression methods you may have have encountered in high school. Depending on the structure of your data, there are many different strategies which fall under this umbrella, such as:

* K-means Clustering
* Singular Value Decomposition
* [Independent Component Analysis]({% post_url /algorithms/2022-03-30-machineLearning %})
* Autoencoders

Another way to understand unsupervised learning algorithms is that they look for ways to compress your data. If you had fifty (x,y) coordinates which all fall onto the line y = 3x+2, an unsupervised learning algorithm can compress those 100 numbers into fifty x-coordinates and a function. See how we've reduced the total datasize? If you've ever compressed an image or a word document, you've made use of an unsupervised learning technique. 

A really cool outcome we get from unsupervised learning is the ability to generate new examples from the underlying principles that we've discovered, also known as generative modeling. 


### Generative Adversarial Modeling

A generative adversarial model, or GAN, is a method to train a generative modeling algorithm. GAN's consist of two parts - a generative modeling program to create plausible examples, and a supervised learning/classification program that tries to distinguish the fake ones from the real ones. They are trained against one another (hence adversarial), until the classifier is no longer able to distinguish between the two. 


### Representation Learning or Feature Learning

Unsupervised learning differentiates algorithms by the data. Representation learning differentiates algorithms by their goals. Many unsupervised learning algorithms are also representation learning algorithms and vice versa, but there is not a perfect overlap. 

Here's an example. We wish to write a program to classify flowers. Using a clustering approach, we might make measurements of the flower color or petal size and shape. K-means clustering would return the averages for each class. While we do find the averages, the properties were pre-defined. 

If we linearized the pixels of each image (n by m), we'd end up performing clustering in ($$n \times m$$) space, which is computationally expensive. 

So how can we get a machine to learn features? Well, when we perform supervised learning with something like a deep neural net, the last hidden layer before the output can actually be a set of features. 

Or in an unsupervised case, independent component analysis and autoencoders achieve this goal by looking for ways to represent the most original information in the fewest variables. The singular value decomposition and eigenvalues are two methods that do this. 

> Consider the example of rotations. A rotation matrix in 3D is a 3x3 matrix, for a total of nine variables. But it turns out that any rotation in 3D can be represented by only three Euler angles (Roll Pitch Yaw). If we have those three numbers, we can follow a specific set of rules to reconstruct the original object. In this way, the Euler angles can be thought of as "features" of the rotation matrix. 


### Reinforcement Learning

Improvement through natural selection is the general idea of reinforcement learning. For some problems, success is measured by a distant goal, or by some cumulative performance. In these cases, it doesn't make sense to define individual state variables. Here is where reinforcement learning comes in. 

### Knowledge Base or Symbolic AI

Although other algorithms perform well enough (i.e. the output is good), they don't gain any real "understanding" about what they're doing, at least, not in the same capacity as you or me. And when something does goes wrong, it's extremely difficult to identify the cause, especially when you're dealing with NN's that can have millions of weights. 

A knowledge base approach uses logic to make deductions. If I said that a cat is a type of mammal, and that all mammals are animals, then it could be deduced that a cat is a type of animal. These types of system are great for when we need to understand how the machine arrived at a decision. But because they operate on such an abstract level, building up the required database of statements is also a highly abstract task that relies on human input. Furthermore, many topics cannot be described with binary yes/no logic (things like the arts, personal opinions, relationships, etc.).





