---
layout: post
title: Machine Learning
permalink: /machineLearning/
mathjax: true
except_separator: <!--more-->
categories: algorithms
---

At its core, machine learning is a **statistical science**, and like most elements of statistics, a great deal of care must be taken when formatting and analyzing data. They way we chose to quantify abstract topics and/or measure error will have a significant impact on the quality of our result. 

<!--more-->

## Matrices

Before getting started - why do we care about matrices? Well, matrices are how we store data. So before we jump into neural networks, we can begin with techniques from linear algebra to extract data patterns.

**Vector** - By default, vectors are columns. The transpose/Hermitian of a vector turns it into a row. 

**Range/Span** - The set of all linear combinations of each vector. 

$$R\left(A\right)={\alpha_1A_1+a_2A_2\ldots+\alpha_kA_k,\ for\ any\ \alpha_i\in F}$$

**Nullspace/Kernel (of a matrix A)** - The set of all vectors [x] such that Ax = 0

$$N\left(A\right)={x\in F^n,\ Ax=0}$$

**Ortho-complement (of a subspace)** -  The set of all vectors [x] that are orthogonal to all vectors in the subspace V.

$$V^\bot={x,\ x\bot y\ for\ all\ y\in V}$$

**Linear Dependence** - A set of vectors are said to linearly dependent if there exist scalars $$\alpha$$ not all zero such that:

$$\alpha_1V_1+a_2V_2\ldots+\alpha_kV_k=0$$

**Rank** - The rank of a matrix is the is the number of linearly independent rows or columns. It is equal to the dimension of the span of the matrix. The rank cannot be greater than min(m, n) given $$A\in F^{m\times n}$$.

### Summary of Matrix Properties

| Name	        | Mathematical Expression	| Equivalent Statements/Other Properties
|-|:-|:-
|Normal Matrix  |	$$AA^H=A^HA$$       | [A] is normal if it commutes with its conjugate transpose
|		        |                       | [A] is diagonalizable by a unitary matrix
|               |                       | There exists a set of eigenvectors of [A] which form an orthonormal basis for range([A])
|               | $$\|A\|^2=tr(A^HA)$$        | The Frobenius norm can by computed by the eigenvalues
|               | $$A=Q\Lambda Q^H$$    | 
|               | $$AQ[:,i]=λiQ[:,i]$$  | [A] can be decomposed into the product of its unitary eigenvector matrices and a diagonal matrix of eigenvalues
| Unitary/Orthogonal Matrix	| $$AA^H=A^HA=I$$ |	[A] is unitary if it is normal and its product with its conjugate transpose equals the identity matrix
|                           | $$\|x\|_2=\|Ax\|_2$$      | The product of a unitary matrix with a vector does not change the magnitude of the vector.
| Symmetric/Hermitian Matrix    |	$$A=A^T$$   | [A] is symmetric if it is equal to its conjugate transpose
|                               |           | All symmetric matrices are also normal matrices
|                               |           | Rectangular matrices are never normal matrices
|                               |           | The eigenvalues of a symmetric (and thus normal) matrix are always real |
| Diagonalizable Matrix	| $$A=Q\Lambda Q^H$$ |	[A] is diagonalizable if it is similar to a diagonal matrix

 
### Singular Value Decomposition

The singular value decomposition of a matrix [A] yields the following expression, where  U\in F^{m\times m} is the matrix of left singular vector, V\in F^{n\times n} is the matrix of right singular vectors, and the strictly positive entries of \Sigma\in F^{m\times n} are referred to singular values. The number of nonzero singular values equals the rank of [A]. Both U and V are unitary matrixes.

$$A\in F^{m\times n}=U\Sigma V^H$$

Realizing that in some cases, the rank of A is less than either m or n, leaving a few zero entries along the singular values. These send corresponding vectors in U and V to zero, and thus A can be reassembled with only the vectors of U, V and singular values through (r). 

$$A=\ \sum_{i=1}^{r}{\sigma_iu_iv_i^H}$$


#### Additional Properties of the SVD

