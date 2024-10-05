Subjects/ Topics:  #Intro #Probability #Combinatorics 

**Definition** - The set of all possible outcomes is call the sample space $\Omega$ 
- $\Omega \neq \emptyset$ (non-triviality)

**Example** - Tossing a coin:
- $\Omega (\text{tossing a coin once}) = \{H, T\}$
- $\Omega (\text{tossing a coin twice}) = \{HH, TH, HT, TT\}$
- etc ...

- Any subset of $\Omega$ is called an **event** E

- The **classical probability** P(E) of an event E, is defined as $P(E) := \frac{|E|}{|\Omega|}$
	- Mathematics doesn't allow to divide by 0 $\Leftrightarrow$ $\Omega \neq \emptyset$
	- However $\left\{\begin{matrix}\text{E is possibly empty} \\ \Omega \text{ is possibly infinite}\end{matrix}\right.$

### Three probability axioms
- **Axiom 0** (non-triviality)
- **Axiom 1** (nonnegativity) $P(E) \geq 0$ 
- **Axiom 2** (Sample space has probability 1) $P(\Omega) = 1$
- Axiom 3 ($\sigma$-additivity) If $E_1$, $E_2$, ... are disjoint, then $$P(\bigcup_i E_i) = \sum_iP(E_i)$$
	- Two sets are disjoint if and only if $A\cap B = \emptyset$ 
	- In combinatorics: we do not allow cross-terms in the inclusion-exclusion principle
	- In probability: two events E, F are mutually exclusive if and only if they can't occur at the same time


**These axioms imply**:
- $P(E) \leq 1\; \forall E$
- $P(\emptyset) = 0$
- If $E \subset F$, then $P(E) \leq P(F)$

### Complementary event 

The **complementary event** of E in $\Omega$, denoted as $E^c$, is defined as $E^c := \Omega \backslash E$ 
- $P(E^c) = 1 - P(E)$
- Useful for when counting E is tedious
- Complementary $\implies$ mutually exclusive

### Mutual Exclusivity

- If E, F are mutually exclusive - $P(E\cup F) = P(E) + P(F)$
- If E, F are not mutually exclusive - $P(E\cup F) = P(E) + P(F) - P(E\cap F)$
- 
### Generating functions

**Example**:
- Toss a six sided die twice, what is the probability the sum is 4
- $\Omega (6-sided die) = \set{1,2,3,4,5,6}$ with probability $\set{p_1,p_2,p_3,p_4,p_5,p_6}$
- $G_{1d6}(x) = p_1x+p_2x^2+p_3x^3+p_4x^4+p_5x^5+p_6x^6$
- $\therefore P(\text{sum is 4}) = [x^4]G_{2d6} = p_1p_3 + p_2p_2 + p_3p_1$
- If dice is fair $= \frac{3}{36} = \frac{1}{12}$

![[prob proof.png]]

**Questions**

You toss a coin and a 4-sided die:
- If you get tail on coin then you take value of zero
- if you get head on coin, then you take value of die
What's the probability of getting 3

= 1/2 * 1/4 = 1/8

Suppose you flip a coin 5 times
- What's the probability of getting 3 heads
	- $\frac{\begin{pmatrix}5\\3\end{pmatrix}}{2^5} = \frac{10}{32}$
- What's probability of getting an even number of heads
	- $\frac{\begin{pmatrix}5\\2\end{pmatrix} + \begin{pmatrix}5\\4\end{pmatrix}}{2^5}$

A football match has 3 outcomes: Win, Lose, Draw
- Suppose a team has a win chance of 0.5, lose chance 0.2, draw chance 0.3
- They play 20 games
- Whats the probability of W=10, L=4, D=6
	- $\begin{pmatrix}20\\10,4,6\end{pmatrix}0.5^{10}0.2^40.3^6 = 0.044$ 
- Probability of getting at least 19 wins
	- P(19,1,0) + P(19,0,1) + P(20,0,0)
- 