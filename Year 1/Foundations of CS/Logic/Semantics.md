Subjects/ Topics: #Semantics #Logic

### Basic truth tables

p | q | p $\to$ q
-- | -- | -- 
0 | 0 | 1
0 | 1 | 1
1 | 0 | 0
1 | 1 | 1

- $[[P]]_\sigma = \sigma (p)$
- $[[\bot]]_\sigma = F$
- $[[\neg \varphi]]_\sigma= \neg ([[\varphi]]_\sigma)$
	- Where $\neg : 2 \to 2$ defined as $\neg(0)=1, \neg(1)=0$
- $[[\varphi \wedge \psi]]_\sigma=\wedge([[\varphi]]_\sigma\;, [[\psi]]_\sigma)$ 
- $[[\varphi \vee \psi]]_\sigma=\vee([[\varphi]]_\sigma\;, [[\psi]]_\sigma)$ 
- $[[\varphi \to \psi]]_\sigma=\to([[\varphi]]_\sigma\;, [[\psi]]_\sigma)$ 

**Example:**
- let $\sigma(p)=T, \sigma(q)=T, \sigma(r)=F$. Derive $[[r\to p\wedge q]]$
	- $\implies\;\to([[r]], [[p\wedge q]])$
	- $\implies\;\to(\sigma(r), \wedge([[p]],[[q]]))$
	- $\implies\;\to(F,\wedge(T,T))$
	- $\implies\;\to(F,T)$
	- $\implies T$

### Tautologies

- A formula $\varphi$ that always evaluates to True for all possible values of propositional variables is called to be a **tautology** or is said to be **valid**.
- A formula $\varphi$ that evaluates to T for at least one assignment of truth values to propositional variables is said to be **satisfiable**
- Two formulas are **logically equivalent** when they evaluate to equal truth values for any assignment of truth values to propositional variables

**Semantic Entailment:**
- If $\varphi \models\psi$ then If $\varphi$ is True then $\psi$ is True
- Suppose that $\Gamma$ is a set of formulas and $\models$ means semantically entails
- $\Gamma \models \varphi$ ($\Gamma$ semantically entails phi) means any truth truth assignment that makes all the formulas of gamma evaluate to T also make $\varphi$ evaluate to T
- $\models \varphi$ means $\emptyset \models \varphi$

### Formal Proof Systems

- Write $\Gamma \vdash \varphi$ when, taking the formulas in $\Gamma$ as assumptions we can prove that $\varphi$ as the conclusion
- Write $\vdash \varphi$ when we can prove $\varphi$ without using any assumptions

"When is a proof system correct"
#### $$\Gamma \vdash \varphi\; \text{implies}\; \Gamma \models \varphi$$
- "Whenever gamma proves phi, gamma semantically entails phi"
- So if we can prove that $\varphi$ holds given from some assumptions, if those assumptions are true then $\varphi$ must also be true
- i.e. if we can prove something in our proof system then it is true

"When is a proof system most useful"
#### $$\Gamma \models \varphi\; \text{implies}\; \Gamma \vdash \varphi$$
- "Whenever gamma semantically entails phi, gamma proves phi"
- Whenever $\varphi$ is true given that some formulas are true, then $\varphi$ is also provable from those formulas
- i.e. if something is true, the proof system is powerful enough to prove it