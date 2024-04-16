The SVD provides an optimal low-rank approximation to a matrix $X$.
Due to providing a hierarchy of low-rank approximations, we can express
the SVD $X$ as a sum of these approximations:

$$
X = \sum^m_{k=1} \sigma_k u_k v_k^* = 
\sigma_1 u_1 v_1^* + 
\sigma_2 u_2 v_2^* + 
... + \sigma_m u_m v_m^*
$$

Due to the hierarchical property of the SVD, these entries; 
which denote the $k\text{th}$ columns of their matrices $U, \Sigma, V^*$, are
arranged in decreasing order. This is the dyadic summation, where each subsequent rank-one matrix in the sequence captures less information in $X$.

Thus we can approximate by truncation by ending the sequence at some rank $r$:

$$
X \approx \tilde X= \sum^r_{k=1} \sigma_k u_k v_k^* = 
\sigma_1 u_1 v_1^* + 
\sigma_2 u_2 v_2^* + 
... + \sigma_r u_r v_r^*
$$

## Optimal approximation and error bounds
Here we specify the optimal approximation to a matrix $X$, at some rank $r$.
The mathematics here aren't too necessary for our use, but refer to pages 8-10 for derivations and the exact theorem. Suffice it to say, we have definitions for:

- Optimal approximation of X (Theorem 1.1, eq 1.6, p 9).
- Exact error of the rank r approximation (eq 1.7, p 9).
- Relative error of the rank r approximation (eq 1.8, p 9).

## Example; Image Compression
See `1-2-example.py`.