---
tags:
  - bil403
  - graph-theory
  - definition
---

# Graph Types

Related: [[Graph — Basic Definitions]] · [[Adjacency and Degree]] · [[Graph Theory MOC]]

## Building blocks

> [!note] Definition — Loop
> An edge with the same endpoints, i.e. $e_{ii} = \{i, i\}$, is called a **loop**.

> [!note] Definition — Multiple edges
> There may be more than one edge between the same pair of vertices; these are **multiple edges**. The number of edges between a pair is the **multiplicity** of that edge.

> [!example] Example
> $V = \{a,b,c\}$, $E = \{ab, ab, bb, ac\}$ → multiplicity of $\{a,b\}$ is **2**, $bb$ is a loop. $m = 4,\; n = 3$.

## Directionality

> [!note] Definition — Directed graph
> In some graphs the edges may be **directed**. A graph with directed edges is a **directed graph (digraph)**. Directed edges are also called **arcs**.

## Simple graph

> [!note] Definition — Simple graph
> A graph with **no loops and no multiple edges** is a **simple graph**.

## Full table of types

| Type | Edges | Multiple edges? | Loops? |
|---|---|---|---|
| **Simple graph** | undirected | ❌ | ❌ |
| **Multigraph** | undirected | ✅ | ❌ |
| **Pseudograph** | undirected | ✅ | ✅ |
| **Simple directed** | directed | ❌ | ❌ |
| **Directed multigraph** | directed | ✅ | ✅ |
| **Mixed graph** | directed + undirected | ✅ | ✅ |

> [!tip] Mnemonic
> Constraints loosen left to right: simple → multigraph (multiples allowed) → pseudograph (loops also allowed). The directed side follows the same logic.

---
> [!tip]- Code (NetworkX)
> ```python
> nx.Graph()        # simple, undirected
> nx.DiGraph()      # simple, directed
> nx.MultiGraph()   # undirected, multiple edges allowed
> nx.MultiDiGraph() # directed, multiple edges allowed
> ```
> Loop: `G.add_edge('b','b')`.
