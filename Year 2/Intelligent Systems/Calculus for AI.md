
### Differential Calculus
- Focuses on understanding the concept of a **derivative**
- In what contexts is **differential calculus** applied in AI?
	- **Backpropogation in Neural Networks**
	- **Rate of change analysis** - Hekps identify trends, anomalies and critical points, which are valuable for forecasting and anomaly detection
	- **Sensitivity Analysis** - asses how sensitive a model's output is to changes in its input or parameters
	- **Optimal decision making** - helps determine the best actions to take at each step to maximise long-term rewards
	- **Natural Language Processing** - helps measure the similarity between words or documents by computing gradients or partial derivatives, enabling applications like word vector representations
	- **Control systems** - control theory often involves differential equations and derivatives to model and control dynamic systems

### Integral Calculus
- The process of finding the accumulation of quantities or the area under a curve.
- In what contexts is **integral calculus** applied in AI?
	- **Data pre-processing and feature engineering** - can be used to pre-process data and create meaningful features to improve the performance of machine learning models
	- **Signal processing** - can be used to calculate properties like the total energy or area under a signal, may be essential for feature extraction and analysis
	- **Probability and Statistics** - employed in probability theory and stats, which are foundational to AI applications involving uncertainty and randomness
	- **Optimisation problems** - relevant in certain optimisation scenarios, e.g. in reinforcement learning, an AI agent might need to maximise the expected cumulative reward over time, which can be modelled as an integral of the reward function.
	- **Simulation and numerical methods** - often involve differential equations and integrating functions over time to model dynamic processes and study the behaviour of AI systems

### Limits
**Examples**
1. 
$$\lim_{x\to-2} \sqrt{x^2-6x+9} = 5$$
2. 
$$\begin{align}f(x) &=
\begin{cases}
3x - 4, & \text{if } x \neq 0 \\
7, & \text{if } x = 0
\end{cases}\\\\
\lim_{x\to0}f(x) &= 3(0) - 4 \\
\lim_{x\to0}f(x) &= -4
\end{align}
$$
It does not matter that $f(0) = 7$. For $x\neq 0$, and thus for all $x$ near $0$, $f(x)=3x-4$.