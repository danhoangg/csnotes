Subjects/ Topics: #LinearAlgebra #Vectors #Matrices 

Eigen-analysis is an important concept in science
- We can often only solve linear systems
- These can be "broken down" into it's constituent parts, analyse these parts and then put them back together to get the full picture, these parts are eigenvectors

**Example**
Say we have a matrix A where $$A=\begin{bmatrix}1&2&1\\6&-1&0\\-1&-2&-1\end{bmatrix}$$
And we want to find $A^{100}$, torture to do by hand and computationally expensive for a computer

Matrices are coordinate representations of linear transformations, will generally turn a vector $\vec{v}$ into $\vec{v'}$ which sometimes point in a different direction.
Matrices that don't change the direction of a vector means that applying the same matrix repeatedly scales with the number of matrices applied: $A\vec{v}=\lambda\vec{v}$ 

Lets take a look at $$A=\begin{bmatrix}1&0&0\\0&-6&0\\0&0&-3\end{bmatrix}$$
$A^{100}$ is easy to compute here as the direction doesn't change:$$A^{100}=\begin{bmatrix}1^{100}&0&0\\0&(-6)^{100}&0\\0&0&(-3)^{100}\end{bmatrix}$$
This is our strategy, if we can find vectors that are only scaled by A and then transform into A into a new basis defined by these vectors

We need to solve $$\begin{align} A\vec{v}&=\lambda\vec{v} \\(A-\lambda I)\vec{v}&=0 \end{align}$$
Such solutions can only exist if $\det{(A-\lambda I)}=0$ and so therefore we need to solve that

**Example**
Find the eigenvalues of $A=\begin{bmatrix}1&1\\6&2\end{bmatrix}$ $$(A-\lambda I) = \begin{bmatrix}1-\lambda&1\\6&2-\lambda \end{bmatrix}$$
$$\begin{align}\text{det}(A-\lambda I) &= 0 \\ (1-\lambda)(2-\lambda)-6 &= 0 \\ \lambda^2-3\lambda -4&=0 \\\lambda_1=4,\;\lambda_2=-1 \end{align}$$
4 and -1 are our eigenvalues
If we sub in 4 and -1 we can obtain our eigenvectors
$$\lambda=4:\;\;\;\;\;\begin{bmatrix}-3&1\\6&-2\end{bmatrix}\begin{bmatrix}x\\y\end{bmatrix}=0$$ $$\begin{align}-3x +y=0 \\ 6x-2y=0 \\y=3,\;\;x=1 \end{align}$$
$\therefore \vec{v_1}=\begin{pmatrix}1\\3\end{pmatrix}$
And by subbing $\lambda=-1$ we can obtain $\vec{v_2}=\begin{pmatrix}1\\-2\end{pmatrix}$ 
#### Recipe for getting Eigenvectors and eigenvalues:
- Find the characteristic polynomial $\text{det}(A-\lambda I)$
- Solve to get $\lambda$ values/ eigenvalues
- Sub in $\lambda$ values to get the eigenvectors

Remember to transform into different bases $$A'=MAM^{-1}$$
So lets transform into a new base spanned by v1 and v2 where A' scales by factors given by the eigenvalues, $\lambda_1,\lambda_2$
$$A=M\begin{bmatrix}\lambda_1&0\\0&\lambda_2\end{bmatrix}M^{-1}$$
$$\therefore A^2=M\begin{bmatrix}\lambda_1&0\\0&\lambda_2\end{bmatrix}M^{-1}M\begin{bmatrix}\lambda_1&0\\0&\lambda_2\end{bmatrix}M^{-1} = M\begin{bmatrix}\lambda_1&0\\0&\lambda_2\end{bmatrix}\begin{bmatrix}\lambda_1&0\\0&\lambda_2\end{bmatrix}M^{-1} = M\begin{bmatrix}\lambda_1^2&0\\0&\lambda_2^2\end{bmatrix}M^{-1}$$
$$\implies A^{100} = M\begin{bmatrix}\lambda_1^{100}&0\\0&\lambda_2^{100}\end{bmatrix}M^{-1}$$
**What are the uses of eigenvectors and eigenvalues then?**
- Transformed a complicated matrix into eigenbasis spanned by eigenvectors
- In eigenbasis, matrix has a simple action scaling of vectors by eigenvalues
- Perform calculations in eigenbasis
- Transform back
Depending on whether we find an eigenbasis

- A matrix A is called diagonizable if an invertible matrix M exists such that $M^{-1}AM$ is a diagonal matrix
- If $B=M^{-1}AM$ then A is similar to B
- If A is a $n\times n$ matrix and if the sum of the dimensions of its eigenspaces are equal to n then A is diagonalizable 

