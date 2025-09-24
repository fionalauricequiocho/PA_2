## Programming Assignment 2 – NumPy

## Summary

This repository contains solutions to programming experiments involving NumPy arrays.
The goal is to apply NumPy operations for:

Creating and reshaping arrays

Normalizing data

Filtering elements based on conditions

The problems included are:

Normalization Problem – Generate a random matrix and normalize it.

Divisible by 3 Problem – Generate squares of integers, reshape into a matrix, and extract values divisible by 3.

## Problem Descriptions and Solutions

## 1. Normalization Problem

Problem:
Create a random 5×5 NumPy array, compute its mean and standard deviation, normalize the array, and save the result as a .npy file.

Code Snippet:

<pre>
import numpy as np

X = np.random.random((5, 5))
X

mean_X = X.mean()
mean_X

std_X = X.std()
std_X

X_normalized = (X - mean_X) / std_X
X_normalized

np.save("X_normalized.npy", X_normalized)
</pre>

Explanation:

np.random.random((5,5)) → generates a 5×5 array of random values between 0 and 1

.mean() and .std() → compute the mean and standard deviation

Normalization formula:

𝑋
𝑛
𝑜
𝑟
𝑚
𝑎
𝑙
𝑖
𝑧
𝑒
𝑑
=
𝑋
−
𝜇
𝜎
X
normalized
	​

=
σ
X−μ
	​


np.save() saves the normalized array in .npy format.

Example Output (sample values):

Mean of X: 0.4931
Standard Deviation of X: 0.2846
Normalized X:
 [[-1.05  0.24 ...]
  [ 0.76 -0.43 ...]]

## 2. Divisible by 3 Problem

Problem:
Create a 10 x 10 ndarray with the squares of the first 100 positive integers, then determine the elements divisible by 3, and lastly save as div_by_3.npy

Code Snippet:
<pre> 
import numpy as np

numbers = np.arange(1, 101)  # integers 1 to 100

A = numbers**2
A

A = A.reshape(10, 10)
A

div_by_3 = A[A % 3 == 0]
div_by_3 


np.save("div_by_3.npy", div_by_3)
 </pre>

Explanation:

np.arange(1, 101) → generates integers 1 to 100.

numbers**2 → squares each integer.

.reshape(10, 10) → reshapes into a 10×10 matrix.

A[A % 3 == 0] → filters elements divisible by 3.

np.save() → stores the result in .npy format.

Example Output (sample values):

10x10 ndarray of squares:
 [[   1    4    9 ...]
  ...
  [9604 9801 10000]]

Elements divisible by 3:
 [  9  36  81 144 225 ... 9801]

## Libraries Used

NumPy – for array creation, reshaping, random generation, mathematical operations, and saving .npy files.

## Conclusion

Through this exercise, I learned how to:

Generate and manipulate arrays using NumPy.

Apply statistical operations like mean and standard deviation.

Normalize data using vectorized operations.

Reshape arrays and filter elements based on conditions.

Save results for later use with .npy files.
