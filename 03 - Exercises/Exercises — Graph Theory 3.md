---
tags:
  - bil403
  - exercise
  - graph-theory
---

# Exercises — Graph Theory 3

Related topics: [[Adjacency List and Matrix]] · [[Incidence Matrix]] · [[Graph Isomorphism]] · [[Self-Complementary Graphs]]

---

### Q1. Matrix symmetry
Why is the adjacency matrix of a simple undirected graph symmetric, and why is its diagonal zero?

> [!success]- Solution
> Being undirected, $v_i \sim v_j \iff v_j \sim v_i$ → $a_{ij} = a_{ji}$ (**symmetric**). With no loops, no vertex is adjacent to itself → $a_{ii} = 0$. (→ [[Adjacency List and Matrix]])

### Q2. Incidence matrix column
If you see 3 ones in a column of an incidence matrix, what does it mean?

> [!success]- Solution
> In a simple graph each column has **2** ones (the edge's two endpoints). Three ones → this is a **hyperedge** (a nonbinary edge touching 3 vertices). One 1 → a **loop**. (→ [[Incidence Matrix]])

### Q3. Memory choice
For a social network with 1,000,000 vertices but an average of 5 neighbors per vertex, adjacency list or matrix?

> [!success]- Solution
> The network is very **sparse** ($m \approx 2.5$M, whereas the matrix has $10^{12}$ cells). → **adjacency list** (far less memory). (→ [[Adjacency List and Matrix]])

### Q4. Isomorphism invariant
Two graphs have the same degree sequence: $(3,3,2,2,2,2)$. Are they necessarily isomorphic?

> [!success]- Solution
> **No, not necessarily.** Equal invariants do **not** guarantee isomorphism. Two structurally different graphs can share a degree sequence. However, if the invariants **differed**, we could conclusively say they are **not** isomorphic. (→ [[Graph Isomorphism]])

### Q5. Not isomorphic — how to show?
$G$ has a 3-cycle (triangle), $H$ does not. Can they be isomorphic?

> [!success]- Solution
> No. The "number of triangles (3-cycles)" is a graph invariant; isomorphism preserves it. If one is 0 and the other $\ge 1$ → **not isomorphic**. (→ [[Graph Isomorphism]])

### Q6. Self-complementary — pre-screen
Can a graph on $n = 6$ or $n = 7$ vertices be self-complementary?

> [!success]- Solution
> The necessary condition is $n \equiv 0$ or $1 \pmod 4$. $6 \bmod 4 = 2$ → **cannot**. $7 \bmod 4 = 3$ → **cannot**. (The smallest nontrivial self-complementary examples are $n=4$: $P_4$ and $n=5$: $C_5$.) (→ [[Self-Complementary Graphs]])

### Q7. Self-complementary edge count
How many edges must a self-complementary graph on $n = 8$ vertices have?

> [!success]- Solution
> $m = \dfrac{n(n-1)}{4} = \dfrac{8 \cdot 7}{4} = 14$ edges. (Since $8 \equiv 0 \pmod 4$ the result is an integer, consistent.) (→ [[Self-Complementary Graphs]])