|$$Av_j=\sigma_ju_j\ \ \ \ \ \ if\ j\in\left(1,r\right)$$
|$$Av_j=\sigma_ju_j=0\ \ \ \ \ \ \ \ if\ j\in(r+1,\ n)$$
|$$A^Hu_j=\sigma_jv_j\ \ \ \ \ \ \ \ if\ j\in(1,\ r)$$
|The right singular vectors of AH are the left singular vectors of A and vice-versa
|The dimension of the range of A is equal to the rank of A
|$$u_1,u_2,\ldots u_r$$ are orthogonal basis vectors for the range of A
|$$u_{r+1},u_{r+2},\ldots u_m$$ are orthogonal basis vectors for the orthocomplement of the range of A
|$$v_{r+1},v_{r+2},\ldots u_n$$ are orthogonal basis vectors for the nullspace of A
|$$v_1,v_2,\ldots v_r$$ are orthogonal basis vectors for the orthocomplement of the nullspace of A


### Orthogonal Projection Matrix 

Consider a set of vectors $$v_1,\ v_2,\ \ldots v_k$$ which form an orthonormal basis for the subspace of some range V. The orthogonal projection matrix of the subspace V as well as the orthocomplement of V is formed as:

$$P_v=Q_kQ_k^H$$

$$P_{v^\bot}={I-Q}_kQ_k^H$$

The orthogonal projection matrix when multiplied by a vector finds the projection of that vector onto the subspace and is equal to subtraction of any orthogonal components from the original vector. That is:

$$P_{v^\bot}x=x-P_vx$$


### Pseudo-Inverse (Moore-Penrose Inverse)

Note that a non-square matrix cannot be inverted in the traditional sense. However, it is still possible to achieve a partial inverse by using the SVD. We define the pseudo inverse as:

$$A^+=V\Sigma^+U^H$$

$$\Sigma^+=\left[\begin{matrix}\Sigma_{r\times r}&0_{r,\ n-r}\\0_{m\times r,\ r}&0_{m-r,\ n-r}\\\end{matrix}\right]\ \in F^{n\times m}$$

### Least Squares Regression/Ordinary Least Squares

Given a problem stated in the following format, it is possible to find an exact solution.

$$x_{LS}=argmin\|Ax-b\|_2^2$$

$$x_{LS}=A^+b$$

Thus, we may be generally motivated to format our problems in the above format, such that a solution can be easily solved using the pseudo-inverse. Consider a dataset of inputs and corresponding outputs, denoted as t and b.

Our approximation function we would like to take the form:

$$b_j=c_1+c_2t_j+c_3t_j^2+ \ldots α_1cos(t_j)+β_1sin(t_j)+α_2cos(t_j)+β_2sin(t_j)+ \ldots$$

This can be represented in a linear format by defining the following sets of A and x matrices.

$$x=\ \left[c_1,\ c_2,c_3,\ldots,\ \alpha_1,\beta_1,\alpha_2,\beta_2,\ \ldots\right]^T$$

$$A_j=[1,\ t_j,\ t_j^2, \ldots,\cos(t_j),\sin(t_j),\cos(t_j),\sin(t_j)]$$

Thus, the dot product of x with Aj should yield Equation 1. Repeating the above for every data point will yield a full matrix for A. The coefficients for our model equation which best fit the data can be found now using least squares regression.


### Regularized Least Squares

Consider for a moment, a constrained least squares problem:

$$x_{LS}=argmin\|Ax-b\|_2^2$$

$$\|Dx\|_2<τ$$

As we did in optimization, we can include the constraint, as something that should be included in the weighting of the objective function. 

$$x_{LS}=argmin\|Ax-b\|_2^2+λ^2\|Dx\|_2^2$$

We can be reformed into our classic least squares problem format by defining the following sets of matrices:

$$\widetilde{A}=\left[\begin{matrix}A\\\lambda D\\\end{matrix}\right],\ \widetilde{b}=\left[\begin{matrix}b\\0\\\end{matrix}\right]$$

$$x_{LS}=argmin\|Ax-b\|_2^2$$


### First Difference Matrix

The first difference matrix when multiplied by a vector yields the elementwise gradients (taking the spacing/index to be the x displacement).

