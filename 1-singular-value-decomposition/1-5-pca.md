p23-28

The method of Principal Component Analysis:

1. Pre-process data with mean subtraction.
2. Set variance to unity (setting the variance equal to 1)
3. Performing the SVD: leaves us with a coordinate system of orthogonal, (unrelated to eachother) components that have maximal correlation with measurements.

Let a matrix $X$ (of $n \times m$) contain features as columns and observations or measurements as rows.

The mean, $\bar x$ is:

$$\begin{align}\bar x_j = \frac{1}{n} \sum^{n}_{i=1} X_{ij}\end{align}$$

The mean matrix is:

$$\begin{align}\bar X = 
\begin{bmatrix}
1 \\
... \\
1 \\
\end{bmatrix}
\bar x\end{align}$$

Where the matrix above is the matrix of ones. I found this notation confusing, [here](https://math.stackexchange.com/questions/3507918/subtracting-the-mean-from-every-row-of-a-matrix) is a good derivation of why the above operation works.

The mean subtracted data is given by:

$$B = X - \bar X$$

And the covariance of B is:

$$C = \frac{1}{n-1}B * B$$

Where the * denotes matrix multiplication, not complex operation.

The principal components are the eigenvectors of $C$, where each $C_{ij}$ quantifies the correlation of the $i$ and $j$ features across all experiments. We can find the eigenvector matrix, $V$ with:

$$CV = VD \\
C = VDV^* \\
D = V^*CV$$

This ties back to our SVD definition, as the columns of $V$ are the principle components and the elements of diagonal matrix $D$ are the variances of the data, also defining the coordinates of $C$.

With our definition of:

$$B = U \Sigma V^* \\
C = \frac{1}{n-1} B * B = \frac{1}{n-1} V \Sigma^2 V^* \\
D = \frac{1}{n-1} \Sigma^2$$

This relates the diagonal elements, $\lambda_k$ of $D$ to the singular values:

$$\begin{align}\lambda_k = \frac{\sigma_k^2}{n-1}\end{align}$$

Where we can again keep the first r number of singular values for an approximation.
This is therefore a very useful tool for finding the principal components of a dataset.