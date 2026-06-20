---
tags:
  - bil403
  - graph-theory
  - definition
---

# Adjacency and Degree

Related: [[Graph — Basic Definitions]] · [[Handshaking Theorem]] · [[Degree Sequences and Havel–Hakimi]]

## Adjacency and incidence

> [!note] Definition — Adjacent
> The two vertices in an edge (its endpoints) are **adjacent**. Two edges that share a **common endpoint** are **adjacent edges**.

> [!note] Definition — Incident
> If $e = uv$ is an edge, then $u$ and $e$ are **incident**; likewise $v$ and $e$.

Two adjacent vertices are also called **neighbors** of each other.

## Neighborhood

> [!note] Definition — Open and closed neighborhood
> The set of neighbors of a vertex $v$ is its **neighborhood**, denoted $N(v)$. This is the **open neighborhood**.
> Adding $v$ itself gives the **closed neighborhood**:
> $$N[v] = N(v) \cup \{v\}$$

For a set of vertices: if $A \subseteq V$ then
$$N(A) = \bigcup_{v \in A} N(v)$$

> [!example] Example
> If $N(a) = \{b, e\}$ then $N[a] = \{a, b, e\}$.

## Degree

> [!note] Definition — Degree
> The **degree** of a vertex in an undirected graph is the number of edges incident with it; denoted $\deg(v)$.
> **A loop counts as 2 edges.**

> [!example] Example — Graph $G$ (lecture example)
> $\deg(a)=2,\ \deg(b)=4,\ \deg(c)=4,\ \deg(d)=1,\ \deg(e)=3,\ \deg(f)=4,\ \deg(g)=0$
> $N(a)=\{b,f\},\quad N(c)=\{b,f,e,d\}$

## Special degree values

> [!note] Definition — Isolated and pendant
> - $\deg(v) = 0$ → the vertex is **isolated**.
> - $\deg(v) = 1$ → the vertex is **pendant** (end-vertex).

## Maximum / minimum degree

> [!note] Definition
> - $\Delta(G)$ → the **maximum degree** of the graph
> - $\delta(G)$ → the **minimum degree** of the graph

For every vertex the following bound holds:
$$0 \le \delta(G) \le \deg(v) \le \Delta(G) \le n - 1$$

> [!example] Example
> $G$: $\delta(G)=0,\ \Delta(G)=4$ · $H$: $\delta(H)=1,\ \Delta(H)=6$

## Degree in directed graphs

> [!note] Definition — In- and out-degree
> If $(u, v) \in E(G)$: $u$ is **adjacent to** $v$; $v$ is **adjacent from** $u$. $u$ is the **initial** vertex, $v$ the **terminal** vertex.
> - $\deg^{-}(v)$ → **indegree**: number of edges with $v$ as terminal vertex
> - $\deg^{+}(v)$ → **outdegree**: number of edges with $v$ as initial vertex
>
> A loop contributes **1** to both indegree and outdegree.

> [!important] Theorem — Directed degree sum
> $$\sum_{v \in V} \deg^{-}(v) = \sum_{v \in V} \deg^{+}(v) = |E| = m$$
> Because each edge contributes 1 to indegree and 1 to outdegree.

Undirected counterpart → [[Handshaking Theorem]]

---
> [!tip]- Code (NetworkX)
> ```python
> G.degree('a')            # degree of one vertex
> dict(G.degree())         # all degrees
> list(G.neighbors('a'))   # N(a)
> max(d for _, d in G.degree())   # Δ(G)
> # Directed:
> D.in_degree('v'), D.out_degree('v')
> ```
