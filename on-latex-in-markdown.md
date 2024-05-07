## Formatting LaTeX to render on GitHub

The markdown LaTeX rendering is different on Github/GitLab,
here's a summary of getting things to work nicely:

1. Basic equations:

```
Wrap the text in dollar signs like so;

$$Ax = B$$

Note: don't leave space between the '$$' delimiters and the expression.
```

$$Ax = B$$

2. Multi-line, numbered equations:

```
Wrap the text in dollar signs, add '&' alignment character before '=';

$$\begin{align}Ax &= B \\
c*Ax &= c*B \\
\end{align}$$

Note: don't leave space between the '$$' delimiters and the expression.
```

$$\begin{align}Ax &= B \\
c*Ax &= c*B \\
\end{align}$$

3. Multi-line, non-numbered equations:

```
Omit the align environment and '&' alignment characters;

$$Ax &= B \\
c*Ax &= c*B \\$$
```

$$Ax = B \\
c*Ax = c*B \\$$

4. Matrices:

```
Use the \bmatrix{} environment:

$$X = 
\begin{bmatrix}
| & | & | & |\\
x_1 & x_2 & ... & x_m\\
| & | & | & |
\end{bmatrix}$$
```

$$X = 
\begin{bmatrix}
| & | & | & |\\
x_1 & x_2 & ... & x_m\\
| & | & | & |
\end{bmatrix}$$