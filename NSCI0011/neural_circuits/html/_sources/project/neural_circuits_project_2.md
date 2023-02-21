# Project Brief

A motif is a subgraph with a particular topological structure; for example, there are 13 possible motifs consisting of 3 nodes (see {numref}`motifs`). The aim of motif analysis is to construct a *motif frequency spectrum* (see {numref}`histogram`) which describes the relative abundance of each motif within a graph.
```{figure} motifs.png
---
height: 220px
name: motifs
---
 There are 13 distinct three-node motifs in directed networks. *Reprinted from {cite:p}`fornito2016fundamentals`*
```

```{figure} histogram.png
---
height: 120px
name: histogram
---
The frequency spectrum of the 13 3-node motifs in four different brain networks. *Reprinted from {cite:p}`fornito2016fundamentals`*
```

## Aims

In a recent study the connectome of a large part of the *Drosophila Melanogaster* nervous system was published, consisting of around 25,000 neurons and 20 million synaptic connections (see {numref}`drosophila`) {cite:p}`xu2020connectome`. The aim of this project is to perform motif analysis by repeatedly sampling from the graph of the drosophila connectome. You will:

 - Determine the order-3 isomorphic directed graphs
 - Import the *drosophila* connectome data and determine how to represent it as a directed graph
 - Develop code to calculate the motif spectrum of the graph of the *drosophila* connectome
 - Compare the resulting graph to a suitable null (reference) model

```{figure} drosophila.png
---
height: 250px
name: drosophila
---
The connectome of the highlighted portion of the drosophila central brain consists of around 25,000 neurons and 20 million synaptic connections. *Reprinted from {cite:p}`xu2020connectome`*
```

## Background

2. The suggested text book {cite:p}`fornito2016fundamentals` has some good background and links to further useful information. Chapter 8.1 contains the most relevant material.

3. You will need to understand just a little more graph theory, in particular the idea of *graph isomorphisms*, for which notes will be provided.

4. We will be using a Python library [NetworkX](https://networkx.org/) to automate some of the graph analysis.

## References

```{bibliography}
```
