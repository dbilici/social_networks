---
tags:
  - bil403
  - graph-theory
  - definition
  - exam-relevant
---

# Graph Isomorphism

Related: [[Adjacency List and Matrix]] · [[Self-Complementary Graphs]] · [[Adjacency and Degree]]

> [!question] Core question
> Can we draw two graphs **the same way**? If we ignore the identities of the vertices, do the graphs have the **same structure**?

> [!note] Definition — Isomorphism
> Simple graphs $G_1 = (V_1, E_1)$ and $G_2 = (V_2, E_2)$ are **isomorphic** ($G_1 \cong G_2$) if there is a **one-to-one and onto (bijective)** function $f$ from $V_1$ to $V_2$ such that:
> $$a, b \text{ adjacent in } G_1 \iff f(a), f(b) \text{ adjacent in } G_2$$
> Such an $f$ is an **isomorphism**.

> [!example] Example (from lecture)
> A square $G$ and a "crossed" drawing $H$ are isomorphic ($G \cong H$):
> $$f(u_1)=v_1,\quad f(u_2)=v_4,\quad f(u_3)=v_3,\quad f(u_4)=v_2$$

## Graph invariants

Isomorphic graphs **must be equal** in:
- Number of vertices $|V_1| = |V_2|$
- Number of edges $|E_1| = |E_2|$
- **Degree sequence** is the same → [[Degree Sequences and Havel–Hakimi]]
- Degree distribution is the same

> [!important] Practical strategy
> It is usually easier to show that two graphs are **not** isomorphic:
> - If **any** invariant differs → the graphs are **not isomorphic**. ✅ conclusive
> - If **all** invariants are equal → the graphs are **not necessarily** isomorphic. ⚠️ inconclusive

> [!example] Non-isomorphic examples
> The lecture's $G \not\cong H$ examples: even when invariants look the same, the structure differs (e.g. the count of cycles of a given length does not match).

## Matrix view

> [!note]
> If two graphs are isomorphic, their **adjacency matrices become identical when relabelled** under the isomorphism.
>
> E.g. writing $A_G$ in the order $u_1 u_2 u_3 u_4 u_5 u_6$ and $A_H$ in the order $v_6 v_3 v_4 v_5 v_1 v_2$ makes the two matrices **exactly equal**. → [[Adjacency List and Matrix]]

> [!tip] Practical shortcut
> In practice we may treat "isomorphism $=$ equality". The number of non-isomorphic graphs for small $m$: $m=1 \to 1$, $m=2 \to 2$, $m=3 \to 4$, $m=4 \to 11$.

---
> [!tip]- Code (NetworkX)
> ```python
> nx.is_isomorphic(G, H)                 # True / False
> from networkx.algorithms.isomorphism import GraphMatcher
> gm = GraphMatcher(G, H)
> gm.is_isomorphic()
> next(gm.isomorphisms_iter())           # gives the mapping f
> ```
