Subjects/ Topics:  #Probability #Stats #Distributions

- We denote $p(x \mid \theta), x\in \chi, \theta \in \Theta$
	- $\theta$ is a parameter
	- $\Theta$ is set of valid parameters
	- by changing $\theta$ we change the distribution

**Must know distributions:**
- Bernoulli $p(x \mid \theta) = \theta^x(1-\theta)^{1-x}, \theta \in [0,1],x\in \mathbb{N}$                       Special case of binomial where n=1
- Binomial $p(m \mid n, \theta) = \begin{pmatrix}n\\m\end{pmatrix} \theta^m(1-\theta)^{n-m}, n,m\in \mathbb{N}$                  Toss coin n times, m success
- Geometric $p(k\mid\theta) = (1-\theta)^{k-1}\theta,k\in {1,2,...}$                              Toss coin k times, first success at the kth                                                                                                       time
- Trinomial and multinomial $p(k_1,k_2,k_3\mid n,\theta_1,\theta_2,\theta_3) = \begin{pmatrix}n\\k_1,k_2,k_3\end{pmatrix}\theta_1^{k_1},\theta_2^{k_2},\theta_3^{k_3}$     Generalised binomial

#### Bernoulli Distribution
- $\mathbb{P}(X=1\mid\theta)=\theta$
- $\mathbb{P}(X=0\mid\theta)=1-\theta$
- $\mathbb{E}[X] = \theta$
- $\mathbb{V}[X] = \theta(1-\theta)$

#### Binomial Distribution
- Out of n trials, m success
- $\mathbb{E}[X] = m\theta$
- $\mathbb{V}[X] = m\theta(1-\theta)$

#### Trinomial, multinomial distribution
- Possible outcome {1,2,3} with probability {$p_1,p_2,p_3$}
