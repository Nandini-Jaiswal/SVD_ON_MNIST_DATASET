# **SINGULAR VALUE DECOMPOSITION ON MNIST DATASET**
Here we shall explore how SVD is performed using only top 4 left singular vectors. We shall use the MNIST dataset for this experiment.

## Overview

This repository contains the code for a problem statement, which explores the application of Singular Value Decomposition (SVD) to an image classification problem using the MNIST dataset.

## Dataset

The MNIST dataset is a large collection of handwritten digits, commonly used for benchmarking machine learning algorithms. It contains 70,000 images, each of size 28x28 pixels, representing digits from 0 to 9. The dataset is already divided into training and testing sets.

## Objectives

1. **Forming Matrices**:
    - For each digit \(i\), form a matrix whose columns are images of that digit (excluding the label). 
    - Each matrix should have exactly 784 rows (28x28 pixels) and can have either all or a fixed number \(N\) of columns for each digit.

2. **Matrix Rank**:
    - The 10 matrices formed above are generally not of full rank. For instance, the matrix \(D_5\) contains images labeled 5 and spans a subspace $$D(5) \subset \mathbb{R}^{784}$$

3. **Extracting Singular Vectors**:
    - For each matrix \(D(n)\), extract the first 4 left singular vectors (principal components).
    - Print 5 images for each digit: one from the training dataset and four from the left singular vectors reshaped into 28x28 images.

4. **Classification Model**:
    - Develop a model that computes the minimum norm $$\(\rho_n(z) := \min ||D(n)x - z||\)$$ for a test image vector \(z\), where \(n\) is a digit between 0 to 9.
    - Use a low-rank approximation of the factorization, specifically the first 4 columns of \(U\), for efficiency.

5. **Training and Testing**:
    - Use between 2500-3000 images of each digit in the training set to form the matrices.
    - Use the remaining images as labeled test images.

## Output

The final output includes:

- 50 images: one original image and 4 images corresponding to the left singular vectors for each digit.
- The exact expression used in the classification and justification for its use.
- The confusion matrix and efficiency results.
