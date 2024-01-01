Subjects/ Topics: #SetTheory #Relations 

- An equivalence relation $\sim$ on $X(\sim \subseteq X\times X)$ is a special relation that satisfies the following three **axioms**
	- Reflexivity: $\forall x\in X. x\sim x$
	- Symmetry: $\forall x\in X.$ if $x\sim y$ then $y\sim x$
	- Transitivity: $\forall x,y,z \in X.$ if $x\sim y$ and $y\sim z$ then $x\sim z$

**Examples**:
- $R = \set{(x,y)\mid x\in P, y\in P, \text{have the same first name}}$
	- This relation is equivalence since $(x,x)$ will always be in the set
	- If $(x,y)$ is in the set $R$, then $(y,x)$ must be in $R$ since they will both have the first name
	- And if $(x,y)$ is in set $R$ and $(y,z)$ is in set $R$, then $(x,z)$ must be in set $R$
- $S = \set{(x,y)\mid x\in C, y\in C, \text{are less than 50 miles from each other}}$
	- Relation $S$ is not reflexive since a city cannot be 50 miles from itself and therefore is not an equivalence relation
- Let $\mathbb{N}$ be the set of natural numbers
- $P=\set{(k,m)\mid k\in\mathbb{N}, m\in\mathbb{N}, \text{have the same number of primes in their prime factorisation}}$ 
	- $P$ must be reflexive
	- $P$ must be symmetrical
	- And the relation must be transitive which means $P$ is an equivalence relation

- If $\sim$ is an equivalence relation on X and $a\in X$ then the **equivalence class** of a is the set
	- $[a] = \set{x\mid x\in X, x\sim a}$
- $X/\sim = \set{[x]\mid x\in X}$ is the set of equivalence classes
	- All sets sets in X/~ are either exactly equivalent or disjoint

**Question**
- Let Z be the set of integers. Let ~⊆Z×Z be defined x~y whenever there exists an integer k such that  x = y + 4k
	- ~ is reflexive as k can be 0 and then x=x
	- ~ is symmetric if x=y+4k can exists for an integer k, then y=x-4k
	- ~ is transitive, if y is an integer difference of multiple of 4 from x, and same for y and z, then the difference between x and z must also be an integer difference multiple of 4
- The cardinality of Z/~ is 4, since the relation is equivalence modulo 4 

- A collection $X_1,...,X_n$ of subsets of $X$ is a **partition** of a set $X$ if $X_1\cup ...\cup X_n = X$
- The set of equivalence classes X/~ is a **partition** of X
- The set of equivalence classes X/~ us sometimes called a quotient of X with respect to ~
- A function $\phi:X\to X/\sim$ defined $\phi(x)=[x]$
	- It is always surjective since all equivalence classes are mapped to a value of x
	- It is only ever injective if and only if each equivalence class has a cardinality of 1

- The $\leq$ is a relation 
	- $\leq_R = \set{(x,y)\mid x\in\mathbb{R}, \exists r\in R_+. y=x+r}$

**Partial Orders**
- A relation $\leq \subseteq X\times X$  is a partial order when
	- Reflexive: $x\leq x$
	- Transitive: $x\leq y, y\leq z \implies x\leq z$
	- Anti-symmetric: if $x\leq y$ and $y\leq x$ then $x=y$

- Total orders need the additional property satisfied
	- For all x,y either $x\leq y$ or $y\leq x$
- $\therefore$ $\leq$ is an example of a total order

