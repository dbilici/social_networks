---
tags:
  - bil403
  - graph-theory
  - definition
---

# Incidence Matrix

Related: [[Adjacency List and Matrix]] · [[Adjacency and Degree]] · [[Graph Isomorphism]]

> [!note] Definition — Incidence matrix
> In an undirected graph $G = (V, E)$ with vertices $v_1, \dots, v_n$ and edges $e_1, \dots, e_m$, the **incidence matrix** $M$ is **$n \times m$**:
> $$m_{ij} = \begin{cases} 1 & \text{edge } e_j \text{ is incident with } v_i \\ 0 & \text{otherwise} \end{cases}$$
>
> *(Rows = vertices, columns = edges.)*

> [!example] Example (from lecture)
> For edges $e_1, e_2, e_3, e_4$:
> $$M = \begin{array}{c|cccc} & e_1 & e_2 & e_3 & e_4 \\ \hline v_1 & 1 & 1 & 0 & 0 \\ v_2 & 1 & 0 & 1 & 1 \\ v_3 & 0 & 1 & 1 & 0 \\ v_4 & 0 & 0 & 0 & 1 \end{array}$$

> [!important] Column rules
> - **Simple graph:** each column has exactly **two 1s** (the two endpoints of the edge).
> - **Multiple edges:** labelled and added as separate columns.
> - **Loop:** the column has only **one 1**.

> [!tip] Advantage
> A key advantage of the incidence matrix is that it can represent **nonbinary edges** — cases where an edge touches more than two vertices, e.g. $\{v_1, v_2, v_3\}$. *(This leads to **hypergraphs**.)*

## Comparison

| | size | good for |
|---|---|---|
| Adjacency matrix | $n \times n$ | adjacency queries, path counting ($A^r$) |
| Incidence matrix | $n \times m$ | edge-centric analysis, hypergraphs |

---
> [!tip]- Code (NetworkX)
> ```python
> M = nx.incidence_matrix(G)     # n × m sparse matrix
> M.todense()
> # for directed, with orientation: nx.incidence_matrix(D, oriented=True)
> ```
