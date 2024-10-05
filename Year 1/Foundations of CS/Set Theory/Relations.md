Subjects/ Topics: #SetTheory #Relations

- Given two sets X and Y, the cartesian product $X\times Y$ is the set of all ordered pairs $(x,y) x\in X, y\in Y$
- A (binary) relation R from X to Y is some set of ordered pairs (x,y)
- In other words $R \subseteq X\times Y$
- R,S,T denote relations

- When X=Y, we say that R is a relation **on** X
	- The full relation $X\times Y$, the empty relation $\emptyset \subseteq x\times Y$
	- There is a relation on any set X called the *Identity Relation*
		- $I_X = \set{(x,x)\mid x\in X}$

- A directed graph (digraph) with at most one edge from one vertex to another can be formalised as a binary relation on its set of vertices
![[Digraph.png]]

- If there is a relation R from X to Y and there is a relation S from Y to Z, then R;S is a relation from X to Z defined
- $(x,z) \in R;S$ if there exists $y\in Y$ such that $(x,y) \in R$ and $(y,z)\in S$ 
- R;S is sometimes written as $S\circ R$ 
- Composition is associative

**Functions are special relations**
- Any function $f:x\to Y$ is a special kind of relation from $X$ to $Y$ that satisfies
	- $\forall x\in X$ there **exists a unique** $y\in Y$ s.t. $(x,y)\in f$ 
	- if $(x,y)\in f$ and $(x,z)\in f$ then $y=z$
- Given a function $f$, when we want to emphasise that we are talking about the relation, we call it the **graph** of f
