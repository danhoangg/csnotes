Subjects/ Topics:  #Probability #Stats

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

### Expected Value

**Average/ mean**
#### $$\mathbb{E}[X] = \left\{\begin{matrix}\sum_ix_ip(x_i)\;\; \text{If discrete} \\ \int_{-\infty}^{\infty}xp(x)dx\;\; \text{If continuous}\end{matrix}\right.$$
- P(X=x) is too clumsy, write p(x)
- p(x) is called the **probability distribution function**
	- p(x) is called a probability density function if X is a continuous random variable
	- p(x) is called a probability mass function if X is a discrete random variable

- p(x,y) = P(X=x, Y=y)
- p(x | y) = P(X=x | Y=y)

#### Expected value under transformation
#### $$\mathbb{E}[f(X)] = \left\{\begin{matrix}\sum_if(x_i)p(x_i)\;\; \text{If discrete} \\ \int_{-\infty}^{\infty}f(x)p(x)dx\;\; \text{If continuous}\end{matrix}\right.$$
- $E[aX + bY + c] = aE[x] + bE[Y] + c$
- $E[XY] = E[X]E[Y]$ - IF X and Y are independent

### Variance
$$\mathbb{V}[X] = \mathbb{E}[X^2] - \mathbb{E}[X]^2$$
### Covariance and Correlation

- Variance - seeing the variable as a whole entity
- Covariance - seeing the variable part by part
- Given two RVs X,Y, covariance is defined as $$\text{cov}(X,Y):= \mathbb{E}[(X-\mathbb{E}[X])(Y-\mathbb{E}[Y])] = \mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y]$$
- The **Pearson correlation coefficient** is defined as $$\text{corr}(X,Y) = \frac{\text{cov}(X,Y)}{\sqrt{\mathbb{V}[X]}\sqrt{\mathbb{V}[Y]}}$$
- $-\infty \leq \text{cov}(X,Y) \leq \infty$ and $-1 \leq \text{corr}(X,Y) \leq 1$

**Example**
Given a table like this:

| | X=1 | X=2 | X=3|
| --- | --- | --- | --- |
| Y=1 | 0.05 | 0.15 | 0.1|
| Y=2 | 0.25 | 0.15 | 0.3 |
- $\mathbb{E}[X] = 1\times0.3 + 2\times0.3 + 3\times0.4 = 2.1$
- $\mathbb{E}[Y] = 1\times0.3 + 2\times0.7 = 1.7$

| | X-E[X]=-1.1 | X-E[X]=-0.1 | X-E[X]=0.9|
| --- | --- | --- | --- |
| Y-E[Y]=-0.7 | 0.05 | 0.15 | 0.1|
| Y-E[Y]=0.3 | 0.25 | 0.15 | 0.3 |
$\text{cov}(X,Y) = (-1.1)(0.05)(0.7) + (-0.1)(0.15)(-0.7) + ...$

- $\text{cov}(X,X) = \mathbb{V}[X]$
- $\text{cov}(aX,Y) = a\text{cov}(X,Y)$
- $\text{cov}(X+c,Y) = \text{cov}(X,Y)$
- $\text{cov}(X+Z,Y) = \text{cov}(X,Y) + \text{cov}(Z,Y)$

#### Variance fun facts

- $\mathbb{V}[aX + bY+c] = a^2\mathbb{V}[X] + b^2\mathbb{V}[Y] + 2ab\text{cov}(X,Y)$
- $\mathbb{V}[aX + bY + cZ + d] = a^2\mathbb{V}[X] + b^2\mathbb{V}[Y] + c^2\mathbb{V}[Z] + 2ab\text{cov}(X,Y) + 2ac\text{cov}(X,Z) + 2bc\text{cov}(Y,Z)$ 

### Conditional expectation and conditional variance

- $\mathbb{E}[X\mid Y=y]$ is the conditional expectation of X given Y=y $$\mathbb{E}[X\mid Y=y] = \sum xp(x\mid y) = \sum x\frac{p(x,y)}{p(y)}$$
- Or equivalently, a random variable $Z(y) = \mathbb{E}[X\mid Y=y]$ defined as $$Z(y) = \left\{\begin{matrix}\mathbb{E}[X\mid Y=y_1]\;\;\;\text{with probability }\mathbb{P}(Y=y_1)\\\mathbb{E}[X\mid Y=y_2]\;\;\;\text{with probability }\mathbb{P}(Y=y_2)\\ \vdots\end{matrix}\right.$$
