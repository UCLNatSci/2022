# NSCI0011: Motif Analysis of Neural Circuits

## Background

A motif is a subgraph with a particular topological structure; for example, there are 13 possible motifs consisting of 3 nodes (see {numref}`motifs`). The aim of motif analysis is to determine which specific motifs are present in a network with a frequency that is significantly different to chance. This can be achieved by repeated sampling from a network in order to construct a *motif frequency spectrum* (see {numref}`histogram`) and then comparing this to a suitable 'null model'. Motif analysis has revealed functionally important features in the nervous systems of the macaque, cat and *C. elegans* {cite:p}`sporns2004motifs`.

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

A 'connectome' is a complete description of the structural connectivity of an organism's nervous system, typically as a graph of nodes (neurons) and directed edges (synaptic connections between neurons). To date, the only whole-animal connectome to be completely determined is the nervous system of hermaphrodite *C. elegans*, comprising a graph of 460 nodes and 4887 directed edges. In a recent study the connectome of a large part of the *Drosophila Melanogaster* nervous system was published, consisting of around 25,000 neurons and 20 million synaptic connections (see {numref}`drosophila`) {cite:p}`xu2020connectome`.

```{figure} drosophila.png
---
height: 250px
name: drosophila
---
The connectome of the highlighted portion of the drosophila central brain consists of around 25,000 neurons and 20 million synaptic connections. *Reprinted from {cite:p}`xu2020connectome`*
```

## Project Brief

You should perform a motif analysis of the connectome of *Drosophila Melanogaster*. By reviewing relevant scientific literature, investigate how motif analysis can be performed in nervous systems, then apply appropriate techniques to the *Drosophila Melanogaster* connectome detailed in {cite:p}`xu2020connectome`. Using diagrams and equations, clearly describe how the motif analysis is performed.

## Suggested Breakdown

You will need to perform the following steps to complete the project, but steps 1 and 2 could be completed in either order.

**1\. Write a program which generates the motif spectrum of an arbitrary directed graph.** For a given graph order $n$, you will first need to determine all possible motifs. I would suggest sticking with $n=3$ since it quickly becomes *very* complicated for larger $n$. Then you can use [NetworkX](https://networkx.org/) to determine if a subgraph is isomorphic to one of the motifs. See the notes for an explanation of graph isomorphisms. Finally, you will need to sample a large number of subgraphs so that you can generate the frequency spectrum. Check that your code works by generating the frequency spectrum of a small random graph or a known standard graph.

**2\. Load the *Drosophila* connectome data into Python.** The data is in the form of an edge list in `.csv` format. The easiest way to load the data is using the [Pandas](https://pandas.pydata.org/docs/user_guide/index.html) Python library to read it into a dataframe, which can then be converted to a NetworkX digraph. The data set is *very* large so you should use Pandas filtering to select a specific brain region to investigate (for example AL\(R\)). The data is in the form of a weighted graph so you will have to consider how to best turn this into an unweighted directed graph. You might end up with several disconnected graph - see the notes for how to find connected graph components.


**3\. Generate and investigate the frequency spectrum for the *Drosophila* brain region.** Which motifs are present at a frequency different than would be expected due to chance? The easiest way to do this is to compare the spectrum to an equivalent random graph. It is up to you to determine what an 'equivalent' random graph is - the simplest is a graph with the same number of nodes and edges but there are more sophisticated ways to generate equivalent 'null models'.

## Notes

1. You should make good use of the available supervision. There are some tricky corners in this project, and there is a risk of getting stuck down some blind alleys if you are unlucky. I am happy to provide assistance, but that means approaching me for help.

2. The suggested text book {cite:p}`fornito2016fundamentals` has some good background and links to further useful information. I recommend reading Chapter 8.1 at least.

3. Familiarise yourself with the notes, which contain fundamentals of graphs, components, subgraphs and so on.

## References

```{bibliography}
```
