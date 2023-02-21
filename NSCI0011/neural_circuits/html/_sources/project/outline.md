# Outline

The aim of this project is to perform a 'motif frequency analysis' of the *Drosophila Melanogaster* connectome. Motif analysis is described in Chapter 8.1 of {cite:p}`fornito2016fundamentals` and you should read this chapter carefully for essential background. Some of the cited articles may also prove useful. 

A motif is a small graph with a specific structure, and motif analysis involves counting the frequency that a particular set of motifs appear as a subgraph of a graph of interest (in our case, a graph representing a brain circuit). You should perform a motif analysis for the motifs of order 3 (as shown in the project brief).

Motif analysis requires us to determine whether two graphs (a motif and a subgraph of the connectome) are 'the same'. In graph theory, two graphs are the same if they are *isomorphic*. Graph isomorphisms are explained in {numref}`graph_isomorphisms_section` of these notes. Checking if two graphs are isomporphic is a [hard](https://en.wikipedia.org/wiki/Graph_isomorphism_problem) computational problem, but fortunately you don't need to write this algorithm yourself since you can make use of a Python library [NetworkX](https://networkx.org/) which contains functions for checking graph isomorphism, as well as other useful functions.

You'll need to determine how to sample subgraphs from a connectome graph. If the connectome graph is small enough, it's possible to sample *every* triplet of nodes but this may be infeasible for larger connectome graphs. In this case a strategy of random sampling might prove more effective.

The graph of the *Drosophila Melanogaster* connectome can be downloaded from https://neuprint.janelia.org/ as a text file. It can be tricky to access it from the web site, so it will also be made available here. You will have to determine how best to interpret the data as a directed graph and how to load it into Python using NetworkX.

Lastly, in order to determine whether any of the motifs appear at a higher or lower frequency than expected, you should build a *null model* which acts as a 'reference' or 'control'. The easiest way to do this is by generating a suitable [random graph](https://en.wikipedia.org/wiki/Random_graph).

## NewtorkX

You will also need to understand how to use the [NetworkX](https://networkx.org/) Python package. Work through the [tutorial](https://networkx.org/documentation/stable/tutorial.html) first.

Check that you understand how to use the NewtorkX function `is_isomorphic`. The following exercise would be good a good (and useful) exercise to get you started.

```{exercise}
Write Python code which uses `NetworkX` to calculate and graph the [node degree histogram](https://mathinsight.org/degree_distribution) of an arbitrary graph.
```

## Motif Frequency Analysis

The core programming task is to develop code which calculates the triplet motif frequency spectrum of a given graph. Think about how to split this problem up into discrete funcions. For example,
1. A function which determines whether a subgraph (identified by a list of nodes) of a given graph (identified by an adjacency list or NetworkX object) is isomorphic to a second given graph. Test your function against a known graph (eg the *C Elegans* Egg-laying circuit). You can use NetworkX to test for graph isomorphism.
2. A function which determines whether a given subgraph of given graph is isomorphic to one of the triplet motifs.

Don't get too stuck with this part! If you're not sure how to proceed then please come to me for guidance.

## Drosophila Connectome Data

*Further Information will appear here*.

## Schedule

You should expect to spend no more than 1 or 2 weeks developing code to calculate the motif frequency spectrum. Understanding how to convert the *drosophila* data into a graph might take another week, and the rest of the time should be spent generating results and writing your report.
