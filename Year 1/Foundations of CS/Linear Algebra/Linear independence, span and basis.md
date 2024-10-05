Subjects/ Topics: #LinearAlgebra #Vectors #Matrices 

**Linear Algebra:**
- Vectors
- Gaussian elimination
- Matrices applied on vectors is a linear equation
	- Can be used to enlarge, rotate, shears

#### Linear Independence

- Addresses the "not having too many" requirement 
- A set of vectors {v1, v2, v3} is **linearly dependant** if at least one of the vectors can be expressed as a linear combination of the other vectors  $$v=\sum_{i\neq 1}a_iv_i,\;a_i\neq0,i>1$$
- Otherwise it is linearly independent
**Example**

$v_1=\begin{bmatrix} 2\\1\\1 \end{bmatrix},v_2=\begin{bmatrix} 4\\2\\1 \end{bmatrix},v_3=\begin{bmatrix} 1\\1\\0 \end{bmatrix}$

$2=4\alpha_2 + \alpha_3 \implies 2=3$
$1=2\alpha_2 +\alpha_3 \implies \alpha_3=-1$
$1=\alpha_2$

2 = 3 is wrong therefore linearly dependant because there is no solution

- Equations of the form $A\vec{x}=0$ are called **homogenous** equations
- Zero vector is always the solution
- Solutions of the form $\vec{x}\neq0$ are **non-trivial** solutions

The **kernal** or **nullspace** of a matrix is the set of all solutions to $Ax=0$

**Example**
Determine the nullspace of $A=\begin{bmatrix}3&2\\2&-1\end{bmatrix}$ 
$3x_1 + 2x_2=0$
$2x_1 - x_2=0$
$\implies x_2 = 2x_1$
$\implies 7x_1=0$
$\therefore x_1=0,x_2=0$
The nullspace of A is the vector $\begin{bmatrix}0\\0\end{bmatrix}$

- n p-dimensional vectors are linearly dependent if p < n
	- Must be at least one free variable

A **span** of a set of vectors
- We say a vector $w\in span(V)$ if $w=\sum_{i=1}^n a_i \vec{v_i}$ 

**Example**
$$v_1=\begin{bmatrix}2\\1\\0\end{bmatrix}, v_2=\begin{bmatrix}4\\1\\0\end{bmatrix}$$
Describe the geometry of the span(v1,v2)
- The span is the set of linear combinations of the two vectors
- The two vectors are linearly independent
- The span describes a plane

A **basis** B of a vector space V is a linearly independent subset of V that spans V
- Linear independence
- span(B)=V
- Allows unique linear decomposition of all vectors V if B=(b1,b2) is a basis of V then all v in V can be written as $$\vec{v}=\sum_{i=1}^n\alpha_i\vec{\beta_i}$$
- And $\alpha_i$ are the coordinates of v in B
---
### Canonical basis

In $R^d$ we often use canonical basis
![[Canonical Basis.png]]

The coordinates of v in the canonical basis is v
- The basis vectors in the canonical basis all for right angles to each other
- All have length 1
- Is an example of an **orthonormal** basis

An orthonormal basis of a vector space V is a subset of vectors {v1,v2,v3,...,vd} that form a basis of V and for which we have: $$\langle\vec{v_i},\vec{v_j}\rangle=\delta_{ij}=\left\{\begin{matrix}1\; i=j\\ 0\; i\neq j\end{matrix}\right.$$ **Example**
Are the vectors $\vec{v_1}=\begin{pmatrix}2\\1\end{pmatrix}, \vec{v_2}=\begin{pmatrix}4\\1\end{pmatrix}$ a basis of $R^2$
- Need to check:
	- Linear independence: yes
	- span(v1,v2) = $R^2$

let an arbitrary vector $\vec{v}=\begin{pmatrix}x\\y\end{pmatrix}$ 
For an arbitrary x and y, can I always find $\alpha$ such that $\vec{v}=\alpha_1\vec{v_1}+\alpha_2\vec{v_2}$
$x = 2\alpha_1 + 4\alpha_2$
$y = \alpha_1 + \alpha_2$
$\implies \alpha_1=2y-\frac{x}{2},\;\alpha_2=\frac{x}{2}-y$
$\therefore$ v1, v2 spans $R^2$ and thus is a basis of $R^2$

---
#### Dimensions

The dimension of a vector space V is the number of basis vectors in any basis in V
- Dimension of $R^d$ is d because we have d canonical basis vectors