# Further Graphs

## Isomorphic Graphs

We say that two graphs are *isomorphic* if they have the same network structure. Graphs $G_1$ and $G_2$ are isomorphic if there exists a matching between their nodes such that two nodes are connected by an edge in $G_1$ if and only if their corresponding nodes are connected by an edge in $G_2$.

```{admonition} Definition
An **isomorphsim** between two graphs $(V_1, E_1)$ and $(V_2, E_2)$ is a bijection (one-to-one correspondence)

$$f\colon V_1\to V_2$$

such that $(v_1, v_2)$ is in $E_1$ if and only if $(f(v_1), f(v_2))$ is in $E_2$.

If an isomorphism exists between two graphs, we say that the graphs are **isomorphic**.
```

### Example

Find an isomorphism between the following two graphs.

![](matlab/isomorphic_graphs.png)

**Solution**

These two graphs are isomorphic under the isomorphism $f\colon \{1, 2, 3\}\to \{A, B, C\}$ where $f(1) = C, f(2) = B $ and $f(3) = A$.

### Question 1

1\. Find an isomorphism between the following two directed graphs:

![](matlab/isomorphic_graphs_2.png)

2\. Find a subgraph of the egg-laying circuit isomorphic to the directed graph below.

![](matlab/question1.png)

3\. Use NetworkX functions `subgraph` and `is_isomorphic` to confirm your answer to 2.

### Example

How many simple directed graphs are there with 3 nodes and two edges?

**Solution**

There are 4. Any other simple directed digraph with 3 nodes and 2 edges is isomorphic to one of these.

![](matlab/triplet_motifs_2.png)

### Question 2

Draw all simple directed graphs with 3 nodes and 3 edges.

### Isomorphism from Adjacency Matrix

Given two graphs $G_1$ and $G_2$, we can check whether they are isomorphic by calculating the adjacency matrix of every permutation of the nodes of $G_1$. If one of them is equal to the adjacency matrix of $G_2$, then the two graphs are isomorphic.

There are $n!$ permutations of $n$ nodes, so even for relatively small graphs, checking for isomorphism can take a long time. There are $2.4\times 10^{24}$ possible permutations of a graph with 20 nodes.

### Question 3

Write down all $3! = 6$ adjacency matrices of the following digraph.

![](matlab/triplet_adj.png)

### Graph Invariants

Fortunately, the problem of checking whether two graphs are *not* isomorphic is often easier. For example, if $G_1$ has 5 nodes and $G_2$ has 6 nodes, they certainly are not isomorphic. A graph property which is preserved by isomorphism is called a **graph invariant**.

Some examples of graph invariants:

1. Number of nodes
2. Number of edges
3. Maximum node degree
4. Number of triangle (3-cycle) subgraphs
5. Number of connected components

### Question

1\. Show that the following pairs of graphs are not isomorphic by finding an invariant that they do not share.
![](matlab/question_invariant_1.png) ![](matlab/question_invariant_2.png)

2\. Write down two more graph invariants.

## Random Graphs

```{admonition} definition

A **random graph** is a graph in which the edges are determined in a random way. Given a set of $n$ nodes and edge probability $p$, we define a random simple digraph such that for each node pair $i, j$ $(i\neq j)$ there exists an edge $(i, j)$ with probability $p$.

This definition of random graph is more properly called an **Erdös-Rényi** random graph.

```

We can easily generate random directed graphs using the adjacency matrix graph representation. For a simple digraph, diagonal elements of the matrix are 0, each other element is 1 with probability $p$ and 0 with probability $1-p$.

### Question 4

1. What is the expected number of edges of a random digraph with $n$ nodes and edge probability $p$?
2. Write a program which, given integer $n$ and probability $p$, generates a random simple digraph and determines if it is connected.
3. Use your script to estimate the probability that a random directed graph with 10 nodes and $p= 0.1$ is connected.

## Null Models

What do the graph statistics that we have studied --- such as degree distribution and average path length --- tell us about brain circuits? These statistics scale with the number of edges and nodes in the graph, and so depend on the graph size and connection density as well as other basic properties of the graph.

Given a graph of a neural circuit, a **null model** is a random graph with identical basic properties such as number of nodes and edges. By comparing global properties of the neural circuit graph with the random graph, it is possible to determine whether the properties of the circuit are large or small in relation to the null model.

### Example

The graph of a region of the *Drosophila* connectome, PED\(R\), with connection weight greater than or equal to 10, has $n=197$ nodes and $e=516$ edges, resulting in an edge probability of $p=e/(n^2-n)=0.0134$. We construct a null model consisting of a random graph with $n=197$ nodes and edge probability $p=0.0134$.

PED\(R\) has average path length 2.1 and global clustering coefficient 0.69, compared to 5.3 and 0.02 for the null model.

The **normalised** average path length and global clustering coefficient are $2.1/5.3=0.40$ and $0.69/0.02=34.5$ respectively.


%
%\section*{Network Motifs}
%
%Consider a pair of nodes in a graph. There are four possible ways they may be connected.
%
%\begin{figure}[h]
%	\centering
%	\includegraphics[trim=0 5 0 5,clip,width=0.8\columnwidth]{matlab/pair_motifs.pdf}
%	\caption{Four possible subgraphs of order 2.}
%\end{figure}
%\
%\\
%However, the first subgraph is not connected, and the second and third subgraphs are isomorphic to each other. So there are in fact only two possibilities for connected subgraphs of order 2.
%
%\
%\\
%If we consider triplets of nodes, then there are 13 possible ways they may be connected (Figure~\ref{fig:triplets}). Any connected order 3 subgraph is isomorphic to one of these.
%\ \\
%Each of the possibilities is termed an \textbf{isomorphism class}.
%
%\begin{figure}[h]
%	\centering
%	\includegraphics[trim=0 5 0 5,clip,width=0.8\columnwidth]{matlab/triplet_motifs.pdf}
%	\caption{The 13 isomorphism classes of order 3 connected digraphs. Any connected order 3 subgraph is isomorphic to one of th
%		ese.}
%	\label{fig:triplets}
%\end{figure}
%\
%\\
%A \textbf{network motif} of order $n$ is defined as a connected subgraph consisting of $n$ nodes. For a given $n$, the network motif belongs to one of the order $n$ isomorphism classes.
%
%\ \\
%Usually we are interested in motifs which are statistically overrepresented. That is, they appear more often than we would expect by chance.
%
%\begin{question}
%	\begin{enumerate}
%		\item Which of the 13 order 3 digraphs are contained in the egg-laying circuit?
%		\item $G$ is a connected order 6 digraph whose only order 3 network motif is $m_1^3$. Draw $G$.
%		\item How many distinct adjacency matrices define a graph isomorphic to $m_9^3$?
%	\end{enumerate}
%
%\end{question}
