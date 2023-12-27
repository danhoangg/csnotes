Subjects/ Topics: #Stats #Probability #Distributions 

### The normal distribution

- Also called the Gaussian distribution
- Sample space $\chi = \mathbb{R}$ is the whole real line
- $X\sim\mathcal{N}(\mu,\sigma^2)$ means X is a RV under normal distribution with mean $\mu$ and variance $\sigma^2$
$$\mathbb{P}(X=x;\mu;\sigma^2)=:p(x\mid\mu,\sigma^2)=\frac{1}{\sqrt{2\pi\sigma^2}}\exp(\frac{-(x-\mu)^2}{2\sigma^2})$$
- Probability of an interval = the area under the curve
- $\mathbb{P}(a\leq X\leq b) = \int_a^bp(x)dx$
- Cannot be computed by hand

- Linear transformations of normal variables
	- Suppose we have $X\sim \mathcal{N}(\mu,\sigma^2)$ and $Y=aX$, then $Y\sim \mathcal{N}(a\mu, (a\sigma)^2)$ 
	- If in a different case $Y = X + c$, then $Y\sim \mathcal{N}(\mu + c, \sigma^2)$
	- If $Y = \frac{X - \mu}{\sigma}$ then $Y\sim \mathcal{N}(0, 1)$, also known as standardisation

- A standardised normal distribution is $Z\sim \mathcal{N}(0,1)$
	- It can be calculated using the **error function:**
	- $\text{erf}(z):=\frac{2}{\sqrt{\pi}}\int_0^ze^{-t^2}dt$

- Side note:
	- You have a distribution $X\sim \mathcal{N}(\mu,\sigma^2)$ and want to calculate $P(X_1 \leq X \leq X_2)$
	- Using standard distribution $Z$:
		- Since $X = \sigma Z + \mu$
		- $P(X_1 \leq X \leq X_2) = P(\frac{X_1 - \mu}{\sigma} \leq Z \leq \frac{X_2 - \mu}{\sigma})$

### Finite-sample statistics

- Refers to behaviour of the estimator under repeated sampling
- Also called sampling statistics
- Has 3 applications
	- Comparing the quality of estimators: bias and variance
	- Quantifying the accuracy of an estimator: confidence interval
	- Determine how unlikely a statistics is: hypothesis testing

Suppose we draw 5 samples from a random variable $Y\sim\mathcal{Y}(\mu,\sigma^2)$ 3 times
- The means of these 3 samples are $\bar{y}_1, \bar{y}_2,\bar{y}_3$
- What is the distribution of these?
	- $\mathcal{N}(\mu,\frac{\sigma^2}{n})$ where n is the number of samples taken
	- Sample mean itself follows a normal distribution
	- The more samples taken, the smaller the variance, therefore the more "accurate" of an estimate it is for calculating $\mu$

### Confidence Intervals

- **The motivation:** suppose we have observed data $y = (y_1,y_2,...,y_n)$. Now we would like to model these using a distribution with population parameter $\theta$
- In *point estimation*, we estimate the population parameter $\theta$ using an estimator $\hat{\theta}$
- In *interval estimation*, we quantify how uncertain about the population parameter $\theta$
- **Example** - you want to estimate how tall your friend is
	- Point estimation: "It is estimated at 170 cm"
	- Interval estimation: "It is somewhere between 160 and 180 cm"

#### Frequentist 95% confidence interval
- $T_\alpha(y)$ is a 100(1-$\alpha$)% confidence interval for $\alpha \in (0,1)$
- If $\alpha=0.05$ we call $T_{0.05}$ the 95% confidence interval
	- It means the probability of $\theta \in T_{0.05}(y) = 95\%$ 
- Funny fact:
	- Confidence interval means before we draw the sample y, we know that there is a 95% chance we will draw a dataset that gives an interval that covers the true $\theta$
	- Confidence interval does not mean after we draw the sample y, the true $\theta$ has a 95% chance with the interval we obtained
	- The population parameter $\theta$ is not random, it is fixed

#### Confidence interval for normal mean, known variance

