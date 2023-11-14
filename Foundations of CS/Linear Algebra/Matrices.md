Determinant of a 2x2 and 3x3 as well as inverse

Some interesting determinant rules:
- $|A| = |A^T|$
- $|AB| = |A||B|$
- Matrix is not invertible if |A| = 0
- $|A^{-1}| = |A|^{-1}$

Even more interesting rules:
Suppose A and B are both nxn square matrices
- If B is obtained by switching 2 rows in A, then $|B|=-|A|$
- If B is obtained by adding 2 rows in A, then $|B|=|A|$
- If B is obtained by multiplying a row in A by a scalar b, then $|B| = b|A|$
**Example**
$$\therefore \det\begin{bmatrix}0&-1&0\\1&0&0\\0&1&1\end{bmatrix}=-\det\begin{bmatrix}1&0&0\\0&-1&0\\0&1&1\end{bmatrix}=-\det\begin{bmatrix}1&0&0\\0&-1&0\\0&0&1\end{bmatrix}=1$$
Instead of computing cofactors, we can gaussian eliminate, and use the rules thats just been stated to get to transform a matrix to a triangular shape.

**Cramer's rule**

The inverse of a matrix is equal to the transposed matrix of cofactors divided by the determinant $$A^{-1}=\frac{C^T}{\det{A}}$$