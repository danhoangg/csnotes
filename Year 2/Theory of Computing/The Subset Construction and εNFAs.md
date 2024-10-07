- Let $M = (Q, \Sigma, \Delta, s, F)$ be an NFA
- We will construct a DFA $M'$ over $\Sigma$ with
	- Set of states $Q' \stackrel{\text{def}}{=} 2^q$ 
	- Starting state $s' \stackrel{\text{def}}{=} \set{s}$
	- Final states $F' \stackrel{\text{def}}{=} \set{X\; | \; \exists f \in F . f \in X }$
	- Transition function $\delta'(X, \sigma) \stackrel{\text{def}}{=} \bigcup_{q\in X} \delta(q, \sigma)$
- Claim: $L(M') = L(M)$

#### Epsilon moves
- We have seen that nondeterminism can be tamed
	- The price - possible exponential increase in number of states
- We need one more useful feature: $\epsilon$-moves
- When taking an $\epsilon$-labelled transition without "consuming a symbol"

An $\epsilon$NFA $M \stackrel{\text{def}}{=} (Q, \Sigma, \theta, s, F)$
- Where $\theta : Q \times (\Sigma \cup \set{\epsilon}) \to 2^Q$ is the transition function
	- We will right $q \xrightarrow{\sigma} q'$ for $q' \in \theta(q, \sigma)$

- Write $q \xRightarrow{\epsilon} q'$ if either $q = q'$ or there exists a sequence of $\epsilon$-moves $q \xrightarrow{\epsilon} \dots \xrightarrow{\epsilon} q'$
- Write $q \xRightarrow{\sigma} q'$ for $\sigma \in \Sigma$ if there exists if there exists a sequence $q \xRightarrow{\epsilon} \xrightarrow{\sigma} \xRightarrow{\epsilon} q'$ 
- Write $q \xRightarrow{\sigma\tau} q'$ if we have $q \xRightarrow{\epsilon} \xrightarrow{\sigma} \xRightarrow{\epsilon} \xrightarrow{\tau} \xRightarrow{\epsilon} q'$ and similarly for longer strings
- A string $x$ is accepted if there exists $f \in F$ such that $s \xRightarrow{x} f$

![[epsilon nfa.png| 350]]

- Any NFA is a special kind of $\epsilon$NFA
- Are $\epsilon$NFAs more powerful than NFAs?
	- No! Any $\epsilon$NFA can be turned into an NFA
- So $\epsilon$NFAs accept precisely the regular languages

#### From εNFAs to NFAs
- Let $M$ be an $\epsilon$NFA. Let $M'$ be an NFA with the same states but: $$\Delta'(q,\sigma) \stackrel{\text{def}}{=} \set{q'\;|\;q \xRightarrow{\epsilon}\xrightarrow{\sigma}q'}, F' \stackrel{\text{def}}{=} \set{q \; | \; \exists f\in F. q\xRightarrow{\epsilon}f}$$
- $\epsilon$-transitions removed
- States with $\epsilon$-transitions to a final state become final
- New transitions added to preserve the language
![[ep nfa to nfa.png | 500]]
- Claim $L(M') = L(M)$



