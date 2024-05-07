# Overview

- The SVD is a matrix decomposition. 
- It determines a low-dimensional approximation to high-dimensional data in terms of dominant patterns.
- It is numerically stable, guaranteed to exist and represents dominant correlations in the data.
- The coordinate system of the SVD is in terms of the aforementioned data correlations. 
- It can be used to find the pseudo-inverse of non-square matrices and solutions to $Ax = b$.

## Definition

Let a large data set 

$$X \in \mathbb{C}^{n\times m} \\$$

Where columns $x_k \in \mathbb{C}^n$ are: 

$$X = 
\begin{bmatrix}
| & | & | & |\\
x_1 & x_2 & ... & x_m\\
| & | & | & |
\end{bmatrix}$$

Where the columns denote vectors, which can be from time series or other data. Hence their rows contain degrees of freedom or measurements.

The decomposition exists for every complex-valued matrix:

$$X = U \Sigma V^* \\
\text{where: } U \in \mathbb{C}^{n\times n}, \\
V \in \mathbb{C}^{m\times m}, \\
Sigma \in \mathbb{R}^{n\times m}$$

And U, V are unitary, satisfying 

$$UU^* = U^*U = I$$

for $^*$ denoting the conjugate transpose and $\Sigma$ as real with non-negative diagonals and zeroes elsewhere.

When $n \ge m$, the matrix $\Sigma$ has at most $m$ non-zero diagonal elements; take the $n=1, m=2$ case of:

$$\begin{align}
\Sigma = 
\begin{bmatrix}
\hat \Sigma \\
0
\end{bmatrix}
\end{align}$$

so substituting, we get the economy SVD;

$$\begin{align}
X &= U \Sigma V^* \\
&= 
\begin{bmatrix}
\hat U & \hat U^{\perp}
\end{bmatrix}
\begin{bmatrix}
\hat \Sigma \\
0
\end{bmatrix}
 V^* \\
&= \hat U \hat \Sigma V^*
\end{align}$$

## Computation
The exact solution method for computing the SVD is not too important. Here is a python
implementation:

```
import numpy as np
X = np.random.rand(5, 3) # create random data matrix.
U, X, VT = np.linalg.svd(X, full_matrices=True) # Full SVD.
Uhat, Shat, VThat = np.linalg.svd(X, full_matrices=False) # Economy SVD
```

We will use the SVD for dimensionality reduction extensively.