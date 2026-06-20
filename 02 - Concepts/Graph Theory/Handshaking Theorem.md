---
tags:
  - bil403
  - graph-theory
  - theorem
  - exam-relevant
---

# Handshaking Theorem

Related: [[Adjacency and Degree]] · [[Degree Sequences and Havel–Hakimi]] · [[Graph Theory MOC]]

> [!important] Theorem — Handshaking Theorem
> For an undirected graph $G(V, E)$ with $m$ edges (size):
> $$2m = \sum_{v \in V} \deg(v)$$
> This is also known as the **first theorem of graph theory**.

**Why?** When we sum the degrees, **each edge is counted twice** (once at each of its two endpoints). Therefore the total equals twice the number of edges.

> [!tip] Intuition
> "Handshaking": the sum of the number of handshakes made by everyone in a room is twice the number of handshakes that actually occurred — because each handshake involves two people.

## Corollary: odd-degree vertices

> [!important] Corollary
> Every graph has an **even number of odd-degree (odd) vertices**.

**Proof idea.** Split the vertices into the odd-degree set $U$ and even-degree set $W$:
$$\underbrace{2m}_{\text{even}} = \sum_{v \in V} \deg(v) = \underbrace{\sum_{v \in U} \deg(v)}_{?} + \underbrace{\sum_{v \in W} \deg(v)}_{\text{even (sum of evens)}}$$
The left side is even and the second term on the right is even, so the **first term must also be even**. For a sum of odd numbers to be even, the number of terms (i.e. $|U|$) must be even. $\blacksquare$

> [!note] Reminder
> A vertex with odd degree is an **odd vertex**; one with even degree is an **even vertex**.

---
> [!tip]- Code (NetworkX) — verify the theorem
> ```python
> 2 * G.number_of_edges() == sum(d for _, d in G.degree())   # True
> # the number of odd-degree vertices is always even:
> sum(1 for _, d in G.degree() if d % 2 == 1) % 2 == 0        # True
> ```
