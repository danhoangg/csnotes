Subjects/ Topics:  #Probability #Stats #Combinatorics 

### Univariate
- Let $\Omega = \set{1,2,3}$, let X be a random variable over $\Omega$ such that $X=\left\{\begin{matrix}1\;\; \text{with probability 1/2}\\2\;\; \text{with probability 1/4}\\3\;\; \text{with probability 1/4}\end{matrix}\right.$ 
- RV notation P(X=x), x $\in \Omega$ 
- P(X=1) = 1/2, P(X=2) = 1/4, P(X=3) = 1/4

### Bivariate

- Let X = {1,2,3}, Y = {1,2} be the sample spaces of two RVs 
- Cartesian product X x Y is the sample space for the pair (i,j)
- An example of distribution over $\Omega = X\times Y$ 

| |X=1|X=2|X=3|
| --- | --- | --- | --- |
|Y=1|0.05|0.15|0.1|
|Y=2|0.25|0.15|0.3|

Therefore P(X=1, Y=1) = 0.05
- P(X=x, Y=y) is called a **joint probability**

#### Marginal probabilities
- P(X=x) means only looking at X=x regardless of Y
- $P(X=x) = \sum_{y\in Y} P(X=x, Y=y)$ is called a marginal probability

#### Conditional probabilities
- P(X=x | Y= y) is conditional and it means P(X=x) given Y=y
$$P(X=x \mid Y=y) = \frac{P(X=x, Y=y)}{P(Y=y)}$$
#### Independent random variables
- X, Y are independent if
	- P(X=x, Y=y) = P(X=x)P(Y=y)
- This implies that
	- P(X=x | Y=y) = P(X=x)

#### i.i.d. (Independent and identically distributed)
 - e.g. Toss one six-sided die 10 times
	 - 10 independent random variables all with identical probability distributions
	 - $P(X_1=x_1, X_2=x_2, ... , X_{10}=x_{10}) = P(X_1=x_1)P(X_2=x_2)...P(X_{10}=x_{10})$



