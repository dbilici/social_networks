---
tags:
  - moc
  - bil403
  - code
aliases:
  - Lab Map
---

# 💻 Lab & Code MOC

> [!info]
> Lab sessions and code notes. The course uses **Python** (`networkx` / `igraph`) and **Pajek**; part of the final is on the computer. Parent map: [[BİL403 — Home]].

## Setup
```bash
pip install networkx python-igraph matplotlib numpy scipy
# Pajek: mrvar.fdv.uni-lj.si/pajek/ (Windows)
```

## NetworkX quick reference (concept → code)
| Concept | Code |
|---|---|
| Create graph | `G = nx.Graph()` / `nx.DiGraph()` |
| Add nodes/edges | `G.add_node`, `G.add_edges_from([...])` |
| Degree → [[Adjacency and Degree]] | `G.degree(v)` |
| Neighbors | `list(G.neighbors(v))` |
| Adjacency matrix → [[Adjacency List and Matrix]] | `nx.adjacency_matrix(G)` |
| Shortest path → [[Distance and Diameter]] | `nx.shortest_path_length(G,u,v)` |
| Components → [[Connectedness and Components]] | `nx.connected_components(G)` |
| Isomorphism → [[Graph Isomorphism]] | `nx.is_isomorphic(G,H)` |
| Draw | `nx.draw(G, with_labels=True)` |

## Lab notes
> *(One note per lab: `Lab 1 — ...`)*
- 

> [!tip]
> The foldable **`#code`** sections under each concept note feed into here; collect recurring patterns in this MOC.
