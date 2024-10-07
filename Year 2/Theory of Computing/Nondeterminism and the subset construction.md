![[dfa ting.png | 400]]
- The above DFA over the alphabet $\set{a, b}$ accepts the language $$L = \set{w\; | \; w \; \text{ends with }b}$$
- It would be nice if the automaton could 'guess' when we are about to read the last symbol and then not allow and subsequent transitions
- NFAs can do this

### Determinism vs Nondeterminism
- **Determinism**
	- Next state is uniquely determined by current state and input
- Nondeterminism
	- Given a current state and input, there can be any number of next states, including 0

**Nondeterministic transitions**
![[nfa.png | 350]]
- We have states and transitions as before but
	- There are 2 $b$-labelled transitions from state 0
	- There are no transitions from state 1

An NFA $M \stackrel{\text{def}}{=} (Q, \Sigma, \Delta, s, F)$
- Where $\Delta : Q \times \Sigma \to 2^Q$ is the transition function
	- We will right $q \xrightarrow{\sigma} q'$ for $q' \in \Delta(q, \sigma)$
- Here $2^Q$ is the powerset

#### Nondeterministic acceptance
- An automaton accepts some strings (and rejects those it doesn't accept)
- For $\sigma_1, \sigma_2 \in \Sigma$, write $q \xrightarrow{\sigma_1\sigma_2} q'$ when there is a $q''$ such that $q \xrightarrow{\sigma_1} q''$ and $q'' \xrightarrow{\sigma_2} q'$ and similarly for longer length strings. Write $q \xrightarrow{\epsilon} q'$ when $q=q'$
- A string $x \in \Sigma^*$ determines a (possibly empty) set of states $q$ such that $s \xrightarrow{x} q$. M accepts $x$ when there exists $f\in F$ such that $s \xrightarrow{x} f$

#### NFAs and DFAs
- Any DFA is a special kind of NFA
	- Compose $\delta : Q \times \Sigma \to Q$ with the singleton function $\eta : Q \to 2^Q$ defined by $\eta(q) = \set{q}$ to obtain a function $\delta ; \eta : Q \times \Sigma \to 2^Q$
	- NFAs are at least as powerful as DFAs
- Is there any language that can be represented by a NFA but not a DFA?
	- No! Any NFA can be converted to a DFA that accepts the same language. The conversion method is known as the subset construction
	- The resulting DFA collects all the states that could be reached by reading a given string in the original NFA in a single state

#### Subset construction
- Let $M = (Q, \Sigma, \Delta, s, F)$ be an NFA
- We will construct a DFA $M'$ over $\Sigma$ with
	- Set of states $Q' \stackrel{\text{def}}{=} 2^q$ 
	- Starting state $s' \stackrel{\text{def}}{=} \set{s}$
	- Final states $F' \stackrel{\text{def}}{=} \set{X\; | \; \exists f \in F . f \in X }$
	- Transition function $\delta'(X, \sigma) \stackrel{\text{def}}{=} \bigcup_{q\in X} \delta(q, \sigma)$

- The states that correspond to subsets $\emptyset$ and $\set{1}$ are called **unreachable**
- Unreachable states play no part in deciding acceptance
- Some people call $\emptyset$ the error state

#### Conclusion
- Any DFA is an NFA, so regular languages are included in the class of languages accepted by NFAs
- Any NFA can be turned into a DFA that accepts the **same** language, so reverse inclusion also holds here
	- NFAs accept precisely the regular languages
- NFAs are often easier to write but DFAs are easier to implement