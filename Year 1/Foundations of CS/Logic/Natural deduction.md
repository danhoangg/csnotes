Subjects/ Topics: #Proofs #Logic #NaturalDeduction

Natural deduction is both **sound** and **complete** for propositional logic

- Formal proofs in natural deduction(proof trees or derivations) is a different kind of tree to an abstract syntax tree
	- Nodes labelled with formulas
	- Labels of each parent and its children correspond to particular proof rule
	- leaves are assumptions traditionally drawn with leaves (assumptions) at the top and the root (conclusion) at the bottom

![[proof tree.png]]

- In natural deduction proof rules naturally fall into two classes:
	- **Introduction rules** - allow the introduction of a logical connective
	- **Elimination rules** - allow the elimination of a logical connective

### Conjunction Rules

**$\wedge$ - Introduction**
#### $$\frac{\psi\;\;\;\;\varphi}{\varphi\wedge\psi}$$
**$\wedge$ - Elimination**
#### $$\frac{\varphi\wedge\psi}{\varphi}\;\;\;\frac{\varphi\wedge\psi}{\psi}$$
#### Implication Rules

**$\to$ - Introduction**
#### $$\frac{\psi}{\varphi\to\psi}$$ Only if $\varphi$ has been given as an assumption

**$\to$ - Elimination**
#### $$\frac{\varphi\;\;\;\;\varphi\to\psi}{\psi}$$
#### Example
$\{\varphi\wedge\psi,\varphi\to[\psi\to\chi]\}\vdash\chi$

# $$\frac{\frac{\varphi\wedge\psi}{\psi}\;\;\;\;\;\frac{\frac{\varphi\wedge\psi}{\varphi}\;\;\;\;\varphi\to[\psi\to\chi]}{\psi\to\chi}}{\chi}$$
$\vdash \psi\to(\varphi\to\varphi\wedge\psi)$
# $$\frac{\frac{\frac{[\phi]\;\;[\psi]}{\varphi\wedge\psi}}{\varphi\to\varphi\wedge\psi}}{\psi\to(\varphi\to\varphi\wedge\psi)}$$

### Rules for negation

**$\neg$ - Introduction**
#### $$\frac{\bot}{\neg\varphi}$$  Only if $\varphi$ has been given as an assumption

**$\neg$ - Elimination**
#### $$\frac{\varphi\;\;\;\;\neg\varphi}{\bot}$$
### Rules for disjunction

**$\vee$ - Introduction**
#### $$\frac{\varphi}{\varphi\vee\psi}\;\;\;\frac{\psi}{\varphi\vee\psi}$$
**$\vee$ - Elimination**
#### $$\frac{\chi\;\;\;\chi\;\;\;\varphi\vee\psi}{\chi}$$ Only if $\varphi$ and $\psi$ are given as assumptions


