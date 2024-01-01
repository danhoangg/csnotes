Subjects/ Topics: #SetTheory #Relations

### Function Spaces and Powersets

- Refer back to [[Functions]]
	- For each element x of the domain, there is exactly one element of y of the codomain : the value of f at x

**The graph of a function**
- Functions are defined with their **graphs**
- Given a function $f:X\to Y$, its graph is the set of pairs $\set{(x,f(x))\mid x\in X}$

- Given sets X and Y, let $Y^X$ denote the set of all functions from X to Y
- Cardinality of $Y^X$ is $|Y|^{|X|}$ if Y and X are finite

- Given X and Y are finite sets, and $f:X\to Y$ is a function. What are the cardinalities if:
	- f is injective: $|X|\leq|Y|$
	- f is surjective: $|X| \geq |Y|$
	- f is bijective: $|X|=|Y|$

### Sizes of Infinity

- For finite sets $X\subset Y \implies |X| < |Y|$
- This is not the case for infinite sets
- $\mathbb{N}\subset \mathbb{Z}$ 
	- A bijection for $\mathbb{N}\to\mathbb{Z}$ could be, start with 0 maps to 0, then 1 maps to 1, then 2 maps to -1, continuing this pattern, mapping the next natural number to the next positive integer and the one after to the next negative integer
	- It would start like this: $0\to 0$, $1\to 1$, $2\to -1$, $3\to 2$, $4\to -2$
	- Here you can see that this function is both injective and surjective and therefore $|\mathbb{N}|=|\mathbb{Z}|$

- A set X is called **countable** if there exists a bijection $f:\mathbb{N}\to X$, where N is the set of natural numbers

- Let $(0,1) = \set{x\in \mathbb{R}\mid 0<x<1}$
- $(0,1) \subset \mathbb{R}$ however their cardinalities are the same 

### Uncountable Sets

- The set of real numbers $\mathbb{R}$ is not a countable set
**Proof**
- There are no surjective functions $f:\mathbb{N}\to\mathbb{R}$

- Suppose that real numbers can be listed in a sequence
$r_1 = 0.a_{11}a_{12}a_{13}a_{14}...$
$r_2 = 0.a_{21}a_{22}a_{23}a_{24}...$
$r_3 = 0.a_{31}a_{32}a_{33}a_{34}...$

By taking the diagonal of each number $a_{11}a_{22}a_{33}a_{44}...$  we can construct a number that isn't on the list and therefore the function is not surjective as it never appears in the list.
Therefore there is no bijection for for $f:\mathbb{N}\to\mathbb{R}$
There are however injective function for $f:\mathbb{R}\to\mathbb{N}$, in this sense $\mathbb{R}$ has a larger cardinality than $\mathbb{N}$

