---
tags:
  - bil403
  - exercise
  - graph-theory
---

# Exercises — Graph Theory 2

Related topics: [[Subgraphs]] · [[Complement Graph]] · [[Distance and Diameter]] · [[Connectedness and Components]] · [[Connectivity Measures]] · [[Connectedness in Directed Graphs]] · [[Counting Paths]]

---

### Q1. Induced vs spanning
Of the operations $G - v$ and $G - e$, which produces an induced subgraph and which a spanning subgraph?

> [!success]- Solution
> $G - v$ → **induced** subgraph (remaining vertices and all edges among them). $G - e$ → **spanning** subgraph (all vertices remain, only one edge is dropped). (→ [[Subgraphs]], [[Graph Operations]])

### Q2. Size of the complement
A graph on $n = 6$ vertices has $m = 7$ edges. How many edges are in its complement?

> [!success]- Solution
> $m_{\overline{G}} = \binom{6}{2} - 7 = 15 - 7 = 8$. (→ [[Complement Graph]])

### Q3. Diameter
What is the diameter of $P_5$ (path on 5 vertices) and $C_6$?

> [!success]- Solution
> $P_5$: 4 edges between the two endpoints → $\operatorname{diam} = 4$. $C_6$: the two farthest vertices are opposite, 3 edges → $\operatorname{diam} = 3$. (→ [[Distance and Diameter]])

### Q4. Cut vertices
How many cut vertices does a path $P_n$ ($n \ge 3$) have?

> [!success]- Solution
> All **interior vertices** except the two ends: $n - 2$ of them. Removing any interior vertex splits the path in two. (→ [[Connectedness and Components]])

### Q5. Whitney inequality
If a graph has $\delta(G) = 4$, what can we say about $\kappa(G)$ and $\lambda(G)$?

> [!success]- Solution
> $\kappa(G) \le \lambda(G) \le \delta(G) = 4$. So both are **at most 4** (exact value depends on the graph). (→ [[Connectivity Measures]])

### Q6. Strong vs weak connectivity
Is a directed "cycle" $a \to b \to c \to a$ strongly or weakly connected? What about $a \to b \to c$ (one direction)?

> [!success]- Solution
> The cycle: every vertex reaches every other following directions → **strongly connected**. One-directional $a \to b \to c$: no path from $c$ to $a$ → not strong; but the undirected version is connected → **weakly connected**. (→ [[Connectedness in Directed Graphs]])

### Q7. Path counting (matrix)
Let $A$ be the adjacency matrix of cycle $C_4$. What do the diagonal entries of $A^2$ count, and what is their value?

> [!success]- Solution
> The diagonal entry $(A^2)_{ii}$ counts **closed walks** of length 2 from $v_i$ to $v_i$. In $C_4$ each vertex has 2 neighbors; going to each and back → $(A^2)_{ii} = 2 = \deg(v_i)$. (In general $(A^2)_{ii} = \deg(v_i)$.) (→ [[Counting Paths]])

### Q8. (Conceptual) Bridge and cycle
Can an edge that **belongs to a cycle** be a cut edge (bridge)?

> [!success]- Solution
> No. If the edge is part of a cycle, even after removing it the endpoints are still connected via the other path in the cycle → the number of components does not increase → not a bridge. **Bridges are edges that belong to no cycle.** (→ [[Connectedness and Components]])