$$D=\ \left[\begin{matrix}-1&1&0&0&0\\0&-1&\cdots&0&0\\0&\vdots&\ddots&\vdots&0\\0&0&\cdots&-1&1\\1&0&0&0&-1\\\end{matrix}\right]$$


### Trace of a Matrix

The trace of a matrix is defined as the sum of values down the primary diagonal. The trace is invariant under cyclic permutation:

$$tr\left(AB\right)=tr\left(BA\right)$$

$$tr\left(A+B\right)=tr\left(A\right)+tr\left(B\right)$$


### Frobenius Norm

The Frobenius norm of a matrix is the root of the sum of the square of all values. The frobenius norm is also equal to the square root of the trace, and the sum of square of singular values of A. 

$$\|A\|_F = a_{ij}^2$$

$$\|A\|_F^2=tr(AA^H)=tr(A^HA)=σ_i^2$$


### Principal Component Analysis

Consider a matrix whose columns represent different items in a dataset, and whose rows represent different parameters for each data item (i.e. x, y, z, coordinates). Principal Component Analysis, or PCA, finds an orthonormal basis of directions which best fit the data. These lines minimize the average squared distance of each point to the line. This orthonormal basis are also the left singular vectors obtained through SVD.

The first principal component of a matrix A, associated with the first eigenvector/left singular vector of the eigen decomposition and SVD, can be found as the vector which maximizes the second norm of the product of A with x. 

$$u_1=\ argmax\|Ax\|^2)$$

The next largest principal component can be found by projecting A into the null space formed from the previously found vectors and repeating the previous calculation. (We are finding the next line of best fit that is orthonormal to any previously found lines).


### Independent Component Analysis

ICA decomposes a signal into independent (non-correlated) non-Gaussian signals. When sources are statistically independent, ICA works very well in separating the two. ICA methods tend to breakdown when there is similarity in the signal, leading to correlation. To do this, ICA identifies directions that maximize absolute kurtosis. Mathematically, this is:

$$x=\ argmax(|k_4(x^TA)|)$$

Where Kurtosis, or fourth central cumulant, is defined as:

$$k_4(y^T)=\frac{1}{n}\sum y_i^4- 3(\frac{1}{n} \sum y_i^2)^2$$

And in addition, subject to a spherical constraint on the x input (i.e., two norm of x is equal to 1).

$$\|x\|_2^2=1$$

## Machine Learning Algorithms

Now we can finally get to more modern approaches to machine learning. Current methods fall into three main categories:

1. Supervised Learning
2. Unsurpervised Learning
3. Reinforcement Learning

### K-Means Clustering

Minimizes the intra-cluster variance. The strength of clustering algorithms lies in the fact that it is an unsupervised learning method, i.e., data does not have to come pre-labeled. The process goes:

1. Propose N cluster centers. 
2. Assign every pixel to the closest cluster center. 
3. Calculate new cluster centers using the average of assigned pixels. 
4. Repeat until centers have stabilized.

For data classification, there typically needs to be as many dimensions as independent features (N) we’d like to distinguish. This means that for a task like image classification, we’ll need to find a way to transform a 2D image into a single point in 2D dimensional space. 

### Neural Networks and Deep Nets

Networks are function approximators. Each node consists of any number of inputs and any number of outputs, but is itself a simple activation function (relu, sigmoid, tangent, etc.) These functions generally produce an output in the range of 0 to 1 or -1 to 1. For each node, there are a series of weights and offsets to be calculated/tuned by the learning process.
 
![deep neural net](../images/dnn.png){: .center-image }

The benefit of Deep nets is that they can separate non-linear shapes, at the downside of long computation times and unreliable convergence of results. Results depend a lot on how error is measured, the function of each node, etc.


### Receiver Operator Characteristic Curve

The R.O.C plots the probability of correct classification vs the probability of false positive. In an ideal case, the area under the curve will be equal to 1. A random guesser achieves a straight line on this plot, so a classifier needs to beat this result. Placement along the curve is also important, and changes depending on the application.	

![roc curve](../images/roc.png){: .center-image }
 

### Procrustes Analysis

A method for statistical analysis of shape distributions. An orthogonal Procrustes problem is one that finds the optimal rotation, translation, and/or reflection which aligns two shapes.


