Subjects/ Topics: #Combinatorics #SetTheory 

Combinatorics is counting

$|A\cup B|=|A| + |B| -|A\cap B|$
**Proof**:

$|A\cup B|=|A\cup (B \setminus A)| = |A| + |B\setminus A|$
$|B|=|(B \setminus A) \cup (B\cap A)| = |B\setminus A| + |B\cap A||$

How many ways to form a 3-letter string from alphabet {1,0}:
$2^3=8$

How many ways to form a 3 letter string from alphabet {A, B, C}:
$3^3 = 27$

The **product** rule: cartesian product

$|A\times B| = |P|\cdot|Q|$

The **sum** rule: 

In a cafe you have soup xor salad, 2 soups and 4 salads, how many choices do you have:
|soup $\cup$ salad| = |soup| + |salad| - |soup $\cap$ salad|
|soup $\cap$ salad| = 0 since xor
$\therefore$ 6 options

The **subtraction** rule:

How many subsets of X = {1,2,3} contain at least 2 elements

Let $S \subset X$ that contains at least 2 elements
Let $P = 2^X$ be the power set of X
$S=P\setminus S^C$
$S = P\setminus \set{\text{set containing 0} \cap \text{set containing 1}}$
$S = P \setminus (\set{\set{1,2,3}\cup \set{\varnothing}})$
$|S| = |P| - (3+1)$
$|S| = 8 - 4 = 4$

Floor function: A $\mathbb{R}\to\mathbb{Z}$ mapping $⌊x⌋ = max(m\in\mathbb{Z}\mid m<=x)$ 

#### Permutations and Factorial

A permutation (denoted by $\pi$ or $\sigma$) is an ordered arrangement of a set of distinct objects

$k! = \left\{\begin{matrix}1\;\;\;\;\;\;\;\;\;\;\;\;\text{k = 0 base case}\\ k(k=1)!\;\;\text{k > 0 base case}\end{matrix}\right.$ 

How many permutations of the string HAPPY is there:
$\frac{5!}{2!} = 60$

Permutation also known as the **multinomial coefficient**
$$\frac{n!}{n_1!n_2!...n_r!}=:\begin{pmatrix}n\\n_1,n_2...n_r\end{pmatrix}$$

#### Combinations
##### $$nCk = \begin{pmatrix}n\\k\end{pmatrix} = \frac{n!}{k!(n-k)!}$$
nC0 = nCn = 1
nCk = nC(n-k)
nCk + nC(k+1) = (n+1)C(k+1)

$\sum_{k=0}^{⌊n/2⌋} \begin{pmatrix}n-k\\k\end{pmatrix}=F_{n+1}$

There are $\begin{pmatrix}n+k-1\\k\end{pmatrix}$ ways to choose k elements from a n-set if repetitions of elements are allowed

A farm has cats and dogs. How many ways can you select three pets to take home:
$2^3 = 8$ total cases
There are repetitions within the combination e.g. 112 and 211
Therefore without repetitions, there are 4 cases or $\begin{pmatrix}2+3-1\\3\end{pmatrix} = 4$ 
