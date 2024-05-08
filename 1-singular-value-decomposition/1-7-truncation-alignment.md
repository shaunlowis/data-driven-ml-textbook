p35-40

## Truncation
The singular values outputted by our SVD operation can be truncated, by applying the SVD
at a rank _r_, that captures 90-99% of the variance or energy of the system. Another approach,
often used in machine learning, is a hard set threshold $\tau$. Recently, a optimal truncation
value method has been defined. It assumes gaussian white noise in the sample. The derivation and
conditions are on p35-36, for known, unknown noise, square and rectangular matrices.

## Data alignment
The SVD is sensitive to rotations and translations in its data. See 1-7-example.ipynb.
It is fundamentally geometric, depending on the coordinate system of the data. Great care must
be taken to preserve dimensionality and maintain invariance to rotation in the dataset.