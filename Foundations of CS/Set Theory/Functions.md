Subjects/ Topics: #SetTheory #Functions 

1:1 mapping system such that for each element $x$ of the domain there is exactly one element $y$ of the codomain, the value f at $x$

- f, g, h are common letters to denote functions
- A function f from set X to set Y is usually written f : X → Y
	- X is the domain
	- Y is the codomain
	- f(x)=y, the value of f at x is y

**Range** of a function f : X → Y is the largest subset $R \subseteq Y$ that satisfies that:
- For all $r\in R$ there exists $x\in X$ such that f(x)=r

The range is the set of elements of Y that are mapped to by f

The **total** number of possible functions that map a set X to a set Y is $|Y|^{|X|}$

### Functions of several variables

A function with several variables can have a domain that is a cartesian product of sets, e.g.:
- Addition or multiplication of integers can have the domain of $\mathbb{N}\times\mathbb{N}$ and so $+:\mathbb{N}\times\mathbb{N}→\mathbb{N}$ defined as $+(x,y) = x+y$
- Or let $2=\set{0,1}$, then binary logic gates can be functions defined as $2\times2→2$ 

Given any set X there is an identity function $X→X$ denoted as $id_x$
- how is it defined, e.g.
- $f:\mathbb{R}→\mathbb{R}$ defined $f(x) = x^2$
- $s:\mathbb{N}→\mathbb{N}$ defined $s(x) = x+1$

### Composition

- If $f:X→Y$ and $g:Y→Z$ then $f;g:X→Z$ is a function that is defined (f;g)(x) = g(f(x))
- $f;g$ is sometimes written as $g\cdot f$

![[Composition.png]]

- Function composition is associative: $(f;g);h = f;(g;h)$

### Inverting 

- Given a function $f:X→Y$, an inverse( if it exists) is defined as $f^{-1}:Y→X$ such that:
	- $f^{-1}(f(x))=x$
	- $f(f^{-1}(y))=y$
- Therefore $f;f^{-1}=id_x$ and $f^{-1};f=id_y$

#### Question:
- Find sets X and Y, and functions $f : X→ Y$, $g: Y→ X$ such that $f;g ≠ id_x$ and $g;f ≠ id_y$
	- let X and Y be $\set{0,1}$
	- $f:X\to Y$ defined as $f(0)=1$, $f(1)=0$ 
	- $g:X\to Y$ defined as $g(0)=0$, $g(1)=1$
- Find sets X and Y, and functions $f : X→ Y,$ $g: Y→ X$ such that $f;g = id_x$ but $g;f ≠ id_y$
	- let X = ${0}$ and Y = $\set{0,1}$
	- $f:Z\to Y$ defined as $f(0)=0$
	- $g:X\to Y$ defined as $g(0)=0$, $g(1)=0$


Next: [[Taxonomy of functions and the isomorphism theorem]]

