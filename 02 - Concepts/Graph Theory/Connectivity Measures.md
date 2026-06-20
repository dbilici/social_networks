---
tags:
  - bil403
  - graph-theory
  - definition
  - theorem
  - exam-relevant
---

# Connectivity Measures

Related: [[Connectedness and Components]] · [[Adjacency and Degree]] · [[Special Graphs]]

Measures **numerically** how connected a graph is.

## Vertex cut and vertex connectivity

> [!note] Definition — Vertex cut set
> A subset $V' \subseteq V$ of $G = (V, E)$ is a **vertex cut set (separating cut)** if $G - V'$ becomes **disconnected**.

> [!example] Example (from lecture)
> In the given graph, $V' = \{b, d\}$ or $\{a, e\}$ are separating sets.

> [!note] Definition — Vertex connectivity
> The **vertex connectivity** $\kappa(G)$ of a noncomplete graph is the **minimum number of vertices** in a vertex cut set.

Special cases:
$$0 \le \kappa(G) \le n - 1$$
- $\kappa(G) = 0$ → $G$ is disconnected **or** $G = K_1$
- $\kappa(G) = 1$ → $G$ has a **cut vertex** (→ [[Connectedness and Components]])
- $\kappa(K_n) = n - 1$ → by definition (you cannot separate a complete graph; the result is a single vertex)

> [!tip] Interpretation
> The larger $\kappa(G)$, the more **connected** the graph (the more vertices you must remove to break it apart).

## Edge connectivity

> [!note] Definition — Edge connectivity
> $\lambda(G)$ is the **minimum number of edges** that must be removed to disconnect the graph.

## Whitney inequality

> [!important] Theorem — $\kappa \le \lambda \le \delta$
> $$\kappa(G) \;\le\; \lambda(G) \;\le\; \min_{v} \deg(v) = \delta(G)$$

> [!note]- Why $\lambda \le \delta$?
> Pick the minimum-degree vertex $v$ (degree $\delta$). Removing its $\delta$ incident edges isolates $v$ → the graph becomes disconnected. So removing $\delta$ edges is **always** enough; the minimum number $\lambda$ cannot exceed it. (For $\kappa \le \lambda$: an edge cut can be converted into a vertex cut.) $\blacksquare$

---
> [!tip]- Code (NetworkX)
> ```python
> nx.node_connectivity(G)    # κ(G)
> nx.edge_connectivity(G)    # λ(G)
> nx.minimum_node_cut(G)     # minimum vertex cut set
> nx.minimum_edge_cut(G)     # minimum edge cut
> ```
