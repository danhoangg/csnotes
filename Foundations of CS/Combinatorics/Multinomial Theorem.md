Subjects/ Topics: #Combinatorics #Binomial #Multinomial


**Binomial Theorem:**
- $(x+y)^n$ 

$[x^a]f(x)$ means the coefficient of $x^a$ in $f(x)$

**Trinominal expansion:**

$(x+y+z)^n = \sum_{i,j,k} \frac{n!}{i!j!k!}x^iy^jz^k$
Where $i+j+k=n$

**Example**
![[Trinomial.png]]

**Multinomial expansion:**

$(x_1+...+x_m)^n = \sum_{k_1,...,k_m}\begin{pmatrix}n\\k_1...k_m\end{pmatrix}x_1^{k_1}...+x_m^{k_m}$  

#### Lattice paths and Multinomial coefficient

By going only in the direction towards the point:
- How many paths are there from point (0, 0) to (2,2)
	- $\frac{4!}{2!2!}$ = 4C2
	- $\begin{pmatrix}2+2\\2\end{pmatrix}$
- How many paths are there from point (0,0,0,) to (2,2,2)
	- $\frac{(2+2+2)!}{2!2!2!}$
	- $\begin{pmatrix}2+2+2\\2,2,2\end{pmatrix}$
