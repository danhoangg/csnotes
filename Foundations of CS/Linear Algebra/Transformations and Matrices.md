Subjects/ Topics: #Matrices #LinearAlgebra #Transformations

How do you change bases on a vector?

Say we have coordinates $(\alpha, \beta)^T$ given in the with bases $\vec{b_1}=\begin{pmatrix}2\\1\end{pmatrix}, \vec{b_2}=\begin{pmatrix}-1\\1\end{pmatrix}$
$\therefore \alpha\vec{b_1} + \beta\vec{b_2} = \alpha\begin{pmatrix}2\\1\end{pmatrix}+\beta\begin{pmatrix}-1\\1\end{pmatrix}$
$=\begin{pmatrix}2\alpha-\beta\\\alpha+\beta\end{pmatrix}$
$=(2\alpha-\beta)\vec{e_1} + (\alpha+\beta)\vec{e_2}$ 

Instead we can write this as a matrix operation
$\begin{pmatrix}2&-1\\1&1\end{pmatrix}\begin{pmatrix}\alpha\\ \beta\end{pmatrix} = \begin{pmatrix}x\\y\end{pmatrix}$

So the matrix M transforms the language of the original coordinate system in the new coordinate system
$$\begin{align}M\begin{pmatrix}\alpha\\ \beta\end{pmatrix} &= \begin{pmatrix}x\\y\end{pmatrix}\\\begin{pmatrix}\alpha\\ \beta\end{pmatrix} &= M^{-1}\begin{pmatrix}x\\y\end{pmatrix}\end{align}$$
### Orthonormal Basis

Remember that  $$\langle\vec{v_i},\vec{v_j}\rangle=\delta_{ij}=\left\{\begin{matrix}1\; i=j\\ 0\; i\neq j\end{matrix}\right.$$
Suppose we have a vector $v=(1,2,3)^T$ and we want to find the coordinate for the first canonical basis vector $e_2$ 
$\langle \vec{v}, \vec{e_2}\rangle =1\times0 + 2\times1 + 3\times0 = 2$
Therefore the answer is 2

More generally:
### $\vec{v} = \sum_i v_i \vec{e_i}$
$\begin{align} \langle \vec{v}, \vec{e_j}\rangle &= \langle\sum_i v_i\vec{e_i},\vec{e_j}\rangle \\ &= \sum_i v_i\langle\vec{e_i},\vec{e_j}\rangle \\ &= \sum_i v_i \delta_{ij} \\ &= v_j \end{align}$ 

- For orthonormal basis scalar product of vector with jth basis vector projects out coordinate j of a vector v

#### Transforming Matrices

- Matrices are coordinate representations of linear maps
- We know how to get matrix representations in the canonical bases

Let coordinates $(\alpha,\beta)^T$ be coordinates in basis B and we have a matrix in the canonical base: $$\begin{align} &\begin{pmatrix}\alpha\\\beta\end{pmatrix}\;\;\;\;\;\text{Start with vector in system B}\\M&\begin{pmatrix}\alpha\\\beta\end{pmatrix}\;\;\;\;\;\text{Calculate it's coordinates in canonical base} \\AM&\begin{pmatrix}\alpha\\\beta\end{pmatrix}\;\;\;\;\;\text{Calculate matrix operation in canonical base}\\ M^{-1}AM&\begin{pmatrix}\alpha\\\beta\end{pmatrix}\;\;\;\;\;\text{Calculate coordinates back in original system} \end{align}$$
So we can say $A_B=M^{-1}AM$