- Consider a given observed dataset $y$ with n data points and $\bar{y}$ is the sample mean
- We assume $\sigma^2$ is known but $\mu$ is not
- We know that $\bar{y}\sim\mathcal{N}(\mu,\frac{\sigma^2}{n})$
- Which then means that $\frac{\bar{y}-\mu}{\sigma/\sqrt{n}}\sim\mathcal{N}(0,1)$
- We are trying to find $$\mathbb{P}(\theta^-\leq\frac{\bar{y}-\mu}{\sigma/\sqrt{n}}\leq\theta^+)=0.95$$
- $z = \frac{\bar{y}-\mu}{\sigma/\sqrt{n}}$ and so it has a density function $\frac{1}{\sqrt{2\pi}}\exp(-\frac{z^2}{2})$
$$\begin{align}
\mathbb{P}(\theta^-\leq\frac{\bar{y}-\mu}{\sigma/\sqrt{n}}\leq\theta^+)&=0.95\\
\int_{\theta^-}^{\theta^+}p(z|0,1)dz &=0.95\\
2\int_{0}^{\theta^+}p(z|0,1)dz &=0.95\;\;\;\;\text{Normal distribution is symmetric}\\
2\int_{0}^{\theta^+}\frac{1}{\sqrt{2\pi}}\exp(-\frac{z^2}{2})dz &=0.95\\
\sqrt{\frac{2}{\pi}}\int_{0}^{\theta^+}\exp(-\frac{z^2}{2})dz &=0.95\\
\text{erf}(\frac{z}{\sqrt{2}})\Biggr|^{\theta^+}_0 &=0.95\\
\text{erf}(\frac{\theta^+}{\sqrt{2}}) &= 0.95\;\;\;\;\text{erf(0) = 0}\\
\theta^+&\approx1.96
\end{align}$$

This means that $\mathbb{P}(-1.96\leq\frac{\bar{y}-\mu}{\sigma/\sqrt{n}}\leq1.96)=0.95$
- Rearranging gets you $\mathbb{P}(\bar{y}-1.96\frac{\sigma}{\sqrt{n}} \leq \mu \leq \bar{y}+1.96\frac{\sigma}{\sqrt{n}}) = 0.95$
- So the true population mean will be in between that range 95% of the time
- Generally: $$\mathbb{P}(\bar{y}-z_{\alpha/2}\frac{\sigma}{\sqrt{n}} \leq \mu \leq \bar{y}+z_{\alpha/2}\frac{\sigma}{\sqrt{n}}) = 1-\alpha$$

#### Confidence intervals for normal mean, unknown variance

- We are given an observed dataset $y$ with $n$ data points
- Both $\mu$ and $\sigma^2$ is unknown
- We must use the unbiased estimator $\hat{\sigma}^2_{\text{unbiased}} = \frac{1}{n-1}\sum_{i=1}^n(y_i-\bar{y})^2$ 
- The random variable $\frac{\bar{y}-\mu}{\hat{\sigma}^2_{\text{unbiased}}/\sqrt{n}}$ is no longer normally distributed, so $z_{a/2}$ cannot be used as it comes from $\mathcal{N}(0,1)$
- Instead, the random variable $\frac{\bar{y}-\mu}{\hat{\sigma}^2_{\text{unbiased}}/\sqrt{n}}$ follows the **student t-distribution** with n-1 degrees of freedom
- The confidence interval using student t-distribution is now $$T_\alpha = [\bar{y}-t_{\alpha/2,n-1}\frac{\hat{\sigma}^2_{\text{unbiased}}}{\sqrt{n}}, \bar{y}+t_{\alpha/2,n-1}\frac{\hat{\sigma}^2_{\text{unbiased}}}{\sqrt{n}}]$$
- The value $t_{\alpha/2,n-1}$ is the 100(1-$\alpha$/2)th percentile of the standard Student t-distribution with n-1 degree-of-freedom
- Must read off table or software, too difficult to calculate

#### Confidence interval for difference of normal means

- We are given two sets of data $y_A$ and $y_b$, where $y_A$ is a realisation of a RV $Y_A$ and $y_b$ is a realisation of RV $Y_B$
- We believe $Y_A\sim\mathcal{N}(\mu_A, \sigma^2_A), Y_B\sim\mathcal{N}(\mu_B,\sigma^2_B)$
- Both means are unknown and variances are known
- We now want to know is there difference between the two samples
- We build a confidence interval for population mean difference $\mu_A - \mu_B$

