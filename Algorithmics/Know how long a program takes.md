Subjects/ Topics: #BigO #BigTheta 

- Big O notation

Think of algorithm that finds minimum element in array
- **Time Complexity** T(n)
- Worst case - array values in decreasing order
- Best case - minimum value is in first position

- The worst-case running time (time complexity) of an algorithm is a function $T:\mathbb{N}\to\mathbb{N}$ where
	- $T(n)$ is the maximum number of primitive operations the algorithm uses on inputs of size $n$
- Gives a guarantee that the algorithm will not take longer
- Average-case time complexity
	- Assumes all inputs are equally likely

#### Big-Theta Notation
- $f(n)$ is $\Theta(g(n))$ if there exists constants $c>0$, $d>0$ and $N\in\mathbb{N}$ such that $$cg(n)\leq f(n)\leq dg(n) \;\text{for}\;n\geq N$$
The $\Theta$ notation captures the idea that two functions have the same rate of growth
- **Advantages**
	- Compare algorithms by comparing rates of growth
	- Can estimate algorithm running  times on large inputs by measuring running time on a small input
- **Disadvantages**
	- Cannot compare algorithms whose running times have the same rate of growth
	- For small inputs, Big-Theta can be misleading

To avoid having to analyse a program with if statements where the second for loop may or may not run, we can make upper and lower bounds
- Big-O notation gives the upper bound for rate of growth
- Big-Omega notation gives the lower bound for rate of growth

##### Big-O notation
- $f(n)$ is $O(g(n))$ if there exists constants $d>0$ and $N\in\mathbb{N}$ s.t. $$f(n) \leq dg(n)\;\text{for}\; n\geq N$$
##### Big-Omega notation
- $f(n)$ is $\Omega(g(n))$ if there exists constants $c>0$ and $N\in\mathbb{N}$ s.t. $$f(n) \leq dg(n)\;\text{for}\; n\geq N$$
- And so $f(n)$ is $\Theta(g(n))$ iff $$f(n) = O(g(n))\;\;\;\text{and}\;\;\; f(n)=\Omega(g(n))$$
#### Use and Misuse

- Big-O notation is most commonly used
- Often people say they have a $O(n^2)$ algorithm when in fact they have a $\Theta(n^2)$
- A $O(n^2)$ algorithm is also a $O(n^3)$ algorithm