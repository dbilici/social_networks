---
tags:
  - bil403
  - exercise
  - graph-theory
---

# Exercises — Graph Theory 1

Related topics: [[Graph — Basic Definitions]] · [[Adjacency and Degree]] · [[Handshaking Theorem]] · [[Degree Sequences and Havel–Hakimi]] · [[Special Graphs]] · [[Bipartite Graphs]]

> [!tip] How to use
> Try to solve first, then click the "Solution" line to expand it. Foldable callouts (`> [!...]-`) open on click in Obsidian.

---

### Q1. Handshaking
At a party there are 9 people. Is it possible for each to shake hands with **exactly 3** others?

> [!success]- Solution
> No. In the handshake graph, if every vertex had degree 3 the degree sum would be $9 \times 3 = 27$, **odd**. But [[Handshaking Theorem|$2m = \sum \deg(v)$]] requires the sum to be even. Contradiction → impossible. (General rule: the number of odd-degree vertices must be even; here there would be 9 odd-degree vertices.)

### Q2. Order and size
How many edges does the complete graph $K_7$ have? What are $\delta$ and $\Delta$?

> [!success]- Solution
> $m = \binom{7}{2} = 21$. Each vertex connects to the other 6 → $\delta = \Delta = 6 = n-1$. (→ [[Special Graphs]])

### Q3. Graphical sequences
Which of these are graphical? **(a)** $5,4,3,2,1$  **(b)** $4,4,4,4$  **(c)** $5,3,3,3,3,3$

> [!success]- Solution
> **(a)** $n=5$ but $\max = 5 > n-1 = 4$ → **not graphical** (a vertex cannot connect to 5 distinct others; only 4 exist).
> **(b)** 4-regular, $n=4$, $\max=4 > 3$ → **not graphical** (in a simple graph). *(It would be possible if loops/multiples were allowed.)*
> **(c)** Sum $= 20$ (even ✅). Havel–Hakimi: delete 5, subtract 1 from the next 5 → $2,2,2,2,2$ → ... → all reach 0 → **graphical**.

### Q4. Neighborhood
In a graph, if $\deg(v) = 0$, what are $N(v)$ and $N[v]$?

> [!success]- Solution
> $v$ is **isolated**. $N(v) = \varnothing$ (empty set), $N[v] = \{v\}$. (→ [[Adjacency and Degree]])

### Q5. Hypercube
How many vertices and edges does $Q_4$ have? Of what degree is it regular?

> [!success]- Solution
> Vertices: $2^4 = 16$. Edges: $n \cdot 2^{n-1} = 4 \cdot 2^3 = 32$. Each vertex has one neighbor per bit flip → **4-regular**. (→ [[Special Graphs]])

### Q6. Bipartite check
Are $K_{3,3}$ and $C_5$ bipartite?

> [!success]- Solution
> $K_{3,3}$ is bipartite by definition (two parts of 3). $C_5$ is an **odd cycle**, so it cannot be 2-colored → **not bipartite**. (→ [[Bipartite Graphs]])

### Q7. Wheel
What are the order, size, $\delta$, and $\Delta$ of $W_5$?

> [!success]- Solution
> $W_5 = C_5$ + 1 center. Order $= 5+1 = 6$, size $= 2 \cdot 5 = 10$. The center connects to all 5 → $\Delta = 5$; cycle vertices have 2 neighbors + center = 3 → $\delta = 3$. (→ [[Special Graphs]])

### Q8. (Conceptual) Regular ⇒ ?
Is every complete graph regular? Is every regular graph complete?

> [!success]- Solution
> $K_n$ is always $(n-1)$-regular → **yes, every complete graph is regular**. The converse is false: $C_4$ is 2-regular but not complete → **not every regular graph is complete**.
