- Lots of problems involve searching
- Usually a trade-off of
	- Speed
	- Memory
	- Optimality
	- Completeness

#### Single-state problem formulation
1. Initial state
2. Actions, or successor function
3. Goal test
	1. Explicit, e.g. x = "at Bucharest"
	2. Implicit, e.g. Checkmate(x)
4. Path cost (additive)

#### Solutions to searching a tree of decisions
- DFS
- BFS
- Depth-limited search
	- DFS with a set depth limit of $n$
- Iterative deepening search (IDS)

**IDS**
- IDS performs a series of depth-limited depth-first searches (DFS) with increasing depth limits. It incrementally increases the depth limit, exploring deeper parts of the tree while retaining the completeness of BFS
- Steps:
	1. Set a depth limit (initially 0)
	2. Run a depth-limited DFS
	3. Increase the depth limit by 1 and repeat the depth-limited DFS, exploring deeper nodes each time
	4. Continue the process until a goal is found or the entire search space is exhausted
- IDS is more space efficient than BFS, BFS has a space complexity of $O(b^d)$ however IDS has a space complexity of $O(bd)$, due to the fact that it only needs to store the current path as it utilises DFS, therefore it is linear in depth.

**Bidirectional Search**
- Do two searches
	- One starting from the initial state
	- The second starting at the goal state
- Motivation:
	- $b^{d/2} + b^{d/2}$ is smaller than $b^d$
- At each iteration of the search:
	- Check if a node is in the fringe/open of the other before expansion
	- If yes, a solution has been found

