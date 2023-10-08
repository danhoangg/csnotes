- A basic relationship between sets is the subset relation:
	- A set x is a subset of Y when every element of X is also an element of Y
	- $X\subseteq Y$
- $X \subset Y$ if $X \subseteq Y$ and there exists $y \in Y$ and $y \notin X$

#### Two sets are equal when:
1. $X \subseteq Y$
2. $Y \subseteq X$

##### **Question**
- Suppose X, Y and Z are sets. Is it always the case that $X\cup (Y\cap Z)=(X\cup Y)\cap(X\cup Z)$
We prove $(X\cup Y)\cap(X\cup Z) \subseteq X\cup (Y\cap Z)$
$x\in (X\cup Y)\cap(X\cup Z) \implies x\in X\cup Y\; \text{and}\; x\in X\cup Z$

**Case 1**                                                                  **Case 2**
$x\in X$                                                                   $x \notin X$
$\implies x\in X\cup (Y\cap Z)$                                         $\implies x\in (Y\cap Z)\;\; \therefore x\in X\cup (Y\cap Z)$


- Prove that for all sets X, Y and Z we have $X\cap(Y\cup Z) = (X\cap Y)\cup(X\cap Z)$
If $x\in X\cap(Y\cup Z)$ then $x\in X\cap Y\; \text{or}\; x\in X\cap Z$
$\therefore x\in (X\cap Y)\cup(X\cap Z)$

### Products and Sums of sets

- $\set{0,1}=\set{1,0}$ is true however often it's useful to order elements
	- Ordered pairs are written like this $(0,1)$ where $(0,1)\neq(1,0)$
	- $(x,y)=(z,w)$ if $x=z$ and $y=w$
	- Sometimes called 'the defining property of an ordered pair'

- If $X$ and $Y$ are sets then $X\times Y$  denotes the set of all ordered pairs
	- $X\times Y = \set{(x,y)\mid x\in X\; \&\; y\in Y}$
	- $|X\times Y| = |X|\times |Y|$

- The sum or disjoint union is defined as $X+Y=\set{(x,0)\mid x\in X}\cup\set{(y,1)\mid y\in Y}$
	- e.g. $\set{a,b}+\set{a,c}=\set{(a,0),(b,0),(a,1),(c,1)}$
	- $|X+Y|=|X\cup Y|$ when $X\cap Y=\varnothing$

### Powersets
- Given a set $X$, the powerset $P(X)$ or $2^X$ is the set of all subsets of $X$
	- $P(\set{0,1})=\set{\varnothing, \set{0}, \set{1}, \set{0,1}}$
	- $P(\set{a,b,c})=\set{\varnothing,\set{a},\set{b},\set{c},\set{a,b},\set{a,c},\set{b,c},\set{a,b,c}}$
	- $PP(\varnothing)=P(\set{\varnothing})=\set{\varnothing, \set{\varnothing}}$
	- $|P(X)|=2^{|X|}$