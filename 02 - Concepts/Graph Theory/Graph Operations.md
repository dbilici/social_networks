---
tags:
  - bil403
  - graph-theory
  - definition
---

# Graph Operations

Related: [[Subgraphs]] · [[Complement Graph]] · [[Graph Theory MOC]]

Deleting/adding vertices and edges from a graph $G = (V, E)$, and combining two graphs.

## Vertex/edge deletion and addition

> [!note] Definition — Summary formulas
> $$G - v = (V - \{v\},\; E')\qquad E' = \text{edges not incident to } v$$
> $$G - e = (V,\; E - \{e\})$$
> $$G + e = (V,\; E + \{e\})$$

- **$G - v$ (vertex deletion):** removes $v$ and all edges incident to it. The result is the subgraph **induced** by $V - \{v\}$. → [[Subgraphs]]
- **$G - e$ (edge deletion):** removes only edge $e$; vertices remain. The result is a **spanning subgraph**.
- **$G + e$ (edge addition):** adds a new edge. $G$ is a **spanning subgraph** of $G + e$.

> [!info] Bulk deletion
> $v$ and $e$ can also be **subsets**: $G - U$ for $U \subseteq V$, $G - X$ for $X \subseteq E$.

> [!example] Example (from lecture)
> For $U = \{t, x\}$, $G - U$ deletes both vertices and the incident edges. For $X = \{tw, ux, vx\}$, $G - X$ deletes only those three edges.

## Union

> [!note] Definition — Union
> For $G_1 = (V_1, E_1)$ and $G_2 = (V_2, E_2)$:
> $$G_1 \cup G_2 = (V_1 \cup V_2,\; E_1 \cup E_2)$$

> [!example] Example
> ```mermaid
> graph LR
>   subgraph G1
>     a1((a)) --- b1((b)); a1 --- d1((d)); b1 --- e1((e)); b1 --- c1((c)); e1 --- c1
>   end
>   subgraph G2
>     a2((a)) --- b2((b)); b2 --- d2((d)); b2 --- c2((c)); c2 --- f2((f))
>   end
> ```
> In the union, all vertices and edges of both graphs are merged into one graph (shared vertices are unified).

---
> [!tip]- Code (NetworkX)
> ```python
> G.remove_node('v')          # G - v
> G.remove_edge('u','v')      # G - e
> G.add_edge('u','v')         # G + e
> U = nx.union(G1, G2)        # if vertex sets are disjoint
> C = nx.compose(G1, G2)      # merges shared vertices (V1 ∪ V2)
> ```
