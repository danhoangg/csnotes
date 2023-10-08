- A set is a collection of objects, also referred to as elements or members
- e.g. a small finite could be {0, 1, 8}
- Element repetition doesn't matter within sets, {0, 2, 5, 2} = {0, 2, 5}
- Infinitely large sets can be defined using ellipses, {0, 1, 2, ...} or {0, 2, 4, ...}
- If an element x is a set X we can write $x \in X$:
	- $a \in \{b,a,c\}$
	- $0 \in \{0,1\}$
	- $i \notin \{t,e,a,m\}$
- Sets can also be empty and are denoted as $\varnothing$
	- $|\varnothing|=0$
### Cardinality
Cardinality of a set is how many elements are in it, also referred to as the size:
- $|\{1,2,3\}| = 3$
- $|\{b,a,b,c\}| = 3$

### Commonly used sets
#### $\mathbb{N} = \{0,1,2,...\}$
#### $\mathbb{Z} = \{...,-2,-1,0,1,2,...\}$
#### $\mathbb{R}$ = Real numbers
#### $\mathbb{C}$ = Complex numbers

### Operations on Sets

1. $A \cup B$ = A or B
2. $A \cap B$ = A and B
3. B - A = The difference of sets

#### Predicates
A predicate $\varphi(x)$ is something that is either true or false about a member x of some universe
- $\varphi(x)$ = "x is an apple" is a predicate in the universe of fruit

Importantly, a predicate is written in this format:
#### $\set{x \mid x \in X\; \&\; \varphi(x) \,}$
- $\set{x \mid x \in \mathbb{N}\; \&\; \text{x is even} \,} = \set{0,2,4,...}$
- $\set{x \mid x \in \mathbb{R}\; \&\; x^2+x-6=0}=\set{2.0, -3.0}$

#### Therefore:
- $X \cup Y = \set{z \mid z \in X\; \text{or}\; z \in Y}$
	- Associative ($X \cup (Y \cup Z) = (X\cup Y)\cup Z$)
	- Commutative ($X\cup Y=Y\cup X$)
- $X \cap B = \set{z \mid z \in X\; \text{and}\; z \in Y}$
	- Associative and commutative
- $X-Y = \set{z \mid z \in X\; \text{and}\; z \notin Y}$
	- Not associative and not commutative


Next: [[Reasoning About Sets]]