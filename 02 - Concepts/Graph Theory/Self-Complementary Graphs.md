---
tags:
  - bil403
  - graph-theory
  - theorem
  - exam-relevant
---

# Self-Complementary Graphs

Related: [[Complement Graph]] · [[Graph Isomorphism]] · [[Special Graphs]]

> [!important] Theorem — Complement and isomorphism
> Two graphs $G$ and $H$ are **isomorphic if and only if** their complements $\overline{G}$ and $\overline{H}$ are isomorphic:
> $$G \cong H \iff \overline{G} \cong \overline{H}$$

> [!note] Definition — Self-complementary
> A graph $G$ and its complement $\overline{G}$ may or may not be isomorphic. **If they are isomorphic** ($G \cong \overline{G}$), then $G$ is **self-complementary**.

## For which $n$ is it possible?

Self-complementarity requires $G$ and $\overline{G}$ to have **equal edge counts** (by isomorphism). From [[Complement Graph]] we know $m(\overline{G}) = \binom{n}{2} - m(G)$:

> [!important] Edge-count condition
> $$m(G) = m(\overline{G}) = \frac{1}{2}\binom{n}{2} = \frac{n(n-1)}{4}$$

> [!note]- Constraint on $n$ — proof
> $m$ must be an **integer**. For $\dfrac{n(n-1)}{4}$ to be an integer, $n(n-1)$ must be **divisible by 4**. Since $n$ and $n-1$ are consecutive (one of them is odd), the factor of 4 must come from the **even** term. This happens only when:
> $$n \equiv 0 \pmod 4 \quad\text{or}\quad n \equiv 1 \pmod 4$$
> $\blacksquare$

> [!example] Self-complementary examples
> - $P_4$ (path on 4 vertices) — $n = 4 \equiv 0$
> - $C_5$ (cycle on 5 vertices) — $n = 5 \equiv 1$
>
> Counterexample: for the lecture's $G$ and $H$, $G \not\cong H$.

> [!tip] Exam tip
> For "can this graph be self-complementary?", first check $n \bmod 4 \in \{0, 1\}$; if not, the answer is immediately **no**. Then verify the edge count $m = n(n-1)/4$.

---
> [!tip]- Code (NetworkX)
> ```python
> nx.is_isomorphic(G, nx.complement(G))   # self-complementary?
> # pre-check on n:
> n = G.number_of_nodes()
> n % 4 in (0, 1)                          # necessary condition
> ```
