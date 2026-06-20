---
tags:
  - bil403
  - graph-theory
  - definition
---

# Graph — Basic Definitions

Related: [[Graph Theory MOC]] · [[Graph Types]] · [[Adjacency and Degree]]

> [!note] Definition — Graph
> A **graph** $G = (V, E)$ is a pair of sets such that $E \subseteq [V]^2$ :
> - $V$: a **nonempty** set of vertices
> - $E$: a set of edges
>
> Each edge has either **one or two** vertices associated with it, called its **endpoints**. An edge is said to **connect** its endpoints.

The edge set is written as the 2-element subsets of $V$:
$$E = \big\{\, \{i, j\} \;\big|\; i, j \in V \,\big\}$$

Equivalent notations for an edge:  $\{i,j\} \;=\; e_{ij} \;=\; ij \;=\; (i,j)$

> [!info] Terminology bridge
> The same concept appears under different names across fields — common in social network analysis:
>
> | | Graph | Network | Social web |
> |---|---|---|---|
> | Points | vertex | node | actor |
> | Lines | edge | link | tie |

## Size measures

> [!note] Definition — Order and size
> - $|V| = n$ → the **order** of the graph
> - $|E| = m$ → the **size** of the graph

> [!example] Example
> With $V = \{a, b, c, d, e\}$ and $E = \{ab, ae, be, bd, ce\}$ (note: $bc$ was crossed out in the lecture):
> $\Rightarrow n = 5,\quad m = 5$

## Finite / infinite
- **Infinite graph:** an infinite vertex set *or* an infinite number of edges.
- **Finite graph:** finite $V$ and finite $E$. → *In this course we always work with finite graphs.*

## Notation
Vertices can be labelled with integers, letters, or any other names. To emphasize membership in a particular graph:
$$V = V(G), \qquad E = E(G)$$

---
> [!tip]- Code (NetworkX)
> ```python
> import networkx as nx
> G = nx.Graph()
> G.add_nodes_from(['a','b','c','d','e'])
> G.add_edges_from([('a','b'),('a','e'),('b','e'),('b','d'),('c','e')])
> G.number_of_nodes()   # n = 5
> G.number_of_edges()   # m = 5
> ```