- $\hat{\mu}_A\sim\mathcal{N}(\mu_A,\frac{\sigma_A^2}{n_A}),\;\;\;\;\;\hat{\mu}_B\sim\mathcal{N}(\mu_B,\frac{\sigma_B^2}{n_B})$ 

- Assuming the samples are independent $\mathbb{V}[\hat{\mu}_A - \hat{\mu}_B] = \mathbb{V}[\hat{\mu}_A] + \mathbb{V}[\hat{\mu}_B]$
- $\therefore$ $$\hat{\mu}_A - \hat{\mu}_B\sim\mathcal{N}(\mu_A = \mu_B,\frac{\sigma_A^2}{n_A}+\frac{\sigma_B^2}{n_B})$$
- Since $Z = \frac{X-\mu}{\sigma} \sim \mathcal{N}(0,1)$  
$$\hat{\mu}_A - \hat{\mu}_B \sim N\left(\mu_A - \mu_B, \frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}\right) \iff \frac{(\hat{\mu}_A - \hat{\mu}_B) - (\mu_A - \mu_B)}{\sqrt{\frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}}} \sim N(0, 1)
$$
So the confidence intervals are $$T_\alpha = \left[ 
\hat{\mu}_A - \hat{\mu}_B - z_{\alpha/2}\sqrt{\frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}}, 
\hat{\mu}_A - \hat{\mu}_B + z_{\alpha/2}\sqrt{\frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}}
\right]
$$
#### Confidence interval for difference of normal means with unknown variance

- Apparently student-t distribution is too difficult for this course, so we're just doing the same thing as known variance
- The way to calculate unbiased variance estimators for the distributions:
	- $\hat{\sigma}_A^{\text{unbiased}} = \frac{1}{n_A - 1} \sum_{i=1}^{n_A} (y_i^A - \bar{y}_A)^2$
	- $\hat{\sigma}_B^{\text{unbiased}} = \frac{1}{n_B - 1} \sum_{i=1}^{n_B} (y_i^B - \bar{y}_B)^2$
- And plug them into the same confidence intervals as before:$$T_\alpha = \left[ 
\hat{\mu}_A - \hat{\mu}_B - z_{\alpha/2}\sqrt{\frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}}, 
\hat{\mu}_A - \hat{\mu}_B + z_{\alpha/2}\sqrt{\frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}}
\right]$$
### Hypothesis Testing

#### Null hypothesis and alternative hypothesis
- $H_0$  :  Null hypothesis
- $H_1$  :  Alternative hypothesis
- 'What is the probability of seeing $y$ given the null hypothesis is true'
	- $\mathbb{P}(y\mid H_0)$ is called the **p-value**
	- Small $p$-value means we have lots of evidence against the null

#### P-value of testing normal mean with known variance: two-sided test
- Dataset $y$, believed to be drawn from $Y\sim\mathcal{N}(\mu,\sigma^2)$ where $\sigma^2$ is known and $\mu$ is unknown $$\begin{align}H_0 : \mu &= \mu_{\text{guess}}\\H_A : \mu &\neq \mu_{\text{guess}}\end{align}$$
- How small is probability of $\mathbb{P}(\hat{\mu}\mid\mu = \mu_{\text{guess}})$
- Estimate the mean from the sample set
- Therefore we can assume that $\bar{y}\sim\mathcal{N}(\mu_{\text{guess}}, \sigma^2/n)$ 
- And so: $\frac{\bar{y} - \mu_{\text{guess}}}{\sigma/\sqrt{n}}\sim\mathcal{N}(0,1)$
- We're trying to find evidence against the null so we try to find $\mathbb{P}(\text{NOT}(\frac{\bar{y} - \mu_{\text{guess}}}{\sigma/\sqrt{n}}\sim\mathcal{N}(0,1)))$ 
Let $z_{\bar{y}} = \frac{\bar{y} - \mu_{\text{guess}}}{\sigma/\sqrt{n}}$ 
- To find $\mathbb{P}(\text{NOT}( z_{\bar{y}}\sim\mathcal{N}(0,1))) = 1 - \mathbb{P}(z_{\bar{y}}\sim\mathcal{N}(0,1))$ 
 - $= 1 - \mathbb{P}(-z_{\bar{y}} \leq Z \leq z_{\bar{y}})$
 - $= \mathbb{P}(Z\leq -z_{\bar{y}}) + \mathbb{P}(z_{\bar{y}} \leq Z)$
 - $p = 2\mathbb{P}(Z\leq -z_{\bar{y}})$
