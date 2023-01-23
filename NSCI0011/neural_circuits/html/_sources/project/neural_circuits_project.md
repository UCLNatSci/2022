# NSCI0011 Coursework - Neural Circuits

## Background

A motif is a subgraph with a particular topological structure; for example, there are 13 possible motifs consisting of 3 nodes (see {numref}`motifs`). The aim of motif analysis is to determine which specific motifs are present in a network with a frequency that is significantly different to chance. This can be achieved by repeated sampling from a network in order to construct a *motif frequency spectrum* (see {numref}`histogram`). Motif analysis has revealed functionally important features in the nervous systems of the macaque, cat and *C. elegans* {cite:p}`sporns2004motifs`.

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

## References

```{bibliography}
```
