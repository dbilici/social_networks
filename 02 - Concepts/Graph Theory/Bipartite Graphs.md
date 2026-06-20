---
tags:
  - bil403
  - graph-theory
  - special-graph
  - exam-relevant
---

# Bipartite Graphs

Related: [[Special Graphs]] · [[Graph — Basic Definitions]] · [[Graph Theory MOC]]

> [!note] Definition — Bipartite graph
> A simple graph $G$ is **bipartite** if its vertex set $V$ can be partitioned into **two disjoint sets** $V_1$ and $V_2$ such that **every edge** connects a vertex in $V_1$ to a vertex in $V_2$ (so no edge connects two vertices within $V_1$ or two vertices within $V_2$).
> When this holds, the pair $(V_1, V_2)$ is a **bipartition** of $G$.

> [!example] Example — $C_6$ is bipartite
> $V_1 = \{v_1, v_3, v_5\}, \quad V_2 = \{v_2, v_4, v_6\}$
>
> Counterexample: $K_3$ (triangle) is **not bipartite**.

## Characterization by coloring

> [!important] Theorem
> A simple graph is **bipartite if and only if** it is possible to assign one of two colors to each vertex so that **no two adjacent vertices** receive the same color.
> *(This is a special case of graph coloring.)*

> [!tip] Practical test
> No graph containing an **odd cycle** can be bipartite. To test, try a 2-coloring via BFS/DFS; if a conflict appears, it is not bipartite.

## Complete bipartite graph $K_{m,n}$

> [!note] Definition
> The **complete bipartite graph** $K_{m,n}$ is a bipartite graph in which the vertices of one part are connected to **all** the vertices of the other part.

$$n = m + n \ (\text{order}),\qquad m_{\text{size}} = mn$$
$$\delta = \min(m, n),\qquad \Delta = \max(m, n)$$

- $K_{1,n}$ is specifically called a **star**.

> [!example] Examples
> $K_{2,3}, \quad K_{3,5}, \quad K_{2,4}$

## Why important? (matching)

Bipartite graphs are widely used to model relationships between **two different types** of vertices — this problem is called **matching**:
- Job assignments
- Marriages

## Generalization: $k$-partite graphs

> [!note]
> If the vertex set is partitioned into $k$ disjoint sets and edges only go between different sets, the graph is **$k$-partite**. In **complete $k$-partite** graphs, all vertex pairs in different sets are connected.
>
> E.g. $K_{2,3}$ → 2-partite; $K_{1,1,1,1} = K_4$ → 4-partite; $K_{2,2,2}$ → 3-partite.

---
> [!tip]- Code (NetworkX)
> ```python
> from networkx.algorithms import bipartite
> K23 = nx.complete_bipartite_graph(2, 3)
> bipartite.is_bipartite(K23)          # True
> nx.is_bipartite(nx.cycle_graph(6))   # True  (C6)
> nx.is_bipartite(nx.complete_graph(3))# False (K3)
> ```