If p is small then we have strong evidence against the null, otherwise we have no conclusion

#### P-value of testing normal mean with known variance: two-sided test
- Same assumptions as before however $$\begin{align}H_0 : \mu &\leq \mu_{\text{guess}}\\H_A : \mu &> \mu_{\text{guess}}\end{align}$$
- Similarly, $p = \mathbb{P}(Z> z_{\bar{y}})$ 
#### The p-value for hypothesis testing of normal mean with known variance
- Same assumptions as before
- We have a guess $\mu_{\text{guess}}$
- Steps:
	- Calculate the maximum likelihood estimator of mean = $\bar{y}=\frac{1}{n}\sum y_i$
	- Perform standardisation to get $z_{\bar{y}} = \frac{\bar{y} - \mu_{\text{guess}}}{\sigma/\sqrt{n}}$
	- Calculate the p-value: $$p = \begin{cases} 
2\left(1 - P(Z < |z|)\right) & H_0 : \mu = \mu_{\text{guess}} \quad \text{vs} \quad H_A : \mu \neq \mu_{\text{guess}} \\
1 - P(Z < z) & H_0 : \mu \leq \mu_{\text{guess}} \quad \text{vs} \quad H_A : \mu > \mu_{\text{guess}} \\
P(Z < z) & H_0 : \mu \geq \mu_{\text{guess}} \quad \text{vs} \quad H_A : \mu < \mu_{\text{guess}}
\end{cases}
$$
#### The p-value for hypothesis testing of normal mean with unknown variance
- Same assumptions as before except known $\sigma^2$ is unknown as well
	- Calculate sample mean $\bar{y}$
	- Calculate unbiased estimator of variance $\hat{\sigma}^2_{\text{unbiased}}$
	- Perform standardisation to get t-score $t_{\bar{y}} = \frac{\bar{y} - \mu_{\text{guess}}}{\hat{\sigma}^2_{\text{unbiased}} / \sqrt{n}}$
	- Calculate p-value: $$p = \begin{cases} 
2\left(1 - P(T < |t|)\right) & H_0 : \mu = \mu_{\text{guess}} \quad \text{vs} \quad H_A : \mu \neq \mu_{\text{guess}} \\
1 - P(T < t) & H_0 : \mu \leq \mu_{\text{guess}} \quad \text{vs} \quad H_A : \mu > \mu_{\text{guess}} \\
P(T < t) & H_0 : \mu \geq \mu_{\text{guess}} \quad \text{vs} \quad H_A : \mu < \mu_{\text{guess}}
\end{cases}
$$
#### The p-value for hypothesis testing of difference of normal mean, known variance
- The hypothesis testing is $$\begin{align*} H_0 &: \mu_A = \mu_B \\ H_A &: \mu_A \neq \mu_B \end{align*}$$
- Assuming null is true $$\bar{y}_A - \bar{y}_B \sim N\left(0, \frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}\right)$$
- The z-score $$ z_{\bar{y}_A - \bar{y}_B} = \frac{\bar{y}_A - \bar{y}_B}{\sqrt{\frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}}} $$
- The p-value $$p = 2\mathbb{P}(Z < -|z_{\bar{y}_A - \bar{y}_B}|)$$
**One-sided test**
- Hypothesis test is $$\begin{align*} H_0 &: \mu_A \geq \mu_B \\ H_A &: \mu_A < \mu_B \end{align*}$$
- Then $$p = \mathbb{P}(Z < z_{\bar{y}_A - \bar{y}_B})$$