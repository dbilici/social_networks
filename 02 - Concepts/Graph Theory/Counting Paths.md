---
tags:
  - bil403
  - graph-theory
  - theorem
  - exam-relevant
---

# Counting Paths

Related: [[Adjacency List and Matrix]] · [[Paths, Circuits and Walks]] · [[Distance and Diameter]]

> [!important] Theorem — Powers of the adjacency matrix
> Let $G$ be a graph with adjacency matrix $A$. The **number of distinct paths (walks) of length $r$** from $v_i$ to $v_j$ is the $(i, j)$ entry of $A^r$ (for positive integer $r$).
> **Valid for all graphs** (directed/undirected, with multiple edges and loops).

> [!note]- Proof (by induction)
> **Base case ($r = 1$):** $A^1 = A$. Entry $(i,j)$ is the number of single-edge paths $v_i \to v_j$ — by definition of the adjacency matrix.
>
> **Inductive step:** Assume entry $(i,j)$ of $A^r$ gives the number of length-$r$ paths. Since $A^{r+1} = A^r \cdot A$:
> $$\big(A^{r+1}\big)_{ij} = \sum_{k} \big(A^r\big)_{ik}\, A_{kj}$$
> Every length-$(r+1)$ path from $v_i$ to $v_j$ first goes to an **intermediate vertex $v_k$** in $r$ steps ($=(A^r)_{ik}$ paths), then $v_k \to v_j$ in one edge ($=A_{kj}$). Summing the products over all $k$ gives exactly this count. $\blacksquare$

> [!example] Example (from lecture)
> On a graph with vertices $a,b,c,d$,
> $$A = \begin{pmatrix} 0&1&1&0 \\ 1&0&0&1 \\ 1&0&0&1 \\ 0&1&1&0 \end{pmatrix}$$
> Entry $(a,d)$ of $A^4$ is **8** → there are **8 paths** of length 4 from $a$ to $d$:
> ```
> a,b,a,b,d   a,b,d,c,d
> a,b,a,c,d   a,c,a,b,d
> a,b,d,b,d   a,c,a,c,d
> a,c,d,b,d   a,c,d,c,d
> ```

> [!warning] Caution
> These are **walks** (repeated vertices/edges allowed), not "simple paths" in the classical sense. $A^r$ counts repetitions too.

> [!tip] Where does this connect?
> - Diagonal entries ($A^r_{ii}$) → count **closed walks** (circuits) of length $r$.
> - The **shortest distance** between two vertices is the smallest power at which entry $(i,j)$ first becomes nonzero across $A^1, A^2, \dots$ → [[Distance and Diameter]]

---
> [!tip]- Code (NetworkX + NumPy)
> ```python
> import numpy as np
> A = nx.adjacency_matrix(G).todense()
> A4 = np.linalg.matrix_power(A, 4)
> A4[i, j]   # number of length-4 walks from i to j
> ```
