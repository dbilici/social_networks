---
tags:
  - bil403
  - graph-theory
  - theorem
  - exam-relevant
---

# Degree Sequences and Havel–Hakimi

Related: [[Handshaking Theorem]] · [[Adjacency and Degree]] · [[Special Graphs]]

> [!note] Definition — Degree sequence
> The **degree sequence** of a graph is a sequence of numbers corresponding to its degrees, typically written in **nonincreasing** order.

> [!example] Example
> Degree sequence: $4, 3, 2, 2, 1$

**Necessary** conditions for a degree sequence:
- Number of elements $= n$ (number of vertices)
- $\displaystyle\sum_i d_i = 2m$  (→ [[Handshaking Theorem]])
- $\max(d_i) \le n - 1$

## Graphical sequences

> [!note] Definition — Graphical sequence
> An integer sequence is **graphical** if it **is the degree sequence of some graph**.

> [!example] Examples
> - $4, 3, 2, 2, 1$ → **graphical** ✅
> - $3, 3, 3, 1$ → **not graphical** ❌
> - $3, 2, 2, 2, 1$ → **graphical** ✅

## Havel–Hakimi Theorem

> [!important] Theorem — Havel–Hakimi
> Let $S$ be a sequence of nonnegative integers sorted as $\Delta = d_1 \ge d_2 \ge \dots \ge d_n$ with $\Delta \ge 1$. Then $S$ is **graphical if and only if** the following sequence is graphical:
> $$S_1:\quad d_2 - 1,\ d_3 - 1,\ \dots,\ d_{\Delta+1} - 1,\ \ d_{\Delta+2},\ \dots,\ d_n$$

**Steps (algorithm):**
1. **Delete** the largest value $\Delta$ from the sequence.
2. **Subtract 1** from the next $\Delta$ elements.
3. **Re-sort** (descending).
4. Repeat. If all become 0 → **graphical**. If a negative element appears → **not graphical**.

> [!example] Example — $5, 3, 3, 3, 3, 2, 2, 2, 1, 1, 1$
> ```
> 5,3,3,3,3,2,2,2,1,1,1
> Delete 5, subtract 1 from the next 5:
> → 2,2,2,2,1, 2,2,1,1,1
> Re-sort:
> → 2,2,2,2,2,2,1,1,1,1
> → (continue) → 2,2,2,1,1,1,1,1,1
> → 1,1,1,1,1,1,1,1   (★ we can stop here)
> → 1,1,1,1,1,1,0
> → 1,1,1,1,0,0
> → 1,1,0,0,0
> → 0,0,0,0   ✅ graphical
> ```
> > [!tip] Early stopping
> > We can stop earlier if we can already see a corresponding graph. The sequence marked ★, $1,1,1,1,1,1,1,1$, is **graphical** — it is four copies of $K_2$: $4K_2$ (four separate edges). → [[Special Graphs]]

---
> [!tip]- Code (NetworkX)
> ```python
> nx.is_graphical([4,3,2,2,1])        # True
> nx.is_graphical([3,3,3,1])          # False
> # Build a graph from a sequence (Havel–Hakimi):
> G = nx.havel_hakimi_graph([4,3,2,2,1])
> ```
