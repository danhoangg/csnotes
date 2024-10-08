Given $\Sigma$, the set of regular expressions is defined inductively.
- Every $\sigma\in \Sigma$ is a regular expression
	- $L(\sigma) \stackrel{\text{def}}{=} \set{\sigma}$
- $\epsilon$ is a regular expression
	- $L(\epsilon) \stackrel{\text{def}}{=} \set{\epsilon}$
- $\emptyset$ is a regular expression
	- $L(\emptyset) \stackrel{\text{def}}{=} \emptyset$

- If $\alpha, \beta$ is a regular expression then $\alpha + \beta$ is a regular expression
	- $L(\alpha + \beta) \stackrel{\text{def}}{=} L(\alpha) \cup L(\beta)$
	- Some authors write $\alpha \mid \beta$
- If $\alpha, \beta$ is a regular expression then $\alpha\beta$ is a regular expression
	- $L(\alpha \beta) \stackrel{\text{def}}{=} L(\alpha) L(\beta)$
- If $\alpha$ is a regular expression then $\alpha^*$ is a regular expression
	- $L(\alpha^*) \stackrel{\text{def}}{=} L(\alpha)^*$

**Example**
- We say that a string $s$ matches a regular expression $\alpha$ whenever $s\in L(\alpha)$
- For $\Sigma = \set{a, b}$
	- No strings match $\emptyset$ (since $L(\emptyset) = \emptyset$)
	- Strings that end in $b$ match $(a + b)*b$
	- Strings of even length match $((a+b)(a+b))$
	- $abba$ and the empty string match $abba+\epsilon$

- Describe the following language using a regular expression $$\set{w\in\set{a,b}\mid \text{every }b \text{ in } w \text{ is immediately followed by an } a}$$
	- $(a + ba)*$

- The following regular expression over the alphabet $\set{+, -,.,0,1,\dots,9}$ describes the numerical constants: $$(++-+\epsilon)(ee^* + ee^*.e^* + e^*.ee^*)$$
- $12, -3, 1.5, +.7$ match this regex

### Kleene's Theorem

- If $\alpha$ is a regex then $L(\alpha)$ is a regular language
- If $L$ is a regular language then $L=L(\alpha)$ for some regex $\alpha$

- In other words, finite automata and regular expressions describe the same languages

#### Proving Kleene's Theorem
1. Show how to convert a regular expression to a $\epsilon$NFA for the same language
2. Show how to convert any NFA to a regular expression for the same language

- The set of regular expressions is built inductively
	- $\sigma\in\Sigma$, $\epsilon$ and $\emptyset$ are base cases
	- $+$, concatenation and $^*$ are the operations
- To prove that $\forall\alpha.L(\alpha)$ is regular we need to prove that 
	- $L(\sigma)$, $L(\epsilon)$ and $L(\emptyset)$ are regular
	- $L(\alpha)$, $L(\beta)$ are regular then so is $L(\alpha + \beta)$
	- $L(\alpha)$, $L(\beta)$ are regular then so is $L(\alpha\beta)$
	- $L(\alpha)$ is regular then so is $L(\alpha^*)$

![[base cases.png | 500]]

- We proved that regular languages are closed under union, $L(\alpha + \beta) = L(\alpha) \cup L(\beta)$ and so $L(\alpha + \beta)$ is regular
- Showing that $L(\alpha\beta) \stackrel{\text{def}}{=} L(\alpha) L(\beta)$ is regular
	- Let $M_1$ and $M_2$ be NFAs for $L(\alpha)$ and $L(\beta)$ respectively
	- We can construct a new $\epsilon$NFA $M_3$
![[magic.png]]
- All transitions in $M_3$ are those from $M_1$ and $M_2$ plus a $\epsilon$-transition from all final states in $M_1$ to the initial state of $M_2$
- $L(M_3) = L(M_1)L(M_2)  = L(\alpha)L(\beta)$

- Showing that $L(\alpha*) \stackrel{\text{def}}{=} L(\alpha)*$ is regular
- Let $M$ be an NFA for $L(\alpha)$. We construct a new $\epsilon$NFA $M'$
![[kleene star nfa.png]]
- A new initial state $0$ which allows for empty strings 
- Transitions of $M'$ take those of $M$ plus $\epsilon$-transitions as above
- Final states of $M'$ take the singleton $\set{0}$
- $L(M') = L(M)* = L(\alpha)*  = L(\alpha*)$


