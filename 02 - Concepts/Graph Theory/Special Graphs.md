---
tags:
  - bil403
  - graph-theory
  - special-graph
  - exam-relevant
---

# Special Graphs

Related: [[Bipartite Graphs]] · [[Adjacency and Degree]] · [[Graph Theory MOC]]

> [!info] Summary table
> | Graph | Order $n$ | Size $m$ | $\delta$ | $\Delta$ |
> |---|---|---|---|---|
> | Complete $K_n$ | $n$ | $\binom{n}{2}$ | $n-1$ | $n-1$ |
> | Cycle $C_n$ ($n\ge3$) | $n$ | $n$ | $2$ | $2$ |
> | Wheel $W_n$ | $n+1$ | $2n$ | $3$ | $n$ |
> | Hypercube $Q_n$ | $2^n$ | $n\,2^{n-1}$ | $n$ | $n$ |
> | Path $P_n$ ($n\ge1$) | $n$ | $n-1$ | $1$ | $2$ |

## Trivial / empty graphs
- **Trivial graph:** a graph of order 1.
- **Nontrivial:** 2 or more vertices.
- **Empty graph:** a graph of size 0 ($m=0$).
- **Nonempty:** 1 or more edges.

## Complete graph $K_n$

> [!note] Definition
> The **complete graph** $K_n$ on $n$ vertices is the simple graph containing **exactly one edge between each pair of distinct vertices**. If one edge is missing, the graph is **noncomplete**.

$$n = n,\qquad m = \binom{n}{2},\qquad \delta = \Delta = n-1$$
For any **simple** graph: $0 \le m \le \binom{n}{2}$.

## Cycle $C_n$

> [!note] Definition
> $C_n$ ($n \ge 3$) consists of vertices $v_1, v_2, \dots, v_n$ and edges $(v_1,v_2), (v_2,v_3), \dots, (v_{n-1},v_n), (v_n, v_1)$.

$$n=n,\quad m=n,\quad \delta=\Delta=2$$

## Wheel $W_n$

> [!note] Definition
> $W_n$ is obtained by adding **one extra center vertex** to a cycle $C_n$ and connecting this new vertex to **all** $n$ vertices of the cycle ($n \ge 3$).

$$n = n+1,\quad m = 2n,\quad \delta = 3,\quad \Delta = n$$

## Hypercube $Q_n$

> [!note] Definition
> The $n$-dimensional **hypercube** $Q_n$ has vertices representing the $2^n$ **bit strings** of length $n$. Two vertices are adjacent **iff** their bit strings differ in **exactly one** bit position.

$$n = 2^n,\qquad m = n\,2^{\,n-1}$$
> [!example] Example
> $Q_1$: `0—1` · $Q_2$: square (`00,01,11,10`) · $Q_3$: cube (`000…111`).

## Path $P_n$

> [!note] Definition
> $P_n$ ($n \ge 1$) is the graph of order $n$ and size $n-1$ in which vertices connect to the previous and next vertex, **except the first and last** vertex.

$$n=n,\quad m=n-1,\quad \delta=1,\quad \Delta=2$$

> [!tip] Connections
> $P_1 = K_1,\qquad P_2 = K_2,\qquad C_3 = K_3$

## Regular graph

> [!note] Definition
> If **all vertices have the same degree**, the graph is **regular**. If each vertex has degree $r$, the graph is **$r$-regular**.

- $K_n$ graphs are **$(n-1)$-regular**.
- A **3-regular** graph is called a **cubic** graph; $K_4$ is cubic.
- **Petersen graphs** are well-known cubic graphs.

---
> [!tip]- Code (NetworkX)
> ```python
> nx.complete_graph(5)        # K5
> nx.cycle_graph(6)           # C6
> nx.wheel_graph(6)           # wheel (center + 6-cycle)
> nx.hypercube_graph(3)       # Q3
> nx.path_graph(4)            # P4
> nx.petersen_graph()         # Petersen (cubic)
> ```
