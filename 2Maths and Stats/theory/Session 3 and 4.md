## Topics
Normal And Orthonormal Vectors
Vector Norm, Vector Space
Linear Combination, Linear Span
Linear Independence, Basis Vectors

## Normal and Orthonormal Vectors

Orthogonality
Two vectors are orthogonal to each other if their inner product equals zero.

Normal Vector
A normal vector (or unit vector ) is a vector of length 1. 
Any vector with an initial `length > 0` can be normalized by dividing each component in it by the vector’s length.

![[Pasted image 20250322051425.png]]

Orthonormal Vectors
Vectors of unit length that are orthogonal to each other are said to be orthonormal.

Gram-Schmidt Orthonormalization Process
The Gram-Schmidt orthonormalization process is a method for converting a set of vectors
into a set of orthonormal vectors.
Refer pg7 --> linalgWithSVD

## Vector Norm and Vector Space
- Vector Norms are defined as a set of functions that take a vector as an input and output a positive value against it.
- This is called the magnitude of a vector
- We can obtain different lengths for the same vector depending on the type of function we use to calculate the magnitude.

The Standard Norm Equation — P-norm
![[Pasted image 20250322052205.png]]

### L0 Norm
- count the number of non-zero elements in the given vector
![[Pasted image 20250322052730.png]]
### L1 Norm
Mean Absolute Error
- sum of mod of all elements
![[Pasted image 20250322052833.png]]

- When used to compute the loss, the L1 norm is also referred to as the Mean Absolute Error
- L1 norm varies linearly for all locations, whether far or near the origin.
### L2 Norm:
Euclidean distance /  Root Mean Squared Error
important

![[Pasted image 20250322053528.png]]

- The above equation is often referred to as the root mean squared error when used to compute the error.
- L2 norm measures the distance from the origin, also known as Euclidean distance.

### Squared L2 Norm
Mean Squared Error
L2 Norm but squared

![[Pasted image 20250322053827.png]]

- The above equation is often referred to as the mean squared error when used to compute the error in machine learning.
- The above equation is often referred to as the mean squared error when used to compute the error in machine learning.
- It is missing the square root.
- Within Machine Learning applications, the derivative of the Squared L2 Norm is easier to compute and store. The derivate of an element in the Squared L2 Norm requires the element itself. However, in the case of the L2 Norm, the entire vector is needed.

### Max Norm (or L-∞ Norm)
Max norm returns the absolute value of the largest magnitude element

![[Pasted image 20250322054612.png]]

refer -- Vector Norms

### Linear Combination, Linear Span

### Linear Combination
Let $$v_1, v_2, … , v_r$$ be vectors in `Rn`. A **linear combination** of these vectors is any expression of the form
$$k_{1}v_{1} + k_{2}v_{2}+ k_{3}v_{3} + \dots + k_{n}v_{n}$$

### Linear Span
The set of all linear combinations of a collection of vectors v1, v2,…, vr from Rn is called the span of { v1, v2,…, vr }. This set, denoted span { v1, v2,…, vr}, is always a subspace of R

Solve problems 
## Linear Independence and Basis Vectors

- necessary for determining the size of a vector space and finding solutions for optimization problems.

A set of vectors `{v1, v2, . . . , vn}` is linearly independent if the equation:
$$c_{1}v_{1} + c_{2}v_{2} + . . . + c_{n}v_{n} = 0$$

