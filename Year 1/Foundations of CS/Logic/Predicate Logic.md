Subjects/ Topics: #Logic #Proofs #Predicate

- In propositional logic, a "world" is an assignment of truth values to propositional variables
- Predicate logic is a much richer language
	- A world is a set, together with relations and functions. Given a set A:
	- an n-ary function is a function of type $A^n\to A$
	- an n-ary relation is a subset of $A^n$

### Predicate Logic Formula

- Injective function - A fuction $A\to A$  is injective when "for all x and y in A, if f(x)=f(y) then x=y".
- Which can then be translated into a formula of predicate logic: $$\forall x.\forall y. (f(x)=f(y))\to(x=y)$$
- Then a world will satisfy the formula exactly when f is an injective function in that world

- Variables (V), constants (C), function symbols, relation symbols
- Terms: $$T ::= V\mid C\mid f(T, T,...,T)$$
- Formulas: $$F::= R(T,T,...,T)\mid T=T\mid \perp\mid\neg F\mid F\wedge F\mid F\vee F\mid F\to F\mid \exists x.F\mid\forall x. F $$
### Semantics

- **Model**
	- A set A called the domain
	- for each constant symbol a, an element $a\in A$
	- for each n-ary function symbol f, a function $f:A^n\to A$
	- for each n-ary relation symbol R, a subset $R\subseteq A^n$

Given a function $\sigma$ from variables to elements of A, any term now has a corresponding element of A
$⟦x⟧_\sigma = \sigma(x)$
$⟦a⟧_\sigma=a$
$⟦f(t_1,t_2,...,t_k)⟧_\sigma=f(⟦t_1⟧_\sigma,⟦t_2⟧_\sigma,...,⟦t_k⟧_\sigma)$

### Semantics of Formulas

- If φ = R(t1,t2,...,tk) then A $\models_\sigma$ φ iff (⟦t1⟧σ,⟦t2⟧σ,...,⟦tk⟧σ)∈R
-  If φ = $\neg\psi$ then A $\models_\sigma$ φ iff $A\models_\sigma\psi$ does not hold
- If φ = $\psi_1\wedge\psi_2$ then A $\models_\sigma$ φ iff $A\models_\sigma\psi_1$ and $A\models_\sigma\psi_2$
- If φ = $\exists x.\psi$ then A $\models_\sigma$ φ iff there exists $a\in A$ such that $A\models_{\sigma[x\to a]}\psi$
- If φ = $\forall x.\psi$ then A $\models_\sigma$ φ iff for all $a\in A$ such that $A\models_{\sigma[x\to a]}\psi$

If $A\models_\sigma\varphi$ then we say A is a model for $\varphi$

### Logical equivalence
Two formulas $\varphi, \psi$ are logically equivalent ($\equiv$) if for any model we have $A\models \varphi$ iff $A\models\psi$ (logical equivalence is an equivalence relation)
![[predicate examples.png]]

### Semantic Entailment
- Propositional logic
	- $\Gamma\models\varphi$ means: any truth assignment that makes all the formulas of $\Gamma$ evaluate to T also makes $\varphi$ evaluate to T
- Predicate logic
	- $\Gamma\models\varphi$ means: any model A for all the formulas of $\Gamma$ is also a model for $\varphi$

### Natural deduction for predicate logic
**Rules for $\exists$**
$$\frac{\varphi(t)}{\exists x.\varphi(x)}$$
$$\frac{\exists x.\varphi(x)\;\;\;\psi}{\psi}$$
Only if $\varphi(x)$ has been given as an assumption before $\psi$

**Rules for $\forall$**
$$\frac{\varphi(x)}{\forall x.\varphi(x)}$$
$$\frac{\forall x.\varphi(x)}{\varphi(t)}$$

### Example proof
# $$\frac{\frac{\frac{\frac{\forall x.\varphi(x)}{\varphi(x)}\;\;\;[\neg\varphi(x)]}{\perp}\;\;\;\;[\exists x.\neg\varphi(x)]}{\perp}}{\neg\exists x.\neg\varphi(x)}$$
As for predicate logic, natural deduction with the additional rules is sound and complete