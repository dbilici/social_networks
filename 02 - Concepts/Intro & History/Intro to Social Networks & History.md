---
tags:
  - bil403
  - intro
  - history
---

# Intro to Social Networks & History

Related: [[BİL403 — Home]] · [[Graph — Basic Definitions]]

## What is a network?
> [!note] Definition
> A **network** is nodes connected by lines — **no different from a graph**. A graph $G = (V, E)$ consists of a nonempty vertex set $V$ and a link set $E$; $E$ is a set of relations over $V$. → [[Graph — Basic Definitions]]

The same abstract structure (nodes + links) models very different systems:

| Network | Nodes | Links |
|---|---|---|
| Social contact network | individuals | contacts |
| Physician network | doctors | patient sharing |
| Infection network | individuals | who infected whom |
| Friendship network | individuals | friendship |
| Neural network | neurons | synapses |
| Organizational network | organizations | partnership, hierarchy |

## History — milestones
- **Euler (1707–1783)** — the **Königsberg bridges** problem: the birth of graph theory. Land masses are modeled as nodes, bridges as edges.
- **Jacob Moreno (1930s)** — the father of **sociometry**. He called his diagrams **sociograms**; they gave sociology a new perspective (e.g. student friendship networks, "dinner companions").
- **J. Scott (2000)** — the lineage of social network analysis: Gestalt theory + structural-functional anthropology + group dynamics → merging with **graph theory, math/CS and physics** into modern SNA.

## How is social-network data collected?
- **Interviews & surveys:** "Who is your best friend?", "Who do you work with?" (free or limited; in-/out-degree). Time-consuming and expensive (e.g. the *Add Health* study ~90,000 people). **Ego-centric** networks.
- **Direct observation** (ideal for small groups, hard).
- **Archival records.**

> [!info] Attribute data vs relational data
> - **Attribute data** → variable analysis (age, BMI, income…)
> - **Relational data** → **network analysis** (who is connected to whom)

## Network types (two axes)
Two independent distinctions combine into 4 types:
- **Undirected ↔ Directed** (forget directions / reciprocals only)
- **Binary ↔ Weighted** (dichotomize weighted → binary)

## Real-world example networks
Technological (internet, power grid, gas pipelines, transportation) · Social (friendship, romantic/sexual networks, Facebook) · Information (WWW, citation networks, co-authorship) · Biological (food webs, human brain/connectome, metabolic networks, disease-gene network).

> [!example] Interesting examples
> - **Erdős number** — co-authorship distance to Paul Erdős (e.g. Einstein 2, Hawking 4).
> - **Signed networks** — links carry +/− values; Heider's **structural balance** theory (e.g. pre-WWI alliances: "balanced / not balanced").
> - **Patient-sharing network (PANDA)** — work by Güçlü et al.

## "Visualizations are nice, but what do they mean?"
Visualization is a **preliminary analysis** but falls short for large networks. The measures used for real analysis (the rest of the course):
- Degree distributions → [[Adjacency and Degree]]
- Hubs / authorities (collectors/distributors)
- Small-world properties
- **Centrality measures** ⏭️ (next topic)
- Community analysis · similarity · homophily · transitivity & reciprocity

## Key distribution distinction
> [!tip] Remember for the exam
> - **Poisson distribution → Exponential network**
> - **Power-law distribution → Scale-free network**
