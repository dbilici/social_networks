---
tags:
  - bil403
  - graph-theory
  - definition
  - theorem
---

# Complement Graph

Related: [[Graph Operations]] · [[Special Graphs]] · [[Self-Complementary Graphs]]

> [!note] Definition — Complement
> The **complement** of a graph $G$ is the graph $\overline{G}$ such that: if vertices $u$ and $v$ are **connected** in $G$, they are **not connected** in $\overline{G}$ (and vice versa).
>
> That is, $\overline{G}$ contains, over the same vertex set, exactly all simple edges **not** present in $G$.

## Sizes

> [!important] Theorem — Size of the complement
> If $n_G = n$ and $m_G = m$, then:
> $$n_{\overline{G}} = n, \qquad m_{\overline{G}} = \binom{n}{2} - m$$

> [!note]- Proof
> In a simple graph on $n$ vertices the maximum possible number of edges is $\binom{n}{2}$ (one per pair of vertices — see [[Special Graphs|$K_n$]]). $G$ uses $m$ of these; $\overline{G}$ uses exactly the **rest**. Since the vertex set is unchanged, $n_{\overline{G}} = n$. $\blacksquare$

## Key identities

- The union of $G$ with its complement gives the complete graph:
$$G \cup \overline{G} = K_n$$
- $\overline{K_n}$ is the **empty graph** ($m = 0$); i.e. the complement of $K_n$ has no edges.

> [!example] Example
> ```mermaid
> graph LR
>   subgraph G
>     a1((a)) --- b1((b)); c1((c)) --- d1((d)); b1 --- d1
>   end
>   subgraph Gbar["Ḡ"]
>     a2((a)) --- c2((c)); a2 --- d2((d)); b2((b)) --- c2
>   end
> ```
> Edges present in $G$ are absent in $\overline{G}$; edges absent in $G$ are present in $\overline{G}$.

> [!tip] Why useful?
> Used in isomorphism checking and in studying **self-complementary** graphs. → [[Self-Complementary Graphs]]

---
> [!tip]- Code (NetworkX)
> ```python
> Gc = nx.complement(G)
> Gc.number_of_edges() == nx.complete_graph(G.number_of_nodes()).number_of_edges() - G.number_of_edges()  # True
> ```
