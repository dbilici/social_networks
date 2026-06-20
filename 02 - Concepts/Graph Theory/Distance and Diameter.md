---
tags:
  - bil403
  - graph-theory
  - definition
  - theorem
---

# Distance and Diameter

Related: [[Paths, Circuits and Walks]] · [[Connectedness and Components]] · [[Counting Paths]]

> [!note] Definition — Distance
> In a connected graph $G$, the **distance** $d_G(u, v)$ from vertex $u$ to vertex $v$ is the **minimum length** of a $u$–$v$ path (the shortest path).

> [!example] Example (lecture graph $G$)
> $d(v_1, v_1) = 0,\quad d(v_1, v_2) = 1,\quad d(v_1, v_6) = 2,\quad d(v_1, v_7) = 3,\quad d(v_1, v_{10}) = 4$

## Properties of distance (it is a metric)

In a simple graph, distance satisfies the four axioms of a **metric**:

> [!important] Properties
> 1. $d(u, v) \ge 0$  (non-negative)
> 2. $d(u, v) = 0 \iff u = v$
> 3. $d(u, v) = d(v, u)$  (**symmetry** — in an undirected graph)
> 4. $d(u, w) \le d(u, v) + d(v, w)$  (**triangle inequality**)

> [!note]- Proof ideas
> **(1)** Length = number of edges $\ge 0$.
> **(2)** If $u = v$ there is a zero-length path (itself); if $u \neq v$ at least one edge is needed, so $d > 0$.
> **(3)** In an undirected graph every $u$–$v$ path is also a $v$–$u$ path in reverse, of equal length. So the minima are equal.
> **(4)** Concatenating a shortest $u$–$v$ path with a shortest $v$–$w$ path gives a **walk** from $u$ to $w$ of length $d(u,v) + d(v,w)$. The shortest $u$–$w$ path can be no longer. $\blacksquare$

## Diameter

> [!note] Definition — Diameter
> The **diameter** $\operatorname{diam}(G)$ of a connected graph $G$ is the **maximum distance** between any pair of vertices:
> $$\operatorname{diam}(G) = \max_{u, v \in V} d(u, v)$$

> [!example] Example
> In the lecture graph above, $\operatorname{diam}(G) = 4$.

> [!tip] Social-network link
> The "six degrees of separation" idea points to the **small diameter** of social networks. This relates directly to the **small-world** property covered later in the course.

---
> [!tip]- Code (NetworkX)
> ```python
> nx.shortest_path_length(G, 'v1', 'v10')   # d(u,v)
> nx.diameter(G)                             # diameter (requires connected graph)
> dict(nx.all_pairs_shortest_path_length(G)) # all distances
> ```
