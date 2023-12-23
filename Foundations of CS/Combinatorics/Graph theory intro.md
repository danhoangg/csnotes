Subjects/ topics: #GraphTheory #Algorithms

**What is a graph**
A graph consists of nodes that represent states and edges that represent relationships between these states

**Graph isomorphism**
![[isomorphism.png]]
These 3 graphs are the same

### VVEEMAD

**Definition** - Denote graph as $G(V,E)$ where $V$ is the set of vertices and $E$ is the set of edges
e.g. $V=\set{1,2,3}$, $E=\set{(1,1), (1,2), (3,2)}$

- From $E$, we get incidence information $M$
- $M$ can be expressed as incidence matrix  $$M=\begin{bmatrix}1&1&0&1\\2&1&0&0\\0&1&0&0\\0&0&1&1\end{bmatrix}$$
If i is the row and j is the column, then $M[i][j]$ represents how many connections there are between vertex $i$ and vertex $j$

- From $E$ we can get $A$, which stands for 'adjacency', like incidence matrix but doesn't care about direction of connection $$A=\begin{bmatrix}1&2&0&1\\2&1&1&0\\0&1&0&1\\1&0&1&1\end{bmatrix}$$
- $\therefore A=A^T$

- **Indegree:** number of edges come to the node
- **Outdegree:** number of edges leave from the node
- **Degree:** number of edges touching the node

- Degree-0 vertex is called **isolated**
- Degree-1 vertex is called **leaf**, useful in **trees**

**Theorem (Leonhard Euler, 1736)** - $$\text{The sum of degree of all nodes} = \sum^{|V|}_{i=1}deg_i = 2|E|$$
All graphs have even number of odd vertices

We ignore isolated nodes
- Graph theory is about interaction, no edge = no interaction, so we ignore isolated node
- Graphs where all nodes are isolated are **null graphs**, denoted by $N$

**Directed and undirected graphs**
- Directed graph - directed
- Undirected graph - undirected
- Undirected graph is not same as bidirected graph

### Simple graph, multi graph and pseudograph

- Pseudograph has self loop and multi edges
- Multigraphs have no self loop but has multi edges
- Simple graph has neither self loops or multi edges
- Multigraph can be converted into simple graph

**Converting multigraph to simple graph**

$E=\set{(3,5), (3,5)} \to E'\set{(3_a,5),(3_b,5),(3_a,3_b)}$

- Consider simple graph G with |V|=n
- **Null graph** $N_n$ is G with the smallest possible |E|
- **Complete graph** $K_n$ is G with the largest possible |E|
	- A complete graph is a graph in which all pairs of vertices is joined by an edge
	- $K_n$ for n=1 to 8
- A graph is sparse if $|E| << O(\frac{|V|(|V|-1)}{2}) = O(|V^2|)$
- A graph is dense if $|E| \approx O(|V^2|)$ 

#### Walk, trail, path, cycle
- A walk is a sequence in a graph
- A trail is a walk if distinct edges
- A path is a trail if distinct vertices except possible source = sink
- A cycle is a closed path (source = sink)

- A graph is connected if for any $i\in V,j\in V, i\neq j$ there is a path connecting $i$ to $j$
- A forest is an acyclic graph
- A tree is an acyclic connected graph
- A bipartite is graph that vertices can be divided into two parts such that there is no edges within each part

**Question** - How many triangles are there in $K_8$
- There are $\frac{1}{2k}\frac{n!}{(n-k)!}$ length-k cycles in $K_n$ 
#### $$\begin{align}\begin{pmatrix}n\\k\end{pmatrix}&\;\text{Number of ways to choose k node among n vertices}\\(k-1)!&\;\text{The number of orderings in the selected k-set}\\2&\;\text{Number of orientation of the cycle (clockwise and anticlockwise)}\\\frac{\begin{pmatrix}n\\k\end{pmatrix}(k-1)!}{2}&\;\text{By product rule and division rule}\end{align}$$
