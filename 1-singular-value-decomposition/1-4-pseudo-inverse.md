p16-23

The SVD acts as a solution to the classic

$$
Ax = b
$$

by finding the least-squares solution. Care must be taken
in this application as this is only true when the SVD captures all non-zero singular values, otherwise it is just an approximation.

See (1.27) to (1.29b) for specifics and conditions to this application.
An application of this method is shown in  1-3-example.py

When applying this method, the _condition number_ measures the sensitivity
to errors in the input. It is found with:

$$
\kappa (A) = \frac{\sigma_{max} (A)}{\sigma_{min} (A)}
$$

NOTE: these $\sigma$ refer to singular values, not standard deviations.