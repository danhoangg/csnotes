
$$S := \{d_1d_2d_3 | di ∈ {1, ..., 9}, d1 < d2 < d3\}$$
What is the size of S?

**Counting via bijection**

Fact 1 - $d_1 < d_2 < d_3$ $\implies$ $d_1\neq d_2\neq d_3$ 
Fact 2 - $d_1\neq d_2\neq d_3 \implies$ There is exactly one rising number
e.g., for a number {7,1,4}, the raising number is 147 and there is only one possible number

Hence bijection is,
		# of 3-digit numbers **and** # of ways of selecting 3 distinct digits
$\therefore |S| = \begin{pmatrix}9\\3\end{pmatrix}=84$

**Counting via polynomial**

**Example** You distribute 8 identical cookies among 3 children. Each child can receive at least 2 cookies and no more than 4 cookies. How many ways can you distribute?
It is the coefficient of $x^8$ in the expansion of $(x^2+x^3+x^4)^3$

**Example**  All the combinations of rolling 2 six sided die
Consider the polynomial $x^1 + x^2 + x^3 + x^4 + x^5 + x^6$ 
All the terms in $(x^1 + x^2 + x^3 + x^4 + x^5 + x^6)(x^1 + x^2 + x^3 + x^4 + x^5 + x^6)$
Where the power of x is the sum of the two die an the coefficient is how many ways there are to make that sum


**The Power series $G(x) = \sum a_k x^k$**

Consider a set of 1 element, {$e_1$}
- 1 way to select 0 items
- 1 way to select 1 item
- 0 ways to select 2 or more items
$\therefore 1+x^1$ 
Consider a set of 2 elements, {$e_1, e_2$}
- 1 way to select 0 items
- 2 way to select 1 item
- 1 way to select 2 items
- 0 ways to select 3 or more items
$\therefore 1+2x^1 + x^2$

Or $(1+x)^k$ 

**Sequence and generating function**

Given a sequence {1,1,1,1}, the generating function is $$1+x+x^2+x^3$$
The sequence {0,1,2,3} has generating function $x+2x^3+3x^3$

**Example**
A word must start with a prefix, followed by a vowel and ends in a suffix
prefix = {qu, s, t}
vowels = {a, i, oi}
suffixes = {d, ff, ck}

There are $3^3=27$ solutions
How many words length 5 are there?
If the power of each x in the generating function is the length of the word then:
$\begin{align}(qu + s + t)(a + i + oi)(d + ff + ck) &= (x^2 + x + x)(x + x + x^2)(x + x^2 + x^2) \\ &= 4x^3 +12x^4+9x^5+2x^6\end{align}$
So there are 9 words with length 5

**Coefficients in infinite sets**
$[x^{22}](x+x^2+...)^3$ is the same as $[x^{19}](x+x^2+...)^3$ which is $\begin{pmatrix}19+3-1\\19\end{pmatrix} = 210$

