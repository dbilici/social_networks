---
tags:
  - bil403
  - graph-theory
  - definition
  - code
---

# Adjacency List and Matrix

Related: [[Incidence Matrix]] · [[Counting Paths]] · [[Graph Isomorphism]]

The two basic ways to store a graph on a computer.

## Adjacency list

> [!note] Definition
> Stores, for each vertex, the **list of its neighbors**.

> [!example] Example
> | vertex | adjacent vertices |
> |---|---|
> | a | b |
> | b | a, c, e |
> | c | b, d, e |
> | d | c, e |
> | e | b, c, d |

## Adjacency matrix

> [!note] Definition
> For $|V| = n$, an $n \times n$ matrix $A = [a_{ij}]$:
> $$a_{ij} = \begin{cases} 1 & v_i v_j \in E \\ 0 & \text{otherwise} \end{cases}$$
> For a simple graph this is a **zero-one matrix**.

> [!important] Properties
> - The adjacency matrix of a simple **undirected** graph is **symmetric**: $a_{ij} = a_{ji}$.
> - With no loops, the diagonal is zero: $a_{ii} = 0$.
> - With **multiple edges or loops**, the matrix is no longer zero-one (entry = number of edges; loops are usually counted on the diagonal).

> [!warning] Ordering matters
> The ordering of vertices is **arbitrary but must be consistent**. For $n$ vertices there are $n!$ orderings (hence $n!$ different-looking matrices for the same graph). → this is the basis of [[Graph Isomorphism]].

> [!example] Example
> With order $a, b, c, d$:
> $$A = \begin{pmatrix} 0&1&0&1 \\ 1&0&1&0 \\ 0&1&0&0 \\ 1&0&0&0 \end{pmatrix}$$

## Trade-offs: list or matrix?

> [!info] Which when?
> | Situation | Preference | Why |
> |---|---|---|
> | **Sparse** graph | adjacency **list** | less memory |
> | **Dense** graph | adjacency **matrix** | — |
> | "Are u, v adjacent?" query | adjacency **matrix** | $O(1)$ vs list $O(\deg)$ |

$$\text{matrix: } \Theta(1) \quad\text{vs}\quad \text{list: } \Theta(\deg)$$

---
> [!tip]- Code (NetworkX)
> ```python
> # Adjacency list
> {v: list(G.neighbors(v)) for v in G}
> nx.to_dict_of_lists(G)
>
> # Adjacency matrix
> A = nx.adjacency_matrix(G)       # sparse (scipy)
> A.todense()                      # full matrix
> nx.to_numpy_array(G)             # numpy array
> ```
